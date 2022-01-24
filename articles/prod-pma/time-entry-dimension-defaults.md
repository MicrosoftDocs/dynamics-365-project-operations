---
title: Project time entry dimension defaults
description: This topic provides information about how defaulting financial dimensions are applied to time entries.
author: stsporen
ms.date: 01/24/2022
ms.topic: article
ms.reviewer: kfend 
ms.author: stsporen
---

# Project time entry dimension defaults

[!include [banner](../includes/banner.md)]


## Defaulting financial dimensions for project time entries
When you use financial dimensions for project time entries, the default dimension value is assessed in the following order:

1. Resource.
2. Project.
3. Funding source.

For example, if the default dimension is specified on a resource, the default is applied over a default that's specified on the project. Similarly, a default project dimension is applied over the default that is specified in the funding source.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
