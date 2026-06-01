---
title: Defaulting financial dimensions for project time entries
description: Learn how defaulting financial dimensions are applied to project time entries, including the order of priority for resources, projects, and funding sources.
author: mohitmenon
ms.author: mohitmenon
ms.date: 02/06/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Default financial dimensions for project time entries

[!INCLUDE [banner](../includes/banner.md)]

When you use financial dimensions for project time entries, the system checks the default dimension value in the following order:

1. Resource
1. Project
1. Funding source

For example, if you specify the default dimension on a resource, that default value takes precedence over the default value that you specify for the project. Similarly, if you specify the default dimension on a project, that default value takes precedence over the default value that you specify for the funding source.

[!INCLUDE [footer-include](../includes/footer-banner.md)]
