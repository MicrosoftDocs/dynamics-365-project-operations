---
title: Configure automatic invoice creation
description: This article provides information about how to configure the system to generate invoices automatically.
author: suvaidya
ms.author: nshrivastava
ms.date: 06/10/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Configure automatic invoice creation

_**Applies To:** Project Operations Integrated with ERP_


Complete the following steps to configure an automated invoice run in Dynamics 365 Project operations.

1. In **Project Operations**, go to **Settings** > **Recurring Invoice Setup**.
2. Create a batch job, and name it **Project operations create invoices**. The name of the batch job must include the words "create invoices."
3. In the **Job Type** field, select **None**. By default, the **Frequency Daily** and **Is Active** options are set to **Yes**.
4. Select **Run Workflow**. In the **Look Up Record** dialog box, you will see three workflows:

    - ProcessRunCaller
    - ProcessRunner
    - UpdateRoleUtilization

5. Select **ProcessRunCaller**, and then select **Add**.
6. In the next dialog box, select **OK**. A **Sleep** workflow is followed by a **Process** workflow.

  > [!NOTE]
  > You can also select **ProcessRunner** in step 5. Then, when you select **OK**, a **Process** workflow is followed by a **Sleep** workflow.

The **ProcessRunCaller** and **ProcessRunner** workflows create invoices. **ProcessRunCaller** calls **ProcessRunner**. **ProcessRunner** is the workflow that actually creates the invoices. It goes through all the contract lines that invoices must be created for, and it creates invoices for those lines. To determine the contract lines that invoices must be created for, the job looks at invoice run dates for the contract lines. If contract lines that belong to one contract have the same invoice run date, the transactions are combined into one invoice that has two invoice lines. If there are no transactions to create invoices for, the job skips invoice creation.

After **ProcessRunner** has finished running, it calls **ProcessRunCaller**, provides the end time, and is closed. **ProcessRunCaller** then starts a timer that runs for 24 hours from the specified end time. At the end of the timer, **ProcessRunCaller** is closed.

The batch process job for creating invoices is a recurrent job. If this batch process is run many times, multiple instances of the job are created and cause errors. Therefore, you should start the batch process only one time, and you should restart it only if it stops running.

> [!NOTE]
> Batch invoicing only runs for project contract lines that are configured by invoice schedules. A contract line with a fixed price billing method must have milestones configured. A project contract line with a time and material billing method will need a date-based invoice schedule set up. The same applies to a project-based contract line.     


[!INCLUDE[footer-include](../includes/footer-banner.md)]
