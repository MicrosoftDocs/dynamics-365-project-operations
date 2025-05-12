--- 
title: Saving changes to a project's work breakdown structure 
description: This article explains how changes made the work breakdown structure are saved to Dataverse.
author:  abriccetti
ms.date: 07/30/2024  
ms.topic: concept-article
ms.custom: bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
--- 

# Saving changes to a project's work breakdown structure

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

Microsoft Dynamics 365 Project Operations embeds Microsoft Project for the web inside the tasks tab of a project record. When edits are made to the work breakdown structure (WBS) the UI immediately shows the changes; however, an asynchronous save process is triggered to update the relevant fields in Dataverse. The amount of time this asynchronous save takes depends on the size of the changes. If a change requires updates to many entities, for example adjusting dates on a task that many other tasks depend on, it takes longer than a change that updates few entities.

> [!NOTE]
>  The updates to Dataverse are done by the Microsoft Project system user not by the user making edits in the tasks tab. If you check the Modified By column in the project tasks table, the table shows Microsoft Project as the user who made the most recent updates when a project task is edited through the Project for the Web. There two additional columns in the project tasks table called "Project for the web ModifiedBy" and "Project for the web CreatedBy" that shows the user who made the edit or created the task respectively in Project for the web.
> 
## Save Status

An icon in the top right corner of the Project for the web UI indicates the save status. The save status icon has three states.

A green check mark indicates there isn't a pending save, and Dataverse and Project for the web are in sync. This icon indicates that project data in Dataverse, which is calculated from the work breakdown structure, is up-to-date with all changes (for example, data in the summary, estimates, and tracking tabs).

![No pending save.](media/savecomplete.png)

A blue spinner indicating that a save is currently in progress.

![Save in progress.](media/saveinprogress.png)

A red x indicates the save to Dataverse failed, and the project reverts to the previous state upon reload (this reload shows a warning banner and requires a page refresh to revert the failed save and continue editing). To see more details about what caused an error when saving to Dataverse fails, navigate to the **PSS Error Log** (in the **Settings** area).

![Save failure.](media/savefailure.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
