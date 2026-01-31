---
title: Why can’t I delete records from the actuals entity?
description: This article provides information about why you can't delete records from the actuals entity.
author: JPBurrows
ms.custom: 
  - dyn365-projectservice
  - evergreen
ms.date:  07/07/2025
ms.update-cycle: 1095-days
ms.topic: concept-article
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---

# Why can’t I delete records from the Actuals entity?

[!include [banner](../includes/psa-now-project-operations.md)]

[!INCLUDE[cc-applies-to-psa-app-3.x](../includes/cc-applies-to-psa-app-3x.md)]

Project Service Automation (PSA) doesn't allow you to delete actuals because they serve as the source of truth for transactions that have financial implications to downstream systems, such as the general ledger. If actuals could be deleted, the integrity of the financial reporting transactions could be questioned. To establish an audit trail, customers should use journals to create compensating transactions.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
