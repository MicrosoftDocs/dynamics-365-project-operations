---
# required metadata

title: Configure automated invoice creation
description: This topic provides information about hot to configure the system to generate invoices automatically.
author: rumant
manager: AnnBe
ms.date: 09/18/2020
ms.topic: article
ms.prod: 
ms.service: dynamics-365-customerservice
ms.technology: 

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: kfend
ms.search.scope: 
# ms.tgt_pltfrm: 
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Service industries
ms.author: suvaidya
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---

# Configure automated invoice creation

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Complete the following steps to configure an automated invoice run in Project operations.

1. Go to **Settings** \> **Batch jobs**.
2. Create a batch job, and name it **Project operations create invoices**. The name of the batch job must include the term "create invoices."
3. In the **Job type** field, select **None**. By default, the **Frequency Daily** and **Is Active** options are set to **Yes**.
4. Select **Run Workflow**. In the **Look Up Record** dialog box, you will see three workflows:

    - ProcessRunCaller
    - ProcessRunner
    - UpdateRoleUtilization

5. Select **ProcessRunCaller**, and then select **Add**.
6. In the next dialog box, select **OK**. A **Sleep** workflow is followed by a **Process** workflow.

    You can also select **ProcessRunner** in step 5. Then, when you select **OK**, a **Process** workflow is followed by a **Sleep** workflow.

The **ProcessRunCaller** and **ProcessRunner** workflows create invoices. **ProcessRunCaller** calls **ProcessRunner**. **ProcessRunner** is the workflow that actually creates the invoices. It goes through all the contract lines that invoices must be created for, and it creates invoices for those lines. To determine the contract lines that invoices must be created for, the job looks at invoice run dates for the contract lines. If contract lines that belong to one contract have the same invoice run date, the transactions are combined into one invoice that has two invoice lines. If there are no transactions to create invoices for, the job skips invoice creation.

After **ProcessRunner** has finished running, it calls **ProcessRunCaller**, provides the end time, and is closed. **ProcessRunCaller** then starts a timer that runs for 24 hours from the specified end time. At the end of the timer, **ProcessRunCaller** is closed.

The batch process job for creating invoices is a recurrent job. If this batch process is run many times, multiple instances of the job are created and cause errors. Therefore, you should start the batch process only one time, and you should restart it only if it stops running.

> [!NOTE]
> Batch invoicing only runs for project contract lines that are configured by invoice schedules. A contract line with a fixed price billing method must have milestones configured. A project contract line with a time and material billing method will need a date-based invoice schedule set up. The same applies to a project-based contract line.     
