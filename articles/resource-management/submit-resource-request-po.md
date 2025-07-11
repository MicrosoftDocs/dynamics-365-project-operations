---
title: Submitting a resource request
description: This article provides information about submitting a request for a project resource.
ms.custom: 
  - dyn365-projectservice
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: how-to
author: JohnPBurrows
ms.author: abriccetti
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---
# Submitting a resource request

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_

You can submit a generated resource requirement as a resource request. The request is then sent to a Resource Manager for fulfillment.

1. In Project Operations, on the **Projects** page, click the **Team** tab to view a list bookable resources. 
2. Select the generic resource that has a resource requirement from the list and then click **Submit Request**.

![Submitting a resource request.](media/submit-request.png)

The request status of the generic team member changes to **Submitted**.

After the request is fulfilled by the Resource Manager, the generic resource is replaced by a named resource if the Resource Manager fulfills the request with the booking of a named resource. Otherwise, the generic resource remains on the team and the request status changes to **Needs Review**, if the Resource Manager has proposed a named resource.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
