---
title: Defaulting financial dimensions for project time entries
description: This topic provides information about how defaulting financial dimensions are applied to time entries.
author: stsporen
ms.date: 01/24/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: stsporen
---

# Defaulting financial dimensions for project time entries

[!include [banner](../includes/banner.md)]

When you use financial dimensions for project time entries, the default dimension value is assessed in the following order:

1. Resource
2. Project
3. Funding source

For example, if the default dimension is specified on a resource, the default value is applied over the default value that is specified for the project. Likewise, if the default dimension is specified on a project, the default value is applied over the default value that is specified for the funding source.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
