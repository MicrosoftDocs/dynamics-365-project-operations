---
title: Globalization support for Project Operations
description: This article provides information about globalization features for Project Operations
author: ryansandness
ms.author: ryansandness
ms.date: 04/24/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Globalization support for Project Operations

[!INCLUDE[banner](../includes/banner.md)]

To operate your businesses globally, you must comply with country or region‑specific requirements for taxation, statutory reporting, and local business practices. These requirements vary significantly between jurisdictions and local governments frequently update them, often with strict enforcement timelines.

Dynamics 365 Finance provides a globalization platform that enables organizations to support these jurisdictional requirements across multiple countries and regions.

The Globalization Studio reduces the complexity of addressing regulatory and business practice differences by providing:

- No‑code or low‑code globalization tools and services. These flexible tools enable Microsoft, partners, and customers to create, extend, automate, and maintain localization functionality across jurisdictions.
- Out‑of‑the‑box localization content for countries and regions. Microsoft‑provided regulatory features that are continuously monitored and updated to comply with local requirements, and partners can extend.

Project Operations uses the [Globalization Studio](/dynamics365/finance/localizations/global/globalization-studio-overview) for country or region‑specific localization functionality in finance and operations apps.

## Country specific features

Localization functionality specific to individual countries or regions is documented in Finance. Use the table of contents on the left for each country. See [Australia](/dynamics365/finance/localizations/australia/australia) as an example.

## Features that apply to multiple countries

Project Operations supports the following features in Globalization Studio:

- Establishments
- Registration IDs

### Establishments

An establishment represents an operational unit of a legal entity that carries out economic activity on a stable basis and might require its own regulatory identifiers, such as registration numbers used on invoices and regulatory reports.

Establishments are country and region-agnostic, but the feature supports compliance with statutory invoicing requirements across multiple jurisdictions.

### Registration IDs

All countries and regions have requirements for supporting various country and region-specific functionalities related to registration numbers that different state offices provide. **Registration IDs** in Finance provide a unified framework for managing official identification numbers for legal entities, establishments, customers, vendors, and other parties, in accordance with country or region‑specific requirements.

#### Use establishments and registration IDs

To enable this functionality, turn on the **Establishment and Registration ID governance on invoices** feature in **Feature Management**.

For intercompany scenarios, turn on the **Vendor ship-from address support on invoices** feature in **Feature Management**.

You might also need to turn on accounts receivables parameters and accounts payables parameters for some scenarios. For example, project intercompany uses the intercompany customer invoice, which is an extension.

Feature enhancements include:

- A new Project Management and Accounting parameter on the **Invoice** tab for **Require establishment on project invoice**. This feature blocks interactive or batch posting if no establishment is set on the invoice header.
- A new Project Management and Accounting parameter on the **Invoice** tab for **Require registration IDs on project invoice**. This feature blocks interactive or batch posting if any invalid or missing registration IDs are found.
- The **Registration IDs** button now appears in the ribbon of the **Project Invoice Proposal** **Intercompany customer invoice** forms when the associated parameter is enabled. You can preview before posting and view the posted IDs later.
- The **Establishment** control now appears in the header of the **Project Invoice Proposal** and **Intercompany customer invoice** forms when the associated parameter is enabled.

The logic for the establishments is:

- The system checks the financial dimensions of the project transactions on the invoice proposal and the dimensions for the invoice proposal header for consistency. It sets a default establishment if they all match.
- If the system doesn't find a match for the establishment, it leaves the value blank, and posting fails unless you select a valid establishment.
- If the system finds a mismatch of values that results in more than one establishment being valid, users see an error. Users can manually select the establishment if valid, or the user can remove lines to split the invoice so each invoice is specific to an individual establishment.
- Intercompany customer invoicing and project free text invoices also follow this same logic, but the Accounts Receivable parameters control it for **Require establishment on customer invoice** and **Require registration IDs on customer invoice**.
- Project procurement and intercompany vendor invoices also follow this same logic, but the Accounts Payable parameters control it for **Require establishments on vendor invoice** and **Require registration IDs on vendor invoice**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
