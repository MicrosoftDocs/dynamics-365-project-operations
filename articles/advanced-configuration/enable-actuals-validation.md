---
title: Enable actuals validation to prevent invalid actuals
description: Learn how to avoid errors caused by invalid Dataverse actuals that were rolled back.
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

This optional feature enables more validations for actuals records that are integrated from Microsoft Dataverse into the finance and operations infrastructure. It prevalidates the actuals before it allows records to be created during the import from staging process. In this way, it prevents the creation of records that might not be able to be posted. Because of time-outs, rollbacks, and the general nature of dual-write, an originating actuals record might be rolled back in Dataverse. As a result, integration journals that aren't valid can be created.

This feature introduces an asynchronous delay in the import from staging table process. There is now a five-minute wait period between the time when transactions are available for import and the time when the validation runs. Only validated transactions continue to the creation of cost and unbilled sales integration journal lines, and the creation of billed sales invoice lines.

## Error messages that this feature can help avoid

For [integration journals](../project-accounting/project-operations-integration-journal.md), the corresponding records that were created aren't valid. When those records are posted, they are labeled as "invalid actuals." When you post the integration journal, you might receive errors that indicate that this situation occurred. Here are some examples of these errors:

> Unable to look up msdyn_actuals with values X

> Attribute msdyn_transactiontypecode not found in the record of type msdyn_actual

> Unable to write data to entity msdyn_actuals

Because the records can't be corrected, they remain in the integration journal error list.

You can also receive errors about invalid actuals for [invoice proposals](../invoicing/format-update-project-invoice-proposals.md). When you try to post the invoice proposal, you might receive an error that resembles the following example:

> Unable to write data to entity msdyn_actuals

This error blocks the invoice from being posted, and the invoice remains stuck in an open state.

## Enable the feature

In the 10.0.43 release, you must enable the **Project actuals prevalidation** feature in Feature management. After it's enabled, there is another process that you must enable in **Process automation** in the finance and operations architecture. To enable the process automation, go to **System administration \> Setup**, and select the **Initialize process automations**. This process runs every five minutes.

After the process automation is enabled, a background batch job runs on the defined schedule. This batch job connects to Dataverse by using **IOrganizationService** to match staging table records against the two systems. Any discrepancies cause the actuals record in Dynamics 365 Finance to be updated as invalid. After the actuals record is validated, it becomes available to the import from staging process, and records can be created from it.

You can turn the process automation off and on as you require.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
