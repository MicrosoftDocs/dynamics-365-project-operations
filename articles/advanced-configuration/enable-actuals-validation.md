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

For [Integration journals](../project-accounting/project-operations-integration-journal.md), these corresponding records created aren’t valid and when posted will be labeled as “invalid actuals“. Users may see errors such as "Unable to lookup msdyn_actuals with values X”, "Attribute msdyn_transactiontypecode not found in the record of type msdyn_actual", or “Unable to write data to entity msdyn_actuals”  when posting the Integration journal as indications of this situation occurring.  These records will remain in the integration journal error list as they can’t be corrected.  

For [Invoice proposals](../invoicing/format-update-project-invoice-proposals.md), you can also receive errors from invalid actuals. When attempting to post the Invoice Proposal, users may see an error such as “Unable to write data to entity msdyn_actuals”  when posting. This will block the invoice from ever being able to be posted and will be stuck in an open state.

### Enabling the feature

With the 10.0.43 release, the **Project actuals pre-validation feature** needs to be enabled in **Feature management**. Once enabled, there is a process to be enabled in **Process Automations** on the finance and operations architecture. To enable the Process Automation simply click the **Initialize process automations** link under System administration > Setup. The frequency for this process is set to run every 5 minutes.  

Once the Process Automation is enabled, a background batch job will run on the defined schedule. The batch job will reach out to Dataverse using the IOrganizationService to match staging table records against the two systems. Any discrepancies will have the Actual record in Finance updated to be invalid. Once validated, the Actual record will then be mae available to the import from staging process to create records from.  

The process automation can be turned off and on as needed.  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
