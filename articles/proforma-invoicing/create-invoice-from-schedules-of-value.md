---
title: Create invoice from selected schedules of value (Microsoft Dataverse API)
description: Learn how to create invoices from selected schedules-of-value details by using the msdyn_CreateInvoiceFromSchedulesOfValue Microsoft Dataverse action.
author: nshrivastava
ms.author: nshrivastava
ms.date: 10/27/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Create invoice from selected schedules of value

[!INCLUDE [banner](../includes/banner.md)]

Use the `msdyn_CreateInvoiceFromSchedulesOfValue` Microsoft Dataverse action to invoice selected fixed-price milestone details.

This action supports these scenarios:

- Group eligible details and reuse compatible draft invoices
- Group eligible details into new invoices
- Add eligible details to a compatible existing invoice
- Create separate invoices (one invoice per eligible detail)

## Action

This action is a public, unbound Dataverse action.

```http
POST [Organization URI]/api/data/v9.2/msdyn_CreateInvoiceFromSchedulesOfValue
```

Don't include a contract ID in the URL, and don't send a `Target` entity parameter.

## Prerequisites

Before using this action, ensure you meet the following prerequisites:

- Dataverse authentication configured for your client.
- Permissions to perform the underlying invoice operations.
- Existing `msdyn_contractlinescheduleofvalue` detail records to invoice.

## Request headers

```http
Authorization: Bearer <access-token>
Accept: application/json
Content-Type: application/json
OData-Version: 4.0
OData-MaxVersion: 4.0
```

## Request parameters

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| `msdyn_ScheduleOfValueIds` | `Collection(Edm.String)` | Yes | Array of GUID strings for `msdyn_contractlinescheduleofvalue` records (milestone details). |
| `msdyn_CreateNew` | `Edm.Boolean` | No | Default `false`. If `true`, creates new invoices instead of reusing compatible drafts. |
| `msdyn_CreateSeparateInvoices` | `Edm.Boolean` | No | Default `false`. If `true`, creates a separate invoice for each eligible detail. |
| `msdyn_TargetInvoiceId` | `Edm.String` | No | GUID of a compatible existing invoice. Omit when unused. Can't be combined with separate-invoice mode. |

> [!NOTE]
> `msdyn_ScheduleOfValueIds` must contain milestone **detail** IDs, not parent milestone IDs.

## Response properties

| Name | Type | Description |
| --- | --- | --- |
| `msdyn_InvoiceIds` | `Collection(Edm.String)` | IDs of invoices created or updated by the request. |
| `WarningMessages` | `Edm.String` | Warning text when present (semicolon-delimited if multiple). |

`msdyn_InvoiceIds` is an unordered collection. Don't assume positional mapping to input IDs.

## Choose an invoicing mode

| Scenario | `msdyn_CreateNew` | `msdyn_CreateSeparateInvoices` | `msdyn_TargetInvoiceId` | Result |
| --- | --- | --- | --- | --- |
| Group and reuse | `false` | `false` | Omit | Groups eligible details and reuses a compatible open draft when available; otherwise creates invoices. |
| Group into new invoices | `true` | `false` | Omit | Creates new invoices using normal contract and split-billing grouping. |
| Add to existing invoice | `false` | `false` | Compatible invoice GUID | Adds eligible details to the specified invoice if validations pass. |
| Create separate invoices | `false` | `true` | Omit | Creates a new invoice for each eligible detail. |

## Examples

Use the same endpoint and headers for all examples.

### Group and reuse compatible draft

```json
{
  "msdyn_ScheduleOfValueIds": ["<detail-guid-1>", "<detail-guid-2>"],
  "msdyn_CreateNew": false,
  "msdyn_CreateSeparateInvoices": false
}
```

### Group into new invoices

```json
{
  "msdyn_ScheduleOfValueIds": ["<detail-guid-1>", "<detail-guid-2>"],
  "msdyn_CreateNew": true,
  "msdyn_CreateSeparateInvoices": false
}
```

### Add to an existing invoice

```json
{
  "msdyn_ScheduleOfValueIds": ["<detail-guid-1>"],
  "msdyn_CreateNew": false,
  "msdyn_CreateSeparateInvoices": false,
  "msdyn_TargetInvoiceId": "<compatible-invoice-guid>"
}
```

### Create separate invoices

```json
{
  "msdyn_ScheduleOfValueIds": ["<detail-guid-1>", "<detail-guid-2>"],
  "msdyn_CreateNew": true,
  "msdyn_CreateSeparateInvoices": true
}
```

### Example response

```json
{
  "msdyn_InvoiceIds": ["<invoice-guid-1>", "<invoice-guid-2>"],
  "WarningMessages": "<warning text when present>"
}
```

## JavaScript example (model-driven app)

This example uses `Xrm.WebApi.online.execute` in a model-driven app context.

```javascript
class CreateInvoiceFromSchedulesOfValueRequest {
  constructor(payload) {
    Object.assign(this, payload);
  }

  getMetadata() {
    const parameterTypes = {
      msdyn_ScheduleOfValueIds: {
        typeName: "Collection(Edm.String)",
        structuralProperty: 4
      },
      msdyn_CreateNew: {
        typeName: "Edm.Boolean",
        structuralProperty: 1
      },
      msdyn_CreateSeparateInvoices: {
        typeName: "Edm.Boolean",
        structuralProperty: 1
      }
    };

    if (this.msdyn_TargetInvoiceId !== undefined) {
      parameterTypes.msdyn_TargetInvoiceId = {
        typeName: "Edm.String",
        structuralProperty: 1
      };
    }

    return {
      boundParameter: null,
      operationName: "msdyn_CreateInvoiceFromSchedulesOfValue",
      operationType: 0,
      parameterTypes
    };
  }
}

async function createInvoicesFromSchedulesOfValue(payload) {
  const request = new CreateInvoiceFromSchedulesOfValueRequest(payload);
  const response = await Xrm.WebApi.online.execute(request);

  if (!response.ok) {
    throw new Error(await response.text());
  }

  const result = await response.json();
  if (result.WarningMessages) {
    console.warn(result.WarningMessages);
  }

  return result;
}
```

## Eligibility and validation

Only eligible milestone details are invoiced. Standard invoice validations still apply.

If you don't add eligible milestones, the operation fails.

## Execution model and completion

This action runs **synchronously**.

- A successful HTTP response means the request finishes eligible data.
- The response doesn't include an asynchronous job ID or a polling receipt.

## Parallelization guidance

Invoice creation gating covers invoice creation and contract identity.

- Serialize invoice creation requests that touch the same contract.
- Requests with separate contract sets don't share this gate.

When planning parallel runs, partition by the complete contract set touched by each request.

## Retry and reconciliation pattern

This action doesn't provide a client idempotency key or exactly-once guarantee.

Use this pattern:

1. Persist a deduplicated manifest of input detail IDs, contracts, intended mode, and attempts.
1. Persist returned invoice IDs and warnings.
1. After timeout, lost response, or ambiguous failure, reconcile actual outcomes before resubmitting.
1. Retry only details confirmed still eligible and uninvoiced.
1. For Dataverse `429`, honor `Retry-After` and use bounded backoff.

## Avoiding unintended combined invoices in mass uploads

When you process separate and combined groups for the same contract:

- Run separate and combined groups in separate, sequential requests.
- For the combined phase, use `msdyn_CreateNew=true` and `msdyn_CreateSeparateInvoices=false` unless you intentionally target a compatible existing invoice.

This guidance helps you avoid unintended reuse of earlier draft invoices.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
