---
title: Globalization support for Project Operations
description: This article provides information about globalization features for Project Operations
author: ryansandness
ms.author: ryansandness
ms.date: 04/17/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Globalization support for Project Operations

To operate their businesses globally, customers must comply with country or region‑specific requirements for taxation, statutory reporting, and local business practices. These requirements vary significantly between jurisdictions and are frequently updated by local governments, often with strict enforcement timelines.

Dynamics 365 Finance provides a globalization platform that enables organizations to support these jurisdictional requirements across multiple countries and regions.

The Globalization Studio reduces the complexity of addressing regulatory and business practice differences by providing:

- No‑code/low‑code globalization tools and services – Flexible tools that enable Microsoft, partners, and customers to create, extend, automate, and maintain localization functionality across jurisdictions.
- Out‑of‑the‑box localization content for countries and regions – Microsoft‑provided regulatory features that are continuously monitored and updated to comply with local requirements, and can be extended by partners.

Project Operations leverages the [Globalization Studio](/dynamics365/finance/localizations/global/globalization-studio-overview) for country or region‑specific localization functionality on the Finance and Operations platform.

## Country specific features

Localization functionality specific to individual countries are documented under Dynamics 365 Finance. Navigate using the table of contents on the left for each country. See [Australia](/dynamics365/finance/localizations/australia/australia) as an example.

## Features that apply to multiple countries

### Establishments and Registration IDs

Establishments

An establishment represents an operational unit of a legal entity that carries out economic activity on a stable basis and may require its own regulatory identifiers, such as registration numbers used on invoices and regulatory reports.

Establishments are country/region-agnostic, but the feature supports compliance with statutory invoicing requirements across multiple jurisdictions.

Registration IDs

All countries/regions have their requirements for supporting various country/region-specific functionalities related to registration numbers provided by different state offices. **Registration IDs** in Dynamics 365 Finance provide a unified framework for managing official identification numbers for legal entities, establishments, customers, vendors, and other parties, in accordance with country/region‑specific requirements.

#### Using Establishments and Registration IDs

The **Establishment and Registration ID governance on invoices** feature in **Feature Management** is required to enable this functionality.

For Intecompany scenarios, enable the **Vendor ship-from address support on invoices** feature.

Accounts Receivables parameters and accounts payables parameters may also be required to be enabled for some scenarios for as well. For example, project intercompany will use the intercompany customer invoice which is an extension 

Feature enhancements include:

- A new Project Management and Accounting parameter on the **Invoice** tab for **Require establishment on project invoice**. This feature will block interactive or batch posting if no establishment is set on the invoice header.
- A new Project Management and Accounting parameter on the **Invoice** tab for **Require registration IDs on project invoice**. This feature will block interactive or batch posting if any invalid or missing registration IDs are found.
- The **Registration IDs** button now appears in the ribbon of the **Project Invoice Proposal** **Intercompany customer invoice** forms when the associated parameter is enabled. You can preview before posting and view the posted IDs later.
- The **Establishment** control now appears in the header of the **Project Invoice Proposal** and **Intercompany customer invoice** forms when the associated parameter is enabled.

Logic for the establisments is that:

- The financial dimensions of the project transactions on the invoice proposal as well as the dimensions for the invoice proposal header will be checked for consistency and a default establishment is set if they all match.
- If no match is found for the establishment, then the value will be left blank, and posting will fail unless a valid establishment is selected.
- If a mismatch of values are found which would result in more than one establishment being valid, then users will see an error. Users can manually select the establishment if valid, or the user can remove lines to split the invoice so each invoice is specific to an individual establishment.
- Intercompany customer invoicing and project free text invoices will also follow this same logic, but is controlled by the Accounts Receivable parameters for **Require establishment on customer invoice** and **Require registration IDs on customer invoice**.
- Project procurment and intercompany vendor invoices will also follow this same logic, but is controlled by the Accounts Payabale parameters for **Require etablishment on vendor invoice** and **Require registration IDs on vendor invoice**.

