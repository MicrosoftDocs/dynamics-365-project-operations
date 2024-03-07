---
title: Expense overview
description: This article provides information about the Expense functionality in Project Operations. 
author: stsporen
ms.date: 10/06/2020
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: stsporen

---

# Expense home page

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_


Dynamics 365 Project Operations supports the ability to process expenses. Expense processing occurs with or without projects by using a customizable workflow of policies, transaction categories, and approvals.

In Project Operations, there are two supported deployment models for Expense: 

- **Full**: Full deployment is available for **Project Operations for resource/non-stocked based scenarios** or **Project Operations for production order-based scenarios**.
- **Basic**: Basic deployment is available for **Project Operations for resource/non-stocked based scenarios** and **Lite deployment – deal to proforma invoicing**.

## Full 
Full Expense deployment provides a complete policy enforcement that includes the ability to create policies, such as:

  - Expense category limits
  - Travel
  - Per diem
  - Credit card imports
  - Receipt optical character recognition

## Basic 
Basic Expense deployment scenario only allows you to record basic expenses against a project. 

For more information, see [Expense entry (lite)](basic-expense.md)

## Determine your Expense deployment
To determine if you're running the Basic Expense management deployment, verify that the address URL ends with **.crm.dynamics.com**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
