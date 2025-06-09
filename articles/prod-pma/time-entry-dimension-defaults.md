---
title: Defaulting financial dimensions for project time entries
description: This article provides information about how defaulting financial dimensions are applied to time entries.
author: mohitmenon
ms.author: mohitmenon
ms.date: 05/22/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Defaulting financial dimensions for project time entries

[!include [banner](../includes/banner.md)]

When you use financial dimensions for project time entries, the default dimension value is assessed in the following order:

1. Resource
2. Project
3. Funding source

For example, if the default dimension is specified on a resource, the default value is applied over the default value that is specified for the project. Likewise, if the default dimension is specified on a project, the default value is applied over the default value that is specified for the funding source.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
