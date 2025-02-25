---
title: Enable the Dynamics 365 Time Entry Mobile App (Preview)
description: Learn how system administrators can enable the new Microsoft Dynamics 365 Time Entry Mobile App (Preview) for users in their organization.
author: mohitmenon
ms.author: mohitmenon
ms.date: 02/25/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Enable the Dynamics 365 Time Entry Mobile App (Preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

This article explains how system administrators can enable the new Microsoft Dynamics 365 Time Entry Mobile App (Preview) for users in their organization. It also explains how users can open the app after it's enabled.

## For system administrators: Make the mobile app available to users

To make the Time Entry Mobile App available to users, ensure that the version of Dynamics 365 Project Operations in the environment is 4.124.0.0 or later. Then follow these steps.

1. Sign in to [Power Apps](https://make.powerapps.com/).
1. Use the environment picker to select the Project Operations environment where users require access to the app.
1. In the left pane, select **Solutions**.
1. On the **Solutions** page, select **All** above the grid to view all solutions.
1. In the grid, find **TimeEntryMobile**, and select the link in the **Display name** column. The **Objects** section of the **TimeEntryMobile** solution should be opened.
1. In the grid, find **Dynamics 365 Time Entry (Production Ready Preview)**, select the **Commands** button (three dots) for the record, and then select **Share**.
1. You enable the app for users by sharing it with them. To share the app with specific users, add the email ID of each user. To share the app with all users of the selected environment, enter *Everyone*, and then, in the dropdown list, select *Everyone in \<organization name\>*.
1. Select **Share** to enable the app for the selected users. The app is now available in each user's **Apps** section in Power Apps.

> [!NOTE]
> This procedure must be completed for each environment where the Time Entry Mobile App is being enabled. However, it's required only the first time that the app is shared with users.

## For system administrators: Modify or disable access to the mobile app

To modify or disable access to the Time Entry Mobile App for individual users, follow these steps.

1. Sign in to [Power Apps](https://make.powerapps.com/).
1. Use the environment picker to select the desired Project Operations environment.
1. In the left pane, select **Solutions**.
1. On the **Solutions** page, select **All** above the grid.
1. In the grid, find and select **TimeEntryMobile**.
1. Select the **Commands** button (three dots) for the record, and then select **Share**.
1. Select **Manage Access** to view a list of users that already have access to the app.
1. Select the users that require modifications, and then select **Assign app access**.
1. Use the dropdown menu to perform one of the following actions:

    - Switch the selected users' access from *User* to *Co-owner*, or from *Co-owner* to *User*.
    - Select **Remove Access** to take away the selected users' ability to view or use the app.

The next section explains how users (team members) can access the app after a system administrator shares it with them.

## For team members: Open the mobile app

After a system administrator shares the Time Entry Mobile App with you, follow these steps to open it.

1. On your mobile device, install the **Power Apps** mobile app from the [iOS apps store](https://apps.apple.com/app/power-apps/id1047318566) or the [Android Play Store](https://play.google.com/store/apps/details?id=com.microsoft.msapps).
1. Sign in to the app by using the same credentials as your Project Operations user.
1. Go to the **All apps** page, if it isn't already your default view.
1. If your system administrator shared the app with you, **Dynamics 365 Time Entry (Production Ready Preview)** should be listed. Select the app name or icon to open the app on your mobile device.

> [!NOTE]
> If you use multiple Project Operations environments, the Time Entry Mobile App must be shared with you in each environment. If **Dynamics 365 Time Entry (Production Ready Preview)** isn't listed on the **All apps** page, contact your system administrator.

Learn how to [use the app to create and review time entries](log-time-using-time-entry-mobile-app.md) while you're on the go.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
