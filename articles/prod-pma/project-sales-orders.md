---
title: Project sales orders for time and material projects
description: Learn how to create project-based sales orders for time and material projects. Follow step-by-step instructions to manage funding sources and streamline your workflow.
author: mukumarm
ms.author: mukumarm
ms.date: 02/06/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.validFrom: 2019-04-05
ms.dyn365.ops.version: AX 10.0.2

---

# Project sales orders for time and material projects

[!include[banner](../includes/banner.md)]

This article describes how to create a sales order for a project. You can only create sales orders for projects of type **time and material**.

If a time and material project has multiple funding sources on the project contract, you must enable the **Allow sales orders for projects with multiple funding sources** parameter on the **Project management and accounting parameters** page.

> [!NOTE]
>
> - Support for project sales orders with multiple funding sources is available starting with application release 10.0.2 and higher.
> - The parameter to enable the support for project sales orders with multiple funding sources is removed in the April 2020 release wave. After this release, the functionality is always enabled.

You can create project-based sales orders in two ways:

- Go to the project itself. On the Action Pane, select **Manage > Item tasks > Sales order**. The sales order defaults to the project information. If the project contract has more than one funding source, you need to select the funding source to set the customer for the sales order. If there's only one funding source for the project, the customer is set automatically.
- Go to the **All sales order** list page and create a new sales order. You need to select the project for the sales order. After you select the project, the customer is set from the funding source or you need to select the funding source if the project contract has multiple funding sources.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
