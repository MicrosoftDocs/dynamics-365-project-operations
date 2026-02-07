---
title: Troubleshoot working in the Task grid
description: Learn how to troubleshoot common issues in the Dynamics 365 Task grid, including empty tabs, stuck UI, and unsaved changes. Follow step-by-step solutions.
author: abriccetti
ms.date: 02/05/2026
ms.topic: troubleshooting
ms.product:
ms.reviewer: johnmichalak
ms.author: abriccetti
ms.custom:
  - bap-template
  - sfi-image-nochange
---

# Troubleshoot working in the Task grid

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core, Project for the web_

Dynamics 365 Project Operations uses the Task grid as a hosted iframe within Microsoft Dataverse. Because of this architecture, you need to meet specific requirements to ensure authentication and authorization work correctly. This article outlines common issues that can affect your ability to render the grid or manage tasks in the work breakdown structure (WBS).

Common problems include:

- The **Task** tab on the Task grid is empty.
- When you open the project, the project doesn't load and the user interface (UI) is stuck on the spinner.
- Administration of privileges for **Project for the Web**.
- Changes aren't saved when you create, update, or delete a task.

## Issue: The Task tab is empty

### Mitigation 1: Enable cookies

Project Operations requires that you enable third-party cookies to render the work breakdown structure. When you don't enable third-party cookies, you see a blank page instead of tasks when you select the **Tasks** tab on the **Project** page.

For Microsoft Edge or Google Chrome browsers, the following procedures outline how to update your browser setting to enable third-party cookies.

#### Microsoft Edge

1. Open your Edge browser.
1. In the upper-right corner, select the **ellipsis** (...), and then select **Settings**.
1. Under **Cookies and site permissions**, select **Cookies and site data**.
1. Turn off **Block third-party cookies**.
1. Refresh your browser.

#### Google Chrome

1. Open your Chrome browser.
1. In the upper-right corner, select the three vertical dots, and then select **Settings**.
1. Under **Privacy and security**, select **Cookies and other site data**.
1. Select **Allow all cookies**.
1. Refresh your browser.

> [!NOTE]
> If you block third-party cookies, you block all cookies and site data from other sites, even if you allow the site on your exceptions list.

### Mitigation 2: Validate the PEX Endpoint is correctly configured

Project Operations requires that a project parameter reference the PEX Endpoint. This endpoint is required to communicate with the service that renders the work breakdown structure. If the parameter isn't enabled, you receive the error, "The project parameter isn't valid." To update the PEX Endpoint, complete the following steps.

1. Add the **PEX Endpoint** field to the **Project Parameters** page.
1. Identify the product type that you're using. This value is used when the PEX Endpoint is set. Upon retrieval, the product type is already defined in the PEX Endpoint. Keep that value.
1. Update the field with the following value: `https://project.microsoft.com/<lang>/?org=<cdsServer>&clientType=ProjectOperations#/taskgrid?projectId=<id>&type=2`. The following table provides the type parameter that should be used based on the product type.

      | **Product type**                     | **Type parameter** |
      |--------------------------------------|--------------------|
      | Project for the Web on Default org   | type=0             |
      | Project for the Web on CDS named org | type=1             |
      | Project Operations                   | type=2             |

1. Remove the field from the **Project Parameters** page.

### Mitigation 3: Sign in to project.microsoft.com

In your browser, open a new tab, go to project.microsoft.com, and sign in with the user role that you're using to access Project Operations. Only one user should be signed in to a Microsoft product in the browser. The "login.microsoftonline.com refused to connect" error message most often occurs when more than one user is signed in, as shown in the following illustration.

:::image type="content" source="media/MULTIPLE_USERS_LOGGED_IN.png" alt-text="Screenshot of the Pick an account sign-in page showing that two users are signed in.":::

## Issue: The project doesn't load and the UI is stuck on the spinner

For authentication, you must enable pop-ups for the Task grid to load. If you don't enable pop-ups, the screen is stuck on the loading spinner. The following graphic shows the URL with a blocked pop-up label in the address bar, which results in the spinner getting stuck trying to load the page.

   :::image type="content" source="media/popupsblocked.png" alt-text="Screenshot of the stuck spinner and pop-up block.":::

### Mitigation 1: Enable pop-ups

When your project is stuck on the spinner, it's possible that pop-ups aren't enabled.

#### Microsoft Edge

Enable pop-ups in your Edge browser by using one of the following methods.

