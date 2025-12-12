---
title: Assign generic bookable resources to a task and project team
description: This article provides information about booking generic resources to tasks and project teams.
author: JohnPBurrows
ms.custom: 
  - dyn365-projectservice
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: how-to
ms.author: abriccetti
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---
# Assign generic bookable resources to a task and generate resource requirements 

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

In addition to booking and assigning named or real resources to your project, you can assign generic resources to project tasks. These resources can serve as placeholders for named resources until you're ready to staff your project with named resources. 

1. In Project Operations, open the **Project** record and on the **Tasks** tab, then select the resource selector under the **Assigned to** column. Here select the three dots and then **Add generic resource**.

![Creating and assigning a generic team member.](media/add-generic-resource.png)

This opens the **Quick Create: Project Team Member** panel. 

2. Enter the role and any other desired fields of the generic resource team member and then click **Save**.

![Generic team member quick create.](media/generic-resource-quick-create.png)

3. After you create the new generic resource team member, it's assigned to the task. You can continue to assign that generic resource to other tasks in the task schedule.

![Assigning existing generic team member to tasks.](media/assign-generic-resource.png)

4. After you assign the generic resource, you can generate a resource requirement and fulfill it by directly booking or submitting a resource request to a Resource Manager.

![Generating a requirement for a generic team member.](media/generate-requirement.png)

On the team member grid, in addition to being able to use the resource picker as mentioned above, you can add generic resources directly. This can be done by leaving the **Bookable Resource** field on the quick create form blank. The resources are added with a resource requirement that is based on the start/end dates and allocation method specified in the **Quick Create: Project Team Member** panel.

You can see a difference if you add the generic team member directly and then assign more tasks to the generic resource than they have required hours to cover. Click **Generate Requirement** to regenerate the requirement to balance the required hours against assignments.

You can also click the **Resource requirement** link in the team grid to open the requirement and add skills, preferred resources, etc.

![Resource requirement.](media/add-skill-to-requirement.png)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
