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

_**Applies to:** Project Operations Integrated with ERP, Project Operations for manufacturing-based scenarios_

## Introduction

The **Enhanced camera control for Expense Mobile** feature improves the receipt capture experience in the Expense Mobile canvas app. It provides a configurable option to bypass the default camera-first workflow and instead offer more flexible ways to add receipts when creating expenses.

This enhancement introduces improved camera capabilities for more reliable receipt capture and enables users to upload or reuse receipts more efficiently while on the go.

When the feature is enabled, users can choose how they want to add receipts instead of using the existing camera control within the app which has image size limitations.

## What this feature does

When **Enhanced camera control** is enabled:

- Users can upload receipts directly using the **Attachments (file picker)** control.
- Users can select from **existing, unattached receipts**.
- The expense creation flow skips the mandatory camera-first screen.

When the feature is disabled:

- The app retains the original **camera control** which will try to capture images from within the app. As this control has image size limitations, the images captured are not of great resolution.
- Users must capture a receipt using the camera control from within the app.

## Prerequisites

Before enabling this feature, ensure the following requirements are met:

- Access to the **Feature management** workspace in Finance & Operations.
- **Expense Mobile app version:** 3.3.3383.1
- Supported **Dynamics 365 Finance & Operations versions**:
  - 10.0.45 (10.0.2345.206 or later)
  - 10.0.46 (10.0.2428.152 or later)
  - 10.0.47 (10.0.2527.84 or later)

## Enable enhanced camera control

Follow these steps to enable the enhanced camera experience:

1. In **Finance & Operations**, go to **Feature management**.
2. Search for **Enhanced camera control for expense mobile**.
3. Select the feature, and then click **Enable**.

## Use enhanced camera control in Expense Mobile

After the feature is enabled:

1. Open the **Expense Mobile** app.
2. Go to the **Receipts** tab.
3. Select the **+ (Add)** button.

You can now choose from the following options:
- Capture a receipt using the device camera.
- Select previously captured images from your device.
- Upload supported file types using the attachments control.

This experience is also available from within the expense line when you click the **+ (Add)** button. The camera capture screen is replaced through the app. 

This flexible workflow reduces friction and makes it easier to manage receipts during expense creation.

## Summary

Enhanced camera control for Expense Mobile modernizes the receipt capture experience by allowing users to upload or reuse receipts without being forced into a camera-first flow. By enabling this feature through Feature management in Finance & Operations, organizations can provide a more efficient and user-friendly expense submission experience.
