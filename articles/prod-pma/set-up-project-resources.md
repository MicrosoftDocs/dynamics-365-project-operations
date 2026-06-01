---
title: Set up project resources
description: This article provides information about setting up or requesting project resources.
author: tulsij
ms.author: dishantpopli
ms.date: 01/23/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898

---

# Set up project resources

[!include [banner](../includes/banner.md)]

You must set up a calendar and associate it with an employee or a worker. Use the calendar to schedule the project and the working time of the resources that you reserve for the project. During calendar setup, project managers can do resource leveling as part of resource optimization. Based on the calendar schedule, you can put restrictions on resources. Set up a calendar on the **Calendars** page.

When you set up a worker as a project resource, select from workers who work in the company that you're setting up resources for. Alternatively, select workers from other companies in your organization. These workers are known as intercompany resources.

The following procedures explain how to set up a worker as a project resource in your company and how to set up an intercompany project resource.

## Set up a worker as a project resource

1. On the **Workers** page, in the **Workers** list, select the worker that you're adding as a project resource, and open the worker record.
1. On the Action Pane, select **Project** &gt; **Setup** &gt; **Project setup**.
1. Select a calendar, and then close the page.

You can also specify default projects for a resource as a type of pre-assignment. Use pre-assignments when the resource manager or project manager knows which projects the resource works on in advance. A pre-assignment can also be based on the request of a project sponsor or customer. To pre-assign a project, on the **Assign projects** page, on the **Projects** tab, in the **Remaining projects** list, select the appropriate project.

## Set up an intercompany resource

When you set up a worker as an intercompany resource, you must complete the setup in both the lending company and the borrowing company.

### In the lending company

1. In Finance, verify that the lending company is selected, and then complete the procedure in the previous section, "Set up a worker as a project resource."
1. On **Intercompany accounting**, select **New**.
1. In the **Legal entity ID** field, select the lending company. Fill in the remaining fields as appropriate, and then select **Save**.
1. On **Transfer price**, select **New**.
1. In the **Borrowing legal entity** field, select the appropriate company.
1. To lend the borrowing company only the resource that you created at the beginning of this section, in the **Resource** field, select the name of the resource that you created. To make all resources in the lending company available to the borrowing company, leave the **Resource** field blank.
1. On **Project management and accounting parameters**, on the **Intercompany** tab, set the **Enable intercompany resource scheduling and timesheets** option to **Yes**.

### In the borrowing company

- On the **Resources list** page, in the search filter, enter the name of the resource that you created for the lending company, to verify that the name is included in the resource list for the borrowing company.

## Request project resources

The project resource scheduling functionality only lets resource managers distribute staffed resources on engagements or projects. To enable this functionality, complete the following tasks, or verify that they are completed:

- Set up number sequences.
- Set up project management and accounting workflows.
- Enable resource request workflows.

After completing the preceding tasks, you can complete the following tasks as needed:

- Create a resource request from a soft-booked staffed resource.
- Monitor resource requests.
- Fulfill resource requests.
- Request a staffed resource from a WBS.
- Book resources to a project without having a request for a staffed resource.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
