---
title: Developer Notes for Approvals
description: This topic provides additional deverloper information about working with approvals in Project Operations.
author: stsporen
manager: Annbe
ms.date: 10/05/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: stsporen
---

# Approvals Permission
Project Operations includes validation logic that ensures that record transition correctly through the different stages of approval. This is to ensure that supporting rows are created in related tables such as journals and actuals.

This validation ensures that the Approver is marked as a Project Approver within the Project before proceeding.
