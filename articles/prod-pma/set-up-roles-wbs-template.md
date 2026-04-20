---
title: Set up roles on Work breakdown structure templates
description: Learn about setting up role information on Work breakdown structure templates.
author: Yowelle
ms.date: 01/30/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: johnmichalak
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: andchoi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0

---

# Set up roles on Work breakdown structure templates

[!include [banner](../includes/banner.md)]

Project managers set up Work breakdown structure (WBS) templates that they apply when they create a WBS for new projects. Project managers add roles when they create a template. Use the following procedure to assign a role to a WBS template.

1. Select **Project management and accounting** > **Setup** > **Projects** > **Work breakdown structure templates**.
1. Select **Details** for a selected WBS template.
1. Select a task in the list, and then, in the **Role** field, select a role to assign to the task.

## Work with a WBS

You can create a new WBS, or you can copy a WBS from an existing WBS template. A project manager can easily manage the resources by assigning roles to new tasks on the WBS. You can replace roles either after acquiring a resource or after identifying a confirmed resource to work on the task. This flexibility lets project managers perform the following tasks:

- Identify the number of resources that are required for WBS work packages.
- Estimate project costs.
- Determine a preliminary budget.
- Estimate activity duration, based on roles and resources.
- Develop some project management plans, based on the available project information.

The WBS includes additional options to better use the resourcing functionality.

| Option | Description |
|---|---|
| Resource assignments | View the assigned resources, dates, number of hours, and booking type for tasks on the WBS. |
| Auto generate team | Automatically add planned resources by using roles that are associated with a task. Finance automatically suggests planned resources by using multi-criteria decision analysis that is based on roles. After you set the roles and effort (hours) for the tasks in a WBS, and after you release the structure, select **Auto generate team**. The required number of planned resources is added to the WBS and the **Project and team scheduling** tab. |
| Resource (drop-down list) | On the **Launch resource assignment** page, select resources to hard-book or soft-book, based on the specified duration. Adjust the view settings to see and set the duration of resource activities. Select and assign resources at the work package level by using the following options: <ul><li>**Accept** – Confirm changes to the resource that is assigned to a task.</li><li>**Cancel** – Cancel changes to the resource that is assigned to a task.</li><li>**Assign automatically** – An available staffed resource that has a matching role is automatically selected and assigned to the selected task.</li></ul> |

1. On the **All projects** page, select the **XYZ Upgrade Phase 2** project.
1. Select **Plan** > **Activities** > **Work breakdown structure**.
1. Select **New** to add the following level-one activities to the WBS:

    - Initiating
    - Planning
    - Executing
    - Monitoring and Control
    - Close

1. Set the dates and effort (hours), as shown in the following illustration.

    :::image type="content" source="./media/projectresourcing10.jpg" alt-text="Screenshot of setting the dates and effort for project tasks.":::

1. Select the **Initiating** task line, and then, in the **Role** field, select **Senior Project Manager**.
1. Select **Publish**.
1. On the same line, in the **Resource** field, select **Daniel Goldschmidt**, and then select **Accept**.
1. Select the **Planning** task line, and then, in the **Role** field, select **Business analyst**.
1. Select **Publish**, and then select **Auto generate team**.
1. In the message box that appears, select **Yes**.
1. In the **Resource** field, verify that the value is **Business analyst 1**.
1. For the **Business analyst 1** resource, open the lookup, and select **Launch resource assignments**. Then select a worker for the task.
1. Select **Soft assign** &gt; **Full capacity**.

    > [!NOTE]
    > You don't receive a warning that the specified resource is now 2, because the number of resources remains 1.

1. On the **Work breakdown structure** page, validate the resource assignment on the WBS, and then select **Save**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
