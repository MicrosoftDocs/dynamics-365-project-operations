---
title: What's new April 2025 - Project Operations Core
description: This article provides information about quality updates that are available in the April 2025 release of Microsoft Dynamics 365 Project Operations Core.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom:
  - evergreen
  - bap-template
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak
---

# What's new April 2025 - Project Operations Core

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.140.0.239.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Time Entry |**Time Entry Agent** <br><br> This agent creates draft time entries for team members based on their project assignments, bookings, or previous week's entries and allows them to review the entries through Microsoft Teams. The agent can also generate external comments for all entries, enhanced by Outlook meeting details. Finally, team members receive alerts for missing submissions. |  |
| Approvals |**Approvals Agents** <br><br> This agent reviews submitted time, expense, and material usage entries and classifies them as "Ready for Approval" or "Needs review." The classification can assist project managers in making approvals decisions. The agent also includes an automatic approve mode where records marked as "Ready for approval" are automatically approved.|  |
| Actuals |**Corrections for entry journal actuals** <br><br> Actuals that were created via entry journals can be corrected via the correction journal process.|  |
| Quotes,Contracts,Invoicing| **Time Zone Independent Milestone Date** <br><br> This feature enables users to use time zone agnostic milestone dates helping improve accuracy of billing project based milestones |[Timezone independent milestone date](../../sales/tz-independent-date-fields.md)|
| Invoicing | **Ability to customize billing hub** <br><br> This release includes fixes that enable complete customization of Billing hub | [Customize billing hub](../../proforma-invoicing/billing-hub-customization.md)|

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing and Pricing|	3705088|	PostJournalLineCreate plugin prevents calculations if triggered by a custom code or workflow. |
|Billing and Pricing|	4213493|	Actuals created from journal lines aren't invoiceable in multi customer scenarios. |
|Billing and Pricing|	4474308|	Net 60 payment terms can't be used on contract customers.|
|Billing and Pricing|	4560418|	Unable to confirm any invoice for a project contract and customer when NTE Validation is "Not Evaluated" on an actual included in another draft invoice.|
|Billing and Pricing|	4606728|	Unable to view milestones backlog in Billing Hub.|
|Billing and Pricing|	4655376|	Copy of price list copies the number of overrides (incorrectly).|
|Billing and Pricing|	4693909|	Duplicate actuals exist when deleting confirmed invoices.|
|Billing and Pricing|	4826053|	Fields msdyn_basisprice and msdyn_basisprice_Base values are inconsistent with source values when Copying Entity if Cost Plus Pricing feature is enabled.|
|Budget Management|	4712410|	Missing budget subgrid under the budget tab of the project record.|
|Budget Management|	4829338|	Unable to see dropdown values in Transaction Category field.|
|Project Management and Resource Management|	4521947|	Soft booked hours aren't displayed in Team Member grid when viewing "All team members."|
|Project Management and Resource Management|	4536039|	Multiple Team member creations in parallel fail when start and finish dates are provided.|
|Project Management and Resource Management|	4594360|	Schedule variance doesn't get updated when Allow Percent Complete is set to "No" and when a task is marked as completed.|
|Project Management and Resource Management|	4615336|	Project Copilot's Risk assessment capability fails with "exceeding maximum limit" error.|
|Project Management and Resource Management|	4616623|	Effort remaining for NTE projects doesn't update after journal creation.|
|Project Management and Resource Management|	4795813|	Corrupted data may cause server to crash during data upgrade from PSA to Project Operations.|
|Sales|	3706647|	Error thrown "Parent field is hidden because related fields are missing in the form" in Project Information form for Products.|
|Sales|	4484560|	Null reference exception in CopyAddressFieldsFromCustomer when creating Project contract without customer.|
|Sales|	4524407|	Delete button missing for multi-select quote line milestones.|
|Sales|	4529109|	Invoice schedule type isn't redefaulted when billing method is updated on quote line.|
|Sales|	4547718|	Billing method on contract lines can be changed using the API.|
|Sales|	4556898|	Missing validations around Milestone Billing Status.|
|Sales|	4562863|	Remove validation to prevent adding customers with different currency than Contract currency.|
|Sales|	4622690|	Quote Recalculate button doesn't recalculate CostTotal for QuoteLine.|
|Sales|	4625154|	Recalculate button doesn't work within Quotes and Contracts.|
|Sales|	4635324|	"Edit " action is missing on PBB milestone header.|
|Sales|	4658525|	Error occurs during price override from Quote Line Detail (QLD).|
|Sales|	4700320|	Missing Dark Mode Support for Quote Form.|
|Sales|	4702463|	Sales quote line details' currency can be changed to one that's not the quote's currency.|
|Sales|	4769859|	The currency of cost price doesn't get updated from price list while updating role of quote or contract line details.|
|Sales|	4788954|	Unable to Search Contract Line using the Name when Associating to a Task on a Project.|
|Sales|	4789878|	Invoice Schedules Grid shows For Fixed Price Quote Lines.|
|Subcontracting|	4382804|	"Object reference not set to an instance of an object" error is thrown when closing quote as won.|
|Subcontracting|	4572320|	The label for the "New project Budget line" gets truncated, and the tooltip for this label isn't accessible via keyboard.|
|Subcontracting|	4576878|	Disable Price Override button in the Cost grid.|
|Subcontracting|	4593265|	Cost actual created from entry journal has billing status set to unbilled sales created when Vendor Invoice is canceled.|
|Subcontracting|	4593277|	Matching cost actuals created from an entry journal causes all resourcing unit actuals (cost and inter org sales) from the same journal to be canceled.|
|Subcontracting|	4734590|	Incorrect Label on Revise Budget Dialog Box.|
|Subcontracting|	4789243|	Vendor is noncustomizable and nonsearchable in Subcontract entity.|

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
