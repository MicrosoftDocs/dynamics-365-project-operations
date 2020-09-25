---
# required metadata

title: Understanding Project Status
description: This topic provides information about Project management in Dynamics 365 Project operations. 
author: ruhercul
manager: AnnBe
ms.date: 09/16/2020
ms.topic: article
ms.prod: 
ms.service: dynamics-project-operations
ms.technology: 

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: kfend
ms.search.scope: 
# ms.tgt_pltfrm: 
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Service industries
ms.author: suvaidya
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---

Project status summary
======================

The **Status** section on the **Project entity** page provides a summary of a project's health based upon cost and effort.


Status summary fields
---------------------

- The **Overall project status** field is an editable field that shows the overall
status of the project. It uses color-coding, such as green, yellow, and red, to
indicate increasing risk. 
- The **Comments** field lets the project manager enter
specific comments about the status. 
- The **Status updated on** field is not
editable and the value is a timestamp that indicates when the status was last
updated.
- The **Schedule performance** and **Cost performance** fields are set from the
tracking grid. When the schedule and cost variance for the root node in
the **Effort tracking** view are positive, you can set these fields are updated
to **Ahead**. When the schedule and cost variance for the root node are
negative, these fields are set to **Behind**.
