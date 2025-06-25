---
title: What's new 2021 wave 2 early access - Project Operations lite deployment
description: This article provides information about the features available in the 2021 wave 2 early access release of Project Operations lite deployment.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new 2021 wave 2 early access - Project Operations lite deployment

_Applies To: Core deployment - deal to proforma invoicing._

This article applies to the following Dynamics 365 Project Operations components and versions:

- Project Operations on Dataverse environment version 4.23.0.4

The release is only applied when an environment is [opted into Early Access](/power-platform/admin/opt-in-early-access-updates#how-to-enable-early-access-updates).

## Features included in this release

[Subcontract management](/dynamics365/project-operations/pro/subcontracting/managing-subcontracts-overview) - This feature provides better visibility and control over all aspects of work on a project. The preview of subcontract management includes the following capabilities:

- A project manager can create a subcontract with a vendor. By default, the price lists that are attached to the vendor record are used for the subcontract. The vendor account has a relationship type of **Vendor** or **Supplier**.
- A project manager can itemize all of the purchases as line items on the subcontract. Subcontract lines can be for time, expenses, or products. The transaction class of the subcontract line determines what the line is for.
- The vendor account manager and the project manager can iterate over the subcontract. Pricing can be adjusted in the purchase price lists that are attached to the subcontract.
- During the process, if the subcontract line is for time, the vendor account manager can associate vendor contacts with each subcontract line. This association provides information to the project manager who is working on the subcontract. When a vendor contact is associated with a subcontract line, the system automatically creates a bookable resource from the contact, if a bookable resource doesn't already exist.
- The billing method on each subcontract line can be fixed-price or time and material. For fixed-price subcontract lines, a milestone-based invoice schedule is set up.