1. In your Edge browser, select the notification in the upper-right of the browser.
1. Select **Always allow popups and redirects from** the specific Dataverse environment.

     :::image type="content" source="media/enablepopups.png" alt-text="Screenshot of the pop-ups blocked window.":::

Alternatively, complete the following steps.

1. Open your Edge browser.
1. In the upper-right corner, select the **ellipsis** (...), and then select **Settings** > **Site permissions** > **Pop-ups and redirects**.
1. Toggle **Pop-ups and redirects** off to block pop-ups, or toggle on to allow pop-ups on your device.
1. After you enable pop-ups, refresh your browser.

#### Google Chrome

1. Open your Chrome browser.
1. Navigate to a page where pop-ups are blocked.
1. In the address bar, select **Pop-up blocked**.
1. Select the link for the pop-up you want to see.
1. After you enable pop-ups, refresh your browser.

> [!NOTE]
> To always see pop-ups for the site, select **Always allow pop-ups and redirects from [site]** and then select **Done**.

## Issue 3: Administration of privileges for Project for the Web

Project Operations relies on an external scheduling service. The service requires that a user have several roles assigned that allow them to read and write to entities related to the WBS. These entities include project tasks, resource assignments, and task dependencies. If a user can't render the WBS when they go to the **Tasks** tab, it's probably because **Project** for **Project Operations** isn't enabled. A user might receive either a security role error, or an error related to a denial of access.

### Mitigation 1: Validate the application user and end-user security roles

1. Go to **Setting** > **Security** > **Users** > **Application Users**.  

   :::image type="content" source="media/applicationuser.jpg" alt-text="Screenshot of the Application reader.":::

1. Double-click the application user record to verify:

     - The user has access to the project. You can check this by verifying that the user has the **Project Manager** security role.
     - The Microsoft Project application user exists and is configured correctly.

1. If this user doesn't exist, create a new user record.
1. Select **New Users**, change the entry form to **Application User**, and then add the **Application ID**.

   :::image type="content" source="media/applicationuserdetails.jpg" alt-text="Screenshot of the Application user details.":::

## Issue 4: Changes aren't saved when you create, update, or delete a task

When you make one or more updates to the WBS, the changes fail and aren't saved. An error occurs in the schedule grid with a message that says, "Recent change you made couldn't be saved."

### Mitigation 1: Validate the license assignment

1. Verify that the user is assigned the correct license and that the service is enabled in the service plans details of the license.  
1. Verify that the user can open **project.microsoft.com**.

### Mitigation 2: Validate configuration of the Project application user

1. Verify that you create the Project application user.
1. Apply the following security roles to the user:
  
- Dataverse User or Base User
- Project Operations System
- Project System
- Project Operations Dual-write System. This role is required for the Project Operations Integrated with ERP based deployment scenario of Project Operations.

## Issue 5: Permission error while updating a project

While working on a project, an issue might occur. The PSS Error Log displays a message indicating a permission access problem for a user when saving a record. This error can occur during actions like Project Copy, Project Convert, Project Import, or while working on the Task Grid, and so on.

### Mitigation 1: Update the user's permissions for the specific entity

In most cases, the error suggests that the user lacks the necessary permissions to perform specific operations, such as read or write, on an entity record.

1. First, examine the error message to identify the entity name and user name. If the error displays only the user ID, get the username by using this web API: **\<orgurl\>/api/data/v9.2/systemusers(\<Principal/User Id from the error message\>)?$select=fullname,firstname,lastname,domainname,internalemailaddress,windowsliveid**
1. If the username is either "Microsoft Project" or "Microsoft Portfolios," it indicates a permission problem with the Project Operations app user. This user is a built-in user for the integration between Project Online and the customer's organization.

**If the user is the built-in app user:**

1. Make sure the built-in app user is assigned all out-of-the-box (OOB) roles. For more information, see [Validation Configuration of the Project Application User](https://aka.ms/po-tasks-grid-setup-documentation). With each update of Project Operations, security roles are reassigned to this user automatically. However, problems can occur if you manually remove the roles from this app user.
1. If the app user already has all the OOB roles, check any customer plugins that might be triggering operations on extra entities. You might need to change the customer or partner plugin or add extra roles and privileges to the app user.

**If the user is a normal user:**

1. Check the customization or plugin responsible for triggering the CRUD operations on the entity, operating under the user context. You can either use the system service in your plugin or assign more roles and privileges to the user.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
