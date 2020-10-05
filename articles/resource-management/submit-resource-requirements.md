---
title: Submit a resource request
description: You can submit a generated resource requirement as a resource request. The request is then sent to a resource manager for fulfillment. 
author: ruhercul
manager: Annbe
ms.date: 10/04/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: ruhercul

---

# Submit a resource request

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

You can submit a generated resource requirement as a resource request. The request is then sent to a resource manager for fulfillment.

1. In Dynamcis 365 Project Operations, on the **Projects** page, select the **Team** tab to view a list bookable resources. 
2. Select the generic resource that has a resource requirement from the list, and then click **Submit Request**.

The request status of the generic team member will change to **Submitted**.

After the request is fulfilled by the resource manager, the generic resource will be replaced by a named resource if the resource manager fulfills the request with the booking of a named resource. Otherwise, the generic resource will remain on the team and the request status will change to **Needs Review**, if the resource manager has proposed a named resource.
