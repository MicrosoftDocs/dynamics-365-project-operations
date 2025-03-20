---
title: Enable actuals validation to prevent invalid actuals
description: This article provides information about how to avoid errors caused by invalid Dataverse actuals that were rolled back.
author: ryansandness
ms.date: 03/24/2025
ms.topic: article
ms.reviewer: johnmichalak
ms.author: ryansandness
---

# Enable Actuals validation to prevent invalid actuals

This optional feature enables additional validation for actuals records integrated across from Dataverse into the finance and operations infrastructure to pre-validate the actuals before allowing records to be created during the import from staging process that may not be able to be posted. Due to timeouts, rollbacks, and the general nature of Dual Write, integration journals can be created that aren’t valid because the originating actuals record was rolled back in Dataverse.  

This feature introduces an asynchronous delay to the import from staging table process where there will be a 5 minute wait period between when transactions are available for import and when the validation runs. Only validated transactions will continue on for cost and unbilled sales Integration journal line creation and Billed Sales Invoice line creation. 

## Error messages that may be avoided by enabling this feature

For [Integration journals](../project-accounting/project-operations-integration-journal.md), these corresponding records created aren’t valid and when posted will be labeled as “invalid actuals“. Users may see errors such as "Unable to lookup msdyn_actuals with values X” or "Attribute msdyn_transactiontypecode not found in the record of type msdyn_actual.", or “Unable to write data to entity msdyn_actuals.”  when posting Integration journal as indications of this situation occurring.  These records will remain in the integration journal errors list as they can’t be corrected.  

For [Invoice proposals](../invoicing/format-update-project-invoice-proposals.md), you can also receive errors from invalid actuals. When attempting to post the Invoice Proposal, users may see errors such as “Unable to write data to entity msdyn_actuals.”  when posting. This will block the Invoice from ever being able to be posted and will be stuck in an Open state.

### Enabling the feature

With the 10.0.43 release, the **Project actuals pre-validation feature** needs to be enabled in **Feature management**. Once enabled, there is a process to be enabled In Process Automation on the Finance and Operations System administrator area. To enable the Process Automation simply click the **Initialize process automations** link under System administration > Setup. The frequency for this process is set to run every 5 minutes.  

Once the Process Automation is enabled, a background batch job will run on the defined schedule. The batch job will reach out to Dataverse using the IOrganizationService to match staging table records against the two systems. Any discrepancies have the Actual in Finance updated to be invalid. Once validated, the record will then be available to the import from staging process to create records from.  

The feature can be turned off and on as needed.  

#### Other improvements in the 10.0.38 release

Here are some other improvements that were made in this area in the 10.0.38 release:

- You can multiselect rows when you work with integration headers.
- A new, optional **Limit the integration journal lines per header** parameter provides more flexible control over posting. When the parameter is disabled, 200 lines are used by default. You can increase or decrease the value of the parameter as you require. By decreasing the value, you reduce the time that's required to post the journal.
- The **Add filters to the Project Integration journal posting batch job** feature adds default filters that let users specify a period start date, a journal number, or an original journal number in the batch job filter. These filters are useful when you have transactions that require setup or configuration changes before they can be posted. You can now avoid trying to post until the issue is fixed.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
