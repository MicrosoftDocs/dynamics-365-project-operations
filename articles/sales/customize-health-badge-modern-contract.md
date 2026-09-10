---
title: Customize health badges in the modern contract experience (preview)
description: Customize health badges in the Modern Contract experience for Dynamics 365 Project Operations. Learn how to configure grid and KPI thresholds, colors, and rules.
author: poojafandan
ms.date: 09/10/2026
ms.topic: how-to
ms.custom: bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Customize health badges in the modern contract experience (preview)

[!INCLUDE [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

> **Audience: administrators and solution customizers.** This guide explains how to configure the health badge thresholds shown in the Modern Contract experience. It includes internal source references for context. You configure the health badges through the form designer and Form XML, or through a web resource and Setting Definition environment values, as described in this article.

There are two distinct health badges in the Modern Contract experience, each with its own control
and configuration surface:

- **Grid health badge** — the pill badge shown as a grid column: the "Contract health" column on the **My Project Contracts (Modern)** list page, or the "Line health" column on the **Lines** tab sub-grid of the Contract form.
- **KPI card health badge** — the round health badge shown next to a KPI section header on the *form* (for example, the "Financial" section on the Modern Contract form).

Use the section in this article that matches the badge you want to configure.

## Where each badge lives

| &nbsp; | Grid health badge | KPI card health badge |
| --- | --- | --- |
| Control | `ContractListGridCustomizer` / `ContractLinesGridCustomizer` (grid column customizer) | `ModernKPIControl` (PCF, `control-type="virtual"`) placed on the **form**, in `kpiMode="SectionHeader"` |
| Where configured | A **web resource** (`ListHealth.xml` / `LineHealth.xml`) referenced by a **Setting Definition** (`msdyn_ModernContractListHealthConfigSource` / `msdyn_ModernContractLineHealthConfigSource`) | A **JSON block inside the `kpiSourceConfig` parameter** of the PCF control, authored directly in **Form XML** (no setting definition, no separate web resource) |
| Data scope | One badge per grid row (per record) | One badge per KPI/section on the form (aggregated across the record and related records) |
| Update mechanism | Edit web resource content and publish | Edit form XML (via form designer parameters, or solution XML) and publish |

Because each badge sources its health configuration differently, the two guides below don't reuse each other's configuration pattern.

## Part 1: Grid health badge customization guide

This guide covers the pill badge that appears as a **grid column** — either the "Contract health" column on the **My Project Contracts (Modern)** list page, or the "Line health" column on the **Lines** tab sub-grid of the Contract form.

### 1. Where this badge lives

| Grid | Column label | Control | Config web resource | Setting Definition |
| --- | --- | --- | --- | --- |
| My Project Contracts (Modern) list | **Contract health** | `ContractListGridCustomizer` (OneGrid PCF customizer) | `msdyn_/ModernContract/ListHealth.xml` | `msdyn_ModernContractListHealthConfigSource` |
| Contract form → Lines tab sub-grid | **Line health** | `ContractLinesGridCustomizer` (OneGrid PCF customizer) | `msdyn_/ModernContract/LineHealth.xml` | `msdyn_ModernContractLineHealthConfigSource` |

Both customizers share the same JSON schema and parsing and evaluation logic, defined once in a shared health-badge configuration module (`parseHealthBadgeConfig`, `resolveHealthBadgeState`, `resolveHealthBadgeVisual`, `loadHealthBadgeConfigFromWebResource`).

### 2. How the grid health badge works (architecture)

``` txt
Grid customizer init()
 └─ reads Power Platform setting (msdyn_ModernContract{List|Line}HealthConfigSource)
      → gives the web resource NAME to load (defaults to ListHealth.xml / LineHealth.xml,
        but can be overridden to point at a customer-owned web resource — see Step 3)
 └─ loadHealthBadgeConfigFromWebResource(name)
      → fetches the web resource, extracts <json><![CDATA[ ... ]]></json>, parses + validates it
      → falls back to "no badge" (renders no pill) if missing/invalid, never breaks the grid
 └─ per-row cell renderer (ContractHealthCell / healthBadge()) builds a metrics map from the
    row's already-loaded/aliased columns (e.g. grossMargin, costIncurred, nteUtilization, …)
 └─ resolveHealthBadgeState(metrics, config)
      → evaluates config.rules top-to-bottom; first matching rule's level wins; else "onTrack"
      → returns undefined if any metric referenced by a rule is missing (badge cell is blank)
 └─ resolveHealthBadgeVisual(state, config, getString)
      → looks up config.badge[state] for the label key (localized) + color + background
 └─ cell renders the colored pill
```

Key source components:

- The shared health-badge configuration module — parses and validates the JSON schema and evaluates rules (`IHealthBadgeConfig`, `IHealthBadgeRule`, `resolveHealthBadgeState`).
- The list-page grid customizer — reads the `msdyn_ModernContractListHealthConfigSource` setting and builds the row-level metrics map for the **Contract health** column.
- The Lines sub-grid customizer — reads the `msdyn_ModernContractLineHealthConfigSource` setting and builds the row-level metrics map for the **Line health** column.
- The default configuration web resources, `ListHealth.xml` and `LineHealth.xml`.

### 3. Metrics available to rules, per grid

Rules can only reference metric names that the customizer computes and passes to
`resolveHealthBadgeState`. Both grids evaluate every listed metric, even if the metric isn't part of the
matched rule. Plan thresholds against this exact set.

#### Contract health (list page) — `ContractHealthCell`

| Metric | Meaning |
| --- | --- |
| `grossMargin` | Current gross margin (aggregated contract performance). |
| `expectedMargin` | Expected margin baseline. |
| `marginDelta` | `grossMargin - expectedMargin` (0 when either operand is missing). |
| `costIncurred` | Cost incurred to date. |
| `nteUtilization` | NTE consumed, as a percentage (0 when unavailable). |

Shipped default rule (`ListHealth.xml`): **OffTrack** when `marginDelta < 0` **or** `nteUtilization >= 75`. Anything else is **OnTrack** (the list doesn't have a default "Watch" band — add one via `rules` if desired).

#### Line health (Lines sub-grid) — `healthBadge()`

| Metric | Meaning |
| --- | --- |
| `nteConsumedPct` | NTE consumed, as a percentage (0 when unavailable). |
| `margin` | Current line margin. |
| `expectedMargin` | Expected line margin baseline. |
| `marginDelta` | `margin - expectedMargin`, or `null` when either operand is missing. |
| `marginAtRisk` | `1` when the line has billing (`billedAmount > 0`) and `margin <= 0`; else `0`. |
| `marginBelowExpected` | `1` when the line has billing and `margin < expectedMargin`; else `0`. |
| `budgetVariance` | Stored budget-variance value (0 when unavailable). |
| `billedAmount` | Billed amount for the line. |
| `hasBilling` | `1` when `billedAmount > 0`; else `0`. |

Shipped default rules (`LineHealth.xml`):

- **OffTrack** when `nteConsumedPct >= 100` **or** `marginAtRisk >= 1` **or** `budgetVariance < 0`.
- **Watch** when `nteConsumedPct >= 75` **or** `marginBelowExpected >= 1`.
- Else **OnTrack**.

> [!NOTE]
> The `marginAtRisk` / `marginBelowExpected` / `hasBilling` pattern: these are boolean flags use `0` and `1` so you can compare them by using the same `>=` operators as numeric metrics. Use this pattern if you need to add a new conditional (non-ratio) signal.

### 4. Customization steps

#### Step 1 — Decide: edit in place, or override with a customer-owned resource?

The shipped `ListHealth.xml` and `LineHealth.xml` web resources are meant to be **overridden**, not
edited directly, so upgrades don't silently revert your customization. Both files carry the
comment:

> "Override `msdyn_ModernContract{List|Line}HealthConfigSource` to use a customer-owned resource with this format."

Recommended pattern:

1. Create a new web resource (for example, `xyz_/ModernContract/ListHealth.xml`) with the same `<healthBadgeConfiguration><json><![CDATA[ ... ]]></json></healthBadgeConfiguration>` shape.
1. Create an **environment value override** for the corresponding Setting Definition that points at your resource name instead of the shipped default (see Step 2). Don't try to edit the Setting Definition itself.

If you're doing rapid iteration in a dev/test environment only, you can edit the shipped resource directly — just know an upgrade might overwrite it.

#### Step 2 — Create an environment value override (only if using a customer-owned resource)

The Setting Definitions (`msdyn_ModernContractListHealthConfigSource` and `msdyn_ModernContractLineHealthConfigSource`) intentionally lock their Microsoft-owned metadata with `iscustomizable="0"`. The maker UI therefore shows **Setting definition cannot be customized** and disables fields such as Name, Data type, and Default value. This restriction doesn't prevent configuration: `isoverridable="1"` and `overridablelevel="1"` allow an organization/environment value to replace the shipped default at runtime.

To configure the override, follow these steps:

1. Open the applicable Setting Definition.
1. In **Setting environment value**, select **+ New environment value**.
1. Enter the exact name of your published customer-owned web resource, for example, `xyz_/ModernContract/ListHealth.xml` or `xyz_/ModernContract/LineHealth.xml`.
1. Save the environment value.

The override is environment-wide; app-level overrides aren't supported. The **Default value** remains the shipped resource name (for example, `msdyn_/ModernContract/ListHealth.xml`) and shouldn't be edited. Skip this step if you're editing the shipped file in place.

#### Step 3 — Edit the JSON

Both files share the same schema:

``` jsonc
{
  "rules": [
    {
      "level": "OffTrack",              // "OffTrack" or "Watch"
      "anyOf": [                         // first rule (top-to-bottom) whose anyOf has any match wins
        { "metric": "marginDelta", "op": "<", "value": 0 },
        { "metric": "nteUtilization", "op": ">=", "value": 75 }
      ]
    }
    // Optionally add a "Watch" rule block (see LineHealth.xml for an example with both levels).
    // If no rule matches, the badge is "OnTrack".
  ],
  "badge": {
    "onTrack":  { "labelKey": "HealthBadge_OnTrack",  "color": "#107C10", "background": "#DFF6DD" },
    "watch":    { "labelKey": "HealthBadge_Monitor",  "color": "#8A4B08", "background": "#FFF4CE" },
    "offTrack": { "labelKey": "HealthBadge_AtRisk",   "color": "#A4262C", "background": "#FDE7E9" }
  }
}
```

Customization options, from least to most involved:

1. **Change thresholds only** — edit the numeric `value`/`op` pairs in `rules[].anyOf`. You must use one of the metric names listed in Section 3 for that grid — `resolveHealthBadgeState` returns `undefined` (blank badge) if any rule references an unrecognized or unavailable metric.
1. **Add a "Watch" band** — add a second rule object with `"level": "Watch"` (list-page config ships with OffTrack only; the Lines config already has both — use it as a template).
1. **Change badge text/colors** — edit the three `badge.onTrack/watch/offTrack` entries. `labelKey` must resolve via the grid customizer's resource strings (`getString`); `color` and `background` accept literal CSS colors directly, no resource needed.
1. **Derive a new named metric from existing ones — no code change needed.** The shared schema supports an optional top-level `"ratios"` array with the exact same shape as the KPI card's (`{ "as": "...", "num": "...", "den": "...", "defaultNoDen": 0 }`), even though neither shipped `ListHealth.xml` nor `LineHealth.xml` uses it today. Any `num`/`den` you reference must already be one of the metric names in Section 3 for that grid (or the name of another ratio). `resolveHealthBadgeState` computes all `ratios` before evaluating `rules`, so you can reference `ratios[].as` directly from `rules[].anyOf[].metric`. You only need a grid customizer code change (`ContractHealthCell` / `healthBadge()`) when you need a **new raw metric that isn't read or computed today** (for example, a field not currently selected on the row).

#### Step 4 — Publish

To publish the changes, follow these steps:

1. Save and publish the web resource (classic customizations: **Save → Publish**; solution-based: re-import or update the web resource component).
1. If you created or changed the environment value override (Step 2), ensure it's saved for the environment.
1. Refresh the grid (list page or Contract form Lines tab) to verify: the badge should re-color per the new thresholds and labels.

No PCF rebuild is required for JSON-only changes (thresholds, colors, labelKey swaps to *existing* keys) — the customizer loads the config web resource at runtime. A rebuild is only needed if you add a brand-new `labelKey` not already in the customizer's resource strings, or if you need a new metric not already computed by the grid (Step 3, option 4).

### 5. Validation checklist

- [ ] Confirm you edited the correct file for the correct grid (List vs. Lines – they're separate web resources with different available metrics).
- [ ] Confirm every `metric` in `rules[].anyOf` matches a name from Section 3 for that grid exactly (case-sensitive).
- [ ] If you created an environment value override for a customer-owned resource, confirm the resource name matches exactly (including the publisher prefix and folder path).
- [ ] If you customized badge colors, verify sufficient contrast for accessibility (WCAG AA) for both the pill background and text color.
- [ ] Test all three states (OnTrack, Watch, OffTrack) with representative rows, plus the **no badge** case (a row whose contract-performance data hasn't loaded yet).
- [ ] Verify the JSON is well-formed and passes shape validation (both `rules` and a complete `badge` block — all three states — are required, or the whole config is rejected and no badge renders).

## Part 2: KPI card health badge customization guide

Covers the round health badge shown next to a **KPI section header** on the *form* (for example, the "Financial" section on the Modern Contract form). This badge uses a different control, a different configuration surface, and a different deployment step than the grid health badge.

### 1. How the KPI card health badge works (architecture)

`ModernKPIControl` is intentionally **generic** — it has no built-in knowledge of `salesorder`, `msdyn_contractperformance`, or any other entity or attribute. The `kpiSourceConfig` property (type `Multiple`, a JSON string) on the control instance for that form placement provides all the information about *what* to read and *how* to rate it when `kpiMode` is `SectionHeader`. *How* to rate it comes from the `kpiSourceConfig` property (type `Multiple`, i.e. a JSON string) set on the control instance for that form placement, when `kpiMode = SectionHeader`.

``` txt
Form (Form XML)
 └─ customControl: msdyn_ModernKPIControl.ModernKPIControl   (kpiMode = SectionHeader)
      └─ kpiSourceConfig (JSON) ──▶ KpiSnapshot.fetchKpiSnapshot()
                                        │  reads primary record + secondary reads + derived values
                                        ▼
                                 flat numeric "namespace" (Record<string, number>)
                                        │
                                        ▼
                         KpiSnapshot.computeKpiHealth(health, snapshot)
                                        │  evaluates ratios, then rules (first match wins)
                                        ▼
                                OnTrack | Watch | OffTrack
                                        │
                                        ▼
                     KPISectionHealthHeader.tsx renders the badge
                       (label / color / background from health.badge, or built-in defaults)
```

Key source files (for reference, not required reading to customize the badge):

- `ModernKPIControl` PCF control source — includes the config types (`IKpiSourceConfig`, `IKpiHealthSpec`, `IKpiHealthRule`, `IKpiHealthBadgeConfig`), data-fetch logic, and `computeKpiHealth()`.
- The section-header rendering component — renders the pill badge, **Last updated** text, and click-to-navigate-to-tab behavior.
- The control manifest — defines control properties, including `kpiMode` and `kpiSourceConfig`.

### 2. Customization steps

#### Step 1 — Locate the control instances on the form — in **every** copy of that form

To locate the control instances, follow these steps:

1. Open the target form (for example, Contract main form) in the classic form editor or via Form XML.
1. Find the `customControl` element whose `name` is `msdyn_ModernKPIControl.ModernKPIControl` **and** whose `parameters/kpiMode` is `SectionHeader`, on the section you want to change (for example, the "Financial" section). A form can have more than one KPI control instance (for example, duplicated per form factor — web vs. mobile — so update every matching instance).
1. **Critical:** if your organization maintains the contract form across multiple solution layers or packages (for example, an unmanaged development layer, a managed layer, and any solutions that re-export the same form), the same KPI health config is duplicated across each copy. Editing only one copy ships the change to only some layers and solutions — the gap stays invisible until a managed import or an exported app is inspected. Locate every copy of the form (they share the same form ID) and apply the identical edit to each one before publishing.

#### Step 2 — Edit the `kpiSourceConfig` JSON

The JSON has this shape (fields you typically touch for a health badge are `health` and `navigateTabName`; the rest — `entity`, `select`, `secondary`, `derived` — define which values are available to reference and are usually left as-is unless you're adding a new metric):

``` jsonc
{
  "entity": "msdyn_contractperformance",       // primary record to read
  "parentField": "msdyn_salesorderid",         // related-record lookup back to the host record
  "filter": "_msdyn_contractlineid_value eq null and statecode eq 0",
  "select": ["msdyn_contractvalue", "msdyn_billedamount", "msdyn_costincurred", "msdyn_estimatedcost"],
  "lastUpdatedField": "modifiedon",

  // Optional extra scalar reads, added to the same flat namespace as "select" fields.
  "secondary": [
    { "as": "nteLimit", "entity": "salesorder", "field": "msdyn_nottoexceedlimit_base", "byRecordId": true },
    { "as": "lineValueSum", "entity": "salesorderdetail", "field": "extendedamount", "parentField": "salesorderid", "sum": true }
  ],

  // Optional computed values (fallback chains or differences), also added to the namespace.
  "derived": [
    { "as": "contractValueEff", "sources": [{ "field": "msdyn_contractvalue", "skipZero": true }, { "field": "lineValueSum" }] },
    { "as": "marginNumerator", "diff": { "minuend": "contractValueEff", "subtrahend": "msdyn_estimatedcost" } }
  ],

  // ── The health badge itself ──
  "health": {
    // Named ratios computed from namespace values, referenced by rules below.
    "ratios": [
      { "as": "nteConsumption",   "num": "msdyn_billedamount",  "den": "nteLimit",           "defaultNoDen": 0 },
      { "as": "costConsumption", "num": "msdyn_costincurred",   "den": "msdyn_estimatedcost","defaultNoDen": 0 },
      { "as": "expectedMargin",  "num": "marginNumerator",      "den": "contractValueEff",   "defaultNoDen": 1 }
    ],

    // Rules are evaluated top-to-bottom; the FIRST matching rule's level wins.
    // If no rule matches, the badge is "OnTrack".
    "rules": [
      { "level": "OffTrack", "anyOf": [
          { "metric": "costConsumption", "op": ">",  "value": 1 },
          { "metric": "nteConsumption",  "op": ">=", "value": 1 },
          { "metric": "expectedMargin",  "op": "<",  "value": 0 }
      ]},
      { "level": "Watch", "anyOf": [
          { "metric": "costConsumption", "op": ">=", "value": 0.9 },
          { "metric": "nteConsumption",  "op": ">=", "value": 0.8 },
          { "metric": "expectedMargin",  "op": "<",  "value": 0.1 }
      ]}
    ],

    // Optional per-state label/color override. Omit a state (or the whole "badge" block) to
    // fall back to the control's built-in label/icon/color defaults for that state.
    "badge": {
      "onTrack":  { "labelKey": "KpiSectionHeader_Health_OnTrack",  "color": "#0e700e", "background": "#e6f2e6" },
      "watch":    { "labelKey": "KpiSectionHeader_Health_Watch",    "color": "#8a6a00", "background": "#fbf3d5" },
      "offTrack": { "labelKey": "KpiSectionHeader_Health_OffTrack", "color": "#b10e1c", "background": "#fde7e9" }
    }
  },

  // Optional: clicking the badge focuses this form tab (logical name of a <tab> element).
  "navigateTabName": "analysis_tab"
}
```

Customization options, from least to most involved:

1. **Change thresholds only** — edit the numeric `value`s and `op`s under `health.rules` / `health.ratios`. No new data source needed. This change is the most common request (for example, "flag Watch at 75% NTE consumption instead of 80%").
1. **Change badge text/colors** — edit `health.badge.onTrack/watch/offTrack`. `labelKey` must resolve through the control's resource strings (see Step 3) — you can't inline arbitrary literal text for the label. The `color` and `background` properties accept any CSS color string directly (no separate resource needed).
1. **Add a new metric to the rules** — first add the field to `select` (if it's on the primary record), or add a `secondary` or `derived` entry to bring it into the namespace, then reference it from a `ratios` entry or directly by name in `rules[].anyOf[].metric`.
1. **Repoint which tab the badge navigates to** — change `navigateTabName` to the logical name of the desired `<tab>`.

> [!NOTE]
> The important semantic: **all listed metrics referenced by `rules` must be present** for a rating to be produced — if any required metric is missing/null, the badge shows **"No data"** instead of a rating. Keep this in mind when adding conditions that depend on optional secondary reads.

#### Step 3 — (Only if adding a new label) Add a resource string

If you introduce a new `labelKey` (rather than reusing an existing one), add the key/value pair to the control's localized resource files, then rebuild and redeploy the PCF control so the new resource is packaged. Skip this step if you're only reusing one of the existing `KpiSectionHeader_Health_*` keys.

#### Step 4 — Publish

Unlike the grid badge (which is a web resource edit you publish independently of the form), the KPI card's health config lives **inside the form**. After editing:

1. Save and publish the form (classic customizations: **Save → Publish**; solution-based: re-import or update the Form XML component) — for **every** form copy you edited in Step 1.
1. If you changed the resource string (Step 3), rebuild the `ModernKPIControl` PCF and import the updated solution **before** publishing the form, so the new label keys resolve.
1. Hard-refresh the form to verify: the badge recolors according to your new thresholds, and hovering shows the updated label.

### 3. Validation checklist

- [ ] Confirm which `customControl` instances you edited match the section or tile you intended. Check for duplicate `formFactor` entries — Web versus phone or tablet — and update all of them.
- [ ] Confirm you applied the identical edit to every copy of the form across the solution layers or packages your organization maintains.
- [ ] Confirm every `metric` referenced in `health.rules` is actually populated in `select`, `secondary`, `derived`, or `ratios`. Otherwise, the badge silently shows "No data".
- [ ] If you customized badge colors, verify sufficient contrast for accessibility (WCAG AA) for both the pill background and the icon or text color.
- [ ] Verify `navigateTabName` (if set) matches an existing tab's logical name on the same form.
- [ ] Test all three states (OnTrack, Watch, and OffTrack) with representative data, plus the "no data" case (for example, a brand-new record with the health-relevant fields blank).

## Quick reference: Grid badge vs. KPI card badge

| Task | Grid badge (Part 1) | KPI card badge (Part 2) |
| --- | --- | --- |
| Control | `ContractListGridCustomizer` and `ContractLinesGridCustomizer` | `ModernKPIControl` (`kpiMode = SectionHeader`) |
| Where configured | Web resource (`ListHealth.xml` and `LineHealth.xml`), name resolved via a Setting Definition | Inline JSON in the `kpiSourceConfig` form-control parameter (Form XML) |
| Config format | `<healthBadgeConfiguration><json><![CDATA[ ... ]]></json></healthBadgeConfiguration>` | Raw (HTML-entity-escaped) JSON string |
| Governing setting | `msdyn_ModernContractListHealthConfigSource` and `msdyn_ModernContractLineHealthConfigSource` Setting Definitions point to the web resource | None — the JSON is inline on the control, no indirection |
| Ratios and derived metrics | Supported via a top-level `"ratios"` array (same shape as the KPI card's), but raw input metrics are fixed by the customizer's cell-renderer code (Part 1, Section 3). The shipped defaults don't use them. | Fully configurable via `health.ratios`, plus `secondary` and `derived` reads that can pull in new fields and related records. |
| Publish step | Publish the web resource and environment value override if used. | Publish the form and rebuild or import the PCF only if you added a new resource label. |
| Scope of one config block | One grid (one row per record). | One aggregated section or tile on the form. You can combine primary, related, and summed values. |
