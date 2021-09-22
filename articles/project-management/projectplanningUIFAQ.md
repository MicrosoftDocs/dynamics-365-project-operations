---
title: Troubleshoot working in the Task grid 
description: This topic provides troubleshooting information needed when working in the Task grid.
author:  ruhercul
ms.date: 08/02/2021 
ms.topic: article
ms.product:
ms.reviewer: kfend
ms.author: ruhercul
---
Troubleshooting the Task grid
=============================

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_



Overview
--------

The task grid leveraged by Project Operations is a hosted iframe within
Dataverse. As a result, there are specific requirements that must be met to
ensure authentication and authorization functions correctly. This document will
outline the common issues that impact a user’s ability to render the grid or
manage tasks in the work breakdown structure (WBS).

Common issues can be grouped as follows:

1.  When navigating to the task grid, the tab is completely blank.

2.  When opening the project, the project does not load the UI is stuck on the
    spinner.
    
3.  Administration of privileges for **Project for the Web**.

4.  When attempting to create, update or delete a task, changes are not saved.

Issue \#1 – The task tab is completely blank
--------------------------------------------

### Mitigation \#1 – Enable Cookies

Project Operations requires that third-party cookies be enabled in order to
render the work breakdown structure. When third-party cookies aren't enabled,
instead of seeing tasks, you will see a blank page when you select
the **Tasks** tab on the **Project** page.

For Microsoft Edge or Google Chrome browsers, the following procedures outline
how to update your browser setting to enable third-party cookies.

#### **Microsoft Edge**

1.  Open your Edge browser.

2.  In the upper-right corner, select the **ellipsis** (...), and then
    select **Settings**.

3.  Under **Cookies and site permissions**, select **Cookies and site data**.

4.  Turn off **Block third-party cookies**.

#### **Google Chrome**

1.  Open your Chrome browser.

2.  In the upper-right corner, select the three vertical dots, and then
    select **Settings**.

3.  Under **Privacy and security**, select **Cookies and other site data**.

4.  Select **Allow all cookies**.

> If you block third-party cookies, all cookies and site data from other sites will be blocked, even if the site is allowed on your exceptions list.

### Mitigation \#2 – Validate PEX Endpoint has been correctly configured

Project Operations requires that a project parameter reference the PEX Endpoint.
This endpoint is required to communicate with the service used to render the
work breakdown structure. If the parameter isn't enabled, you will receive the
error, *"The project parameter is not valid"*. To update the PEX Endpooint do
the following:

1.  Add the PEX Endpoint field to the Project Parameters page.

2.  Identify the product type that you are using. This value is used when the
    PEX Endpoint is set. Upon retrieval, the product type is already defined in
    the PEX Endpoint. Keep that value.
3. Update the field with the following value: `https://project.microsoft.com/<lang>/?org=<cdsServer>#/taskgrid?projectId=<id>&type=2`.

| **Product type**                     | **Type parameter** |
|--------------------------------------|--------------------|
| Project for the Web on Default org   | type=0             |
| Project for the Web on CDS named org | type=1             |
| Project Operations                   | type=2             |

4.  Remove the field from the Project Parameters page.

Issue \#2 - The project does not load the UI is stuck on the spinner
--------------------------------------------------------------------

![Application user details.](media/popupsblocked.png)

### Mitigation \#1 - Enable Popups

When your project is stuck on the spinner it is possible popups are enabled.

**Microsoft Edge**

To enable popups either select the notification in the top right of the browser
and select “allow popups and redirects…..” from the specific dataverse
environment.
    
 ![Application reader.](media/enablepopups.png)

Alternatively, do the following:

-   Tap the menu … \> Settings \> Site permissions \>** Pop-ups** and redirects.

-   Toggle** Pop-ups** and redirects off for blocking** pop-ups,** or toggle on
    to** allow pop-ups** on your device.


Issue \#3 – Administration of Privileges for Project for the Web
----------------------------------------------------------------

Project Operations relies on an external scheduling service. The service
requires that a user have several roles assigned to read and write to entities
related to the work breakdown structure. These entities include project tasks,
resource assignments, and task dependencies. If a user can't render the work
breakdown structure when they navigate to the **Tasks** tab, it is probably
because **Project** for **Project Operations** has not been enabled. A user
might receive either a security role error, or an error related to a denial of
access.

### Mitigation \#1 – Validation of Application User and End User security roles

1. Go to **Setting > Security > Users > Application Users**.  

   ![Application reader.](media/applicationuser.jpg)
   
2. Double-click the application user record to verify the following:

 - The user has access to the project. This verification is typically done by ensuring that the user has **Project Manager** security role.
 - The Microsoft Project application user exists and is configured correctly.
 
3. If this user doesn't exist, you can create a new user record. Select **New Users**. Change the entry form to **Application User**, and then add the **Application ID**.

   ![Application user details.](media/applicationuserdetails.jpg)


Issue \#4 – Error when updating the work breakdown structure
---------------------------------------------------------------- 

When one or more updates are made to the work breakdown structure, the changes eventually fail and aren't saved. An error occurs in the schedule grid noting that “Recent change you’ve made couldn’t be saved.”

### Mitigation \#1 - Validate license assignment

1. Verify that the user has been assigned the correct license and that the service is enabled in the service plans details of the license.  
2. Verify that the user can open project.microsoft.com.
    
    
### Mitigation \#2 - Validation configuration of the Project Application User
1. Verify that the Project Application user has been created.
2. Apply the following security roles to the user:
  
  - Dataverse user or Base user
  - Project Operations System
  - Project System
  - Project Operations Dual Write System (This role is required if you are deploying the resource/non-stocked based scenario of Project Operations.)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
