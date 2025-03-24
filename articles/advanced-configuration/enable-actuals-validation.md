---
title: Enable actuals validation to prevent invalid actuals
description: This article provides information about how to avoid errors caused by invalid Dataverse actuals that were rolled back.
author: ryansandness
ms.author: ryansandness
ms.date: 03/24/2025
ms.topic: how-to 
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Enable actuals validation to prevent invalid actuals

[!INCLUDE[banner](../includes/banner.md)]

This optional feature enables more validations for actuals records that are integrated from Dataverse into the finance and operations infrastructure and prevalidates the actuals before allowing the records to be created during the import from the staging process that may not be able to post. Due to time-outs, rollbacks, and the general nature of Dual-Write, integration journals can be created that aren't valid because the originating actuals record was rolled back in Dataverse.  

This feature introduces an asynchronous delay to import from the staging table process where there's a five-minute wait period between when transactions are available for import and when the validation runs. Only validated transactions continue on for cost and unbilled sales Integration journal line creation and Billed Sales Invoice line creation.

## Error messages that may be avoided by enabling this feature

For [Integration journals](../project-accounting/project-operations-integration-journal.md), the corresponding records that were created aren't valid, and when posted, are labeled as "invalid actuals." You may see errors like "Unable to look up msdyn_actuals with values X," "Attribute msdyn_transactiontypecode not found in the record of type msdyn_actual," or "Unable to write data to entity msdyn_actuals" when posting the Integration journal as indications this situation occurred.  These records remain in the integration journal error list as they can't be corrected.  

For [Invoice proposals](../invoicing/format-update-project-invoice-proposals.md), you can also receive errors from invalid actuals. When attempting to post the Invoice Proposal, you may receive an error such as "Unable to write data to entity msdyn_actuals." This error blocks the invoice from posting and it's stuck in an open state.

### Enabling the feature

With the 10.0.43 release, the **Project actuals prevalidation feature** needs to be enabled in **Feature management**. Once enabled, there's another process to enable in **Process automation** in the finance and operations architecture. To enable **Process automation**, select the **Initialize process automations** link in **System administration \> Setup**. This process runs every five minutes.  

Once **Process automation** is enabled, a background batch job runs on the defined schedule. The batch job connects to Dataverse using **IOrganizationService** to match staging table records against the two systems. Any discrepancies have the Actual record in Finance updated to be invalid. Once validated, the Actual record is then made available to the import from staging process to create records from.  

The process automation can be turned off and on as needed.  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
