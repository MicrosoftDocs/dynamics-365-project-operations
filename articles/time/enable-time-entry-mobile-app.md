---
title: How to enable Dynamics 365 Time Entry Mobile App (Preview)
description: This article provides information for system administrators to enable the new Time Entry Mobile App (Preview) for users in their organization.
author: mohitmenon
ms.author: mohitmenon
ms.date: 02/21/2025
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Enable Dynamics 365 Time Entry Mobile App (Preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

## Making the app available to end users (System Administrator Instructions)

To share this app with end users, ensure the Project Operations version on the environment is 4.124.0.0 or higher. Next, complete the following steps (for system administrators):

1. Log in to [Power Apps](https://make.powerapps.com/) and select the Project Operations environment where users require access to the mobile app (from the environment drop-down).
2. Navigate to **Solutions** from the menu on the left. Select **“All”** solutions.
3. Look for **TimeEntryMobile** in this list. Click the solution hyperlink.
4. Clicking this solution should navigate you to the **Objects** section of **TimeEntryMobile**.
5. **Dynamics 365 Time Entry (Production Ready Preview)** should be part of the list.
6. Select the **overflow** icon _(three dots)_ for this record and hit **Share**.
7. The app can either be shared with **individual users** by adding their email IDs OR with **all users** of that environment by typing in **“Everyone”** and selecting _“Everyone in \<organisation name\>”_ from the drop-down list. Hit **Share** after selecting the set of users to enable this app for.
8. Completing this step makes the Dynamics 365 Time Entry app available to these users under their **“Apps” section** within Power Apps.

> [!NOTE]
> This step must be **completed for each environment** on which the Time Entry Mobile app is being enabled and is **only required the first time** the app is shared with end users.

## Modify or Disable access to the mobile app

In order to upgrade or disable access to the Dynamics 365 Time Entry (Preview) mobile app from individual users, follow these steps:

1. Once again, login to [Power Apps](https://make.powerapps.com/) and select the desired Project Operations environment.
2. Navigate back to **Solutions** > **All Solutions** and select **TimeEntryMobile**.
3. Click the **overflow** icon _(three dots)_ for the Dynamics 365 Time Entry record and click **Share**.
4. Select **Manage Access**. This step should display a list of users who already have access to the app.
5. Select the users that require modifications and select the **Assign** **app access** option.
6. The drop-down allows you to either switch access from _User_ to _Co-owner_ (and vice versa) OR **Remove Access**, taking away their ability to view or use the app.

The next section explains how end users (team members) can access the mobile app, once it has been shared with them by their system administrators.

## Launching the Dynamics 365 Time Entry (Preview) mobile app (for Team Members)

Once the system administrator has shared the app with end users, the app can be launched by following these steps:

1. Install the **Power Apps mobile app** on your mobile device from the [iOS apps store](https://apps.apple.com/us/app/power-apps/id1047318566) or the [Android Play Store](https://play.google.com/store/apps/details?id=com.microsoft.msapps&hl=en).
2. Log in to the app using the same credentials as your Project Operations user.
3. Navigate to **All apps** (if All Apps isn't your default view already).
4. The **Dynamics 365 Time Entry (Production Ready Preview)** app should be visible if the app was shared by your administrator.
5. Tap the app name or icon to launch this on your mobile device.

> [!NOTE]
> If you're using multiple environments of Project Operations, ensure that the mobile app is **shared with you for every environment**. Reach out to your System Administrator if the Dynamics 365 Time Entry (Production Ready Preview) app is not visible under **All apps**.

Please read the next section to learn more on how to [use the mobile app to create and review time entries](log-time-using-time-entry-mobile-app.md) on the go.


