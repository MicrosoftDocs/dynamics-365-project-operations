---
title: Enable actuals validation to prevent invalid actuals
description: Learn how to avoid errors caused by invalid Dataverse actuals that were rolled back.
author: ryansandness
ms.author: ryansandness
ms.date: 09/24/2026
ms.topic: how-to 
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Enable actuals validation to prevent invalid actuals

[!INCLUDE [banner](../includes/banner.md)]

When you enable this optional feature, you turn on extra validations for actuals records that Microsoft Dataverse integrates into the finance and operations infrastructure. The feature prevalidates the actuals before you can create records during the import from staging process. This validation step prevents the creation of records that might not be able to post. Because of timeouts, rollbacks, and the general nature of dual-write, an originating actuals record might roll back in Dataverse. As a result, you can create integration journals that aren't valid.

This feature introduces an asynchronous delay in the import from staging table process. There's now a five-minute wait period between the time when transactions are available for import and the time when the validation runs. Only validated transactions continue to the creation of cost and unbilled sales integration journal lines, and the creation of billed sales invoice lines.

## Error messages that this feature can help avoid

For [integration journals](../project-accounting/project-operations-integration-journal.md), the corresponding records that you created aren't valid. When you post those records, they're labeled as "invalid actuals." When you post the integration journal, you might receive errors that indicate that this situation occurred. Here are some examples of these errors:

> Unable to look up msdyn_actuals with values X

> Attribute msdyn_transactiontypecode not found in the record of type msdyn_actual

> Unable to write data to entity msdyn_actuals

Because you can't correct the records, they remain in the integration journal error list.

You can also receive errors about invalid actuals for [invoice proposals](../invoicing/format-update-project-invoice-proposals.md). When you try to post the invoice proposal, you might receive an error that resembles the following example:

> Unable to write data to entity msdyn_actuals

This error blocks the invoice from being posted, and the invoice remains stuck in an open state.

## Enable the feature

In Feature management, enable the **Project actuals prevalidation** feature.

In version 10.0.45 and later, enabling this feature automatically enables the **Project operations actuals validation** process automation. Disabling the feature automatically disables the process automation. You don't have to separately enable or disable the process automation.

For versions earlier than 10.0.45, after you enable the feature, go to **System administration** > **Setup** > **Initialize process automations**. Then verify that the **Project operations actuals validation** process is enabled in **Process automation**.

The **Project operations actuals validation** process uses the finance and operations process automation framework. The **Process automation polling system job** starts the validation process according to its schedule.

The validation process connects to Dataverse by using **IOrganizationService** and verifies staging records against actuals in Dataverse. If a corresponding actual can't be found or doesn't match, the staging record is marked as invalid. Only records that successfully complete validation become available to the **Import from staging** process.

The validation process runs every five minutes. Because validation is asynchronous, an actual might not be immediately available to the **Import from staging** process. Processing might take longer if the system has a backlog.

You can turn the **Project actuals prevalidation** feature off and on as required. In version 10.0.45 and later, the corresponding process automation is automatically disabled or enabled with the feature. The feature should be disabled if it is no longer necessary for you.

## Resolve missing integration journal records

If no records appear in the integration journal after you run **Import from staging**, verify the following configuration:

1. In **Feature management**, verify that **Project actuals prevalidation** is enabled.
1. In **System administration** > **Setup** > **Process automation**, verify that **Project operations actuals validation** is enabled.
1. In **System administration** > **Inquiries** > **Batch jobs**, find the **Process automation polling system job**.
1. Verify that the batch job has a status such as **Waiting** or **Executing**. If its status is **Withheld**, change the status to **Waiting**.
1. Allow the polling job and validation process to run before you retry **Import from staging**.

In some development environments, including Unified Development Environments (UDEs), the **Process automation polling system job** might be in a **Withheld** state. If the job was withheld for an extended period, processing might take longer than the normal five-minute interval while the system processes the backlog.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
