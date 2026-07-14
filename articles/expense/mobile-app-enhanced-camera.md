---
title: Enhanced camera control for Expense Mobile
description: Learn how to enable and use enhanced camera control in the Expense Mobile app to simplify receipt capture and uploads.
author: ajitchandran
ms.author: ajitchandran
ms.date: 04/27/2026
ms.topic: how-to
ms.custom:
  - bap-template
ms.reviewer: johnmichalak
---

# Enhanced camera control for Expense Mobile

[!INCLUDE [banner](../includes/banner.md)]

_**Applies to:** Project Operations Integrated with ERP, Project Operations for manufacturing-based scenarios_

## Introduction

The **Enhanced camera control for Expense Mobile** feature improves the receipt capture experience in the Expense Mobile canvas app. It provides a configurable option to bypass the default camera-first workflow and instead offer more flexible ways to add receipts when creating expenses.

This enhancement introduces improved camera capabilities for more reliable receipt capture and enables you to upload or reuse receipts more efficiently while on the go.

When you enable the feature, you can choose how you want to add receipts instead of using the existing camera control within the app that has image size limitations.

When you enable **Enhanced camera control**:

- You can upload receipts directly by using the **Attachments (file picker)** control.
- You can select from **existing, unattached receipts**.
- The expense creation flow skips the mandatory camera-first screen.

When you disable the feature:

- The app retains the original **camera control** which tries to capture images from within the app. As this control has image size limitations, the images captured aren't high resolution.
- You must capture a receipt by using the camera control from within the app.

## Prerequisites

Before enabling this feature, make sure you meet the following requirements:

- Access to the **Feature management** workspace in Finance & Operations.
- **Expense Mobile app version:** 3.3.3383.1
- Supported **Dynamics 365 Finance versions**:
  - 10.0.45 (10.0.2345.206 or later)
  - 10.0.46 (10.0.2428.152 or later)
  - 10.0.47 (10.0.2527.84 or later)

## Enable enhanced camera control

To enable the enhanced camera experience, follow these steps:

1. In **Finance**, go to **Feature management**.
1. Search for **Enhanced camera control for expense mobile**.
1. Select the feature, and then select **Enable**.

## Use enhanced camera control in Expense Mobile

After you enable the **Enhanced camera control for expense mobile** feature, follow these steps:

1. Open the **Expense Mobile** app.
1. Go to the **Receipts** tab.
1. Select the **+ (Add)** button.

You can now choose from the following options:

- Capture a receipt by using the device camera.
- Select previously captured images from your device.
- Upload supported file types by using the attachments control.

You can also access this experience from within the expense line when you select the **+ (Add)** button. The app replaces the camera capture screen.

This flexible workflow reduces friction and makes it easier to manage receipts during expense creation.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
