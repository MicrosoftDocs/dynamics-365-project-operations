---
title: Dynamics 365 expense management mobile app FAQ
description: This article provides answers to frequently asked questions about the Dynamics 365 expense management mobile app.
author: mukumarm
ms.date: 02/04/2025
ms.topic: conceptual
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---

# Expense management mobile app FAQ

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Project Operations for stocked/production-based scenarios._

This article provides answers to frequently asked questions about the Dynamics 365 expense management mobile app. It also describes known issues that affect the app and explains how to work around them.

## Which versions of Microsoft Dynamics 365 Finance support the Expense management mobile app?

The Expense management mobile app requires Dynamics 365 Finance version - 10.0.38 - 10.0.1777.180 or later, 10.0.39 - 10.0.1860.99 or later.

## Which platforms and mobile devices are supported?

The Expense management mobile app runs within the Power Apps mobile app. All platforms that the Power Apps mobile app supports can also run the Expense management mobile app. For more information, see [System requirements, limits, and configuration values for Power Apps](/power-apps/limits-and-config).

## Does the Dynamics 365 expense management mobile app support offline mode?

No, the Expense management mobile app doesn't currently support offline mode.

## Does the Dynamics 365 expense management mobile app support itemization, per diem functionality, and guest functionality?

Yes, the Expense management mobile app supports itemization, per diem functionality, and guest functionality.

## Does the Dynamics 365 expense management mobile app require another license?

No, there are no other licensing costs for the new Expense management mobile app. Its license is covered under the **Team member** license. Users who have a **Team member** license can use this app.

## Does the OCR feature work with cloud hosted environments?

No, the OCR service works only with sandbox or production environments.

## Does the Dynamics 365 expense management mobile app can be used for capturing expenses without projects?

Yes, Dynamics 365 expense management mobile app can be used without projects.

## Why am I getting the warning "Your language preference on Dynamics 365 differs from your mobile app preference, which may cause data issues and an inconsistent experience. To ensure a seamless experience, use the same language on both platforms"?

Having different language preference settings on the Dynamics 365 web application and mobile devices can lead to data and language inconsistencies when your mobile date/time/number format is different from your web application. For example, commas and decimal points when entering numerical values can vary across geographies, and can lead to data entered in a certain format in the mobile application but interpreted and stored in another format on the web application. To avoid this issue, it's recommended you change your individual user preferences so that the language and date, time, and number format are the same on both devices.

## Why am I unable to see my expense reports for a specific legal entity?

This issue can sometimes occur when the legal entity selection is typed in instead of being selected from the drop-down. Navigate to **Settings -> User Options -> Preferences** within the Dynamics 365 web application and select the legal entity from the drop-down.

## Where can I go to discuss the app with the community and submit suggestions to Microsoft?

The **Mobile Experiences** channel within the [Project Operations Discussions](https://teams.microsoft.com/l/team/19%3A8a60b9a0136a4879aeb618021cdcdc91%40thread.tacv2/conversations?groupId=b781f78d-32f2-432f-b1fa-265d8259f9be&tenantId=72f988bf-86f1-41af-91ab-2d7cd011db47) Microsoft Teams channel is a great place to go if you want to exchange tips, ask questions, or submit suggestions for improvement. Channel participants include Microsoft partners, customers, experts, and employees.
