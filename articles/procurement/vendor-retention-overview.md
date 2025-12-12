---
title: Vendor retention overview
description: This article provides an overview of vendor retention capabilities.
author: mukumarm
ms.author: mukumarm
ms.date: 05/22/2024
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Vendor retention overview

_**Applies To:** Project Operations Integrated with ERP_

Your organization might want to retain a portion of payments to vendors who work on projects for your org. For example, before you pay your vendor, you might want to make sure that the items and services they provided meet your expectations.

When you negotiate purchases for projects with vendors, you can specify the vendor retention terms that include the percentage or amount to retain. As the vendor delivers items and services, you deduct the specified retention percentage or amount from your payment to the vendor. When the project is complete, or reaches an interim stage as specified in the vendor contract, you release the retained amount and create a payment to the vendor.

## Vendor retention example

The following example shows how a percentage of a vendor invoice amount is retained based on the percentage that is complete for a project.

Contoso Robotics USA has contracted with the vendor Fabrikam to deliver 100 hours of training for the equipment renewal project. The total contract value is USD 30,000 with an agreed purchase price of USD 300 per hour.

Training will be delivered in three phases with the following schedule:

- Phase 1: 50 hours, or 50 percent of the project
- Phase 2: 30 hours, or 80 percent of the project in total
- Phase 3: 20 hours, or 100 percent of the project

The following table lists the retention terms.

| **Percentage of units delivered** | **Percentage to retain** | **Percentage to release** |
| --- | --- | --- |
| 50% | 20% | 0% |
| 80% | 10% | 10% |
| 100% | 0% | 100% |

The transactions result in the following amounts:

- Phase 1:
  - The amount payable is 50 x 300, or 15,000.
  - 20 percent of the amount, or 3,000, is retained and will be released at a later stage.
  - The amount that is paid to the vendor is 12,000.
- Phase 2:
  - The amount payable is 30 x 300, or 9,000.
  - 10 percent of the amount, or 900, is retained.
  - 10 percent of the 3,000 that was retained in Phase 1, or 300, is released.
  - The amount that is paid to the vendor is 8,400. This amount is 9,000 less the 900 retention plus the 300 that was released from the Phase 1 retention.
- Phase 3:
  - The amount payable is 20 x 300, or 6,000.
  - No amount is retained.
  - The amount that is released is 3,600. This amount consists of the 3,000 that was retained in Phase 1, less the 300 from Phase 1 that was released in Phase 2, plus the 900 that was retained in Phase 2.
  - The amount that is paid to the vendor is 9,600. This amount consists of the retained amount of 3,600 plus the 6,000 for completion of Phase 3.

The total amount paid to the vendor after the three phases are complete is 30,000, which is the total amount of the purchase order (15,000 + 9,000 + 6,000).
