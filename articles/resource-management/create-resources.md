---
title: Create Bookable Resources
description: This article provides a link to information about how to create bookable resources.
author: tulsij
ms.author: tulsijhaveri
ms.date: 05/20/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Create Bookable Resources

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

Resources are the most important asset of a project-based or service-based organization. You can create bookable resource in Dynamics 365 Project Operations using the Resources page. 

## Create  bookable resources
  
- In Project Operations, navigate to the **Resources** area and go to **Resource** > **Resources** and select **New**.

- On the **General** tab:

   - Choose a **Resource Type**. A classification that describes who or what the resource is and how the resource relates to your organization. Depending on the value you choose, there are other related details to define.
        - **User**: A person or a user in your company directory that may be scheduled or may need access to the system. 
       - **Account** or **Contact**: The resource may directly a part of your organization but you want to schedule it. For example, a vendor company that doesn't have access to your system but provides services on your behalf.
       - **Equipment**: A piece of equipment that you want to schedule. For example, a computer or a cell phone.

   - Enter the **Name** of the resource and set the details.
 > [!NOTE]
 > Bookable resource is a shared concept for applications using dataverse such as Dynamics 365 Project Operations as well as Dynamics 365 Field Service.  Some of the bookable resource types such as: **crew**, **facility**, and **pool** are not supported in Project Operations.  
- On the **Project Service** tab, define **Target Utilization** for the resource (if applicable). 
  
- On the **Scheduling** tab:
   - Select appropriate **Organizational Unit** that the resource belongs to and input other details (if applicable).
   - To allow resource to be available for scheduling on the schedule board, select 'Yes' for **Display On Schedule Board**. For more information about displaying resources on the schedule board, see [Experience the schedule board in Universal Resource Scheduling](/dynamics365/common-scheduler/use-schedule-board).
   - Set **Enable for Availability Search** to define if the [schedule assistant can return the resource](/dynamics365/common-scheduler/schedule-assistant) if it matches the criteria.
   
 - **Save** the record to view other details.

### Add work hours  

You can define work hours for each resource. Initially, it uses the default work hours. The schedule board differentiates work hours and nonwork hours with colors. The schedule assistant returns only resources that have capacity in their designated work hours.

-  Open a resource record and go to **Work hours** tab.
-  You can either update existing hours for all events or select **New** > **Working hours** to add more working or nonworking hours.
-  Set the start and end time of the resource's work hours and choose a repeat pattern. Use the *Custom* repeat pattern for recurring working hours, where resources can have different working hours on different days of the week.

  ![BRWorkHours](https://github.com/MicrosoftDocs/dynamics-365-project-operations-pr/assets/129548753/3bab895e-a229-473b-943a-2303e9d65bb3)


- Enable **Capacity** to define the number of times the resource can be booked during their work hours. For example, setting the capacity to *five* means that when booking a resource with the schedule assistant, the resource shows as available and can be overbooked up to the capacity limit (in this case, five times). It's set to *one* by default. Changing the value to *zero* stops showing the resource as available in a resource search.

- **Add break** splits each working hours entry and adds a break of 30 minutes. **Add split** splits each working hours entry evenly into two working hours entries, so that each split entry can have a different capacity. The **Add split** option only shows when you enable **Capacity**.

- Set the time zone for the resource work hours to make sure the system uses them correctly.

- **Save** the work hours to update the work hours calendar.

For more information about editing work hour calendars with code, see [Edit work hour calendars by using APIs](/dynamics365/field-service/field-service-work-hours-calendar-api).

### Add Resource roles 
Resource categories are roles or groups of categories that help distinguish them. For example, a resource's role or job title.

A resource can have multiple categories. [Create resource roles](define-roles.md) and map it to a resource. If a resource has multiple roles assigned, one of them can be defined as a 'default' role. 

- Change to the **Resources** area and go to **Resource** > **Resources**. Open a resource record and select **Related** > **Resource Category Assns**.
  
- Select **New Resource Category Assns**.
  
- Select a **Resource Category** from the lookup.

### Add Skills and other characteristics

Characteristics represent a resource's skills and certifications. For example, a specific skill like a CPR certification; more general, like accounting or web development experience; or as simple as security clearance for a specific building. A certificate can be anything that the organization tracks for resources such as a Project Management Professional (PMP) certificate for a Project Manager or a six sigma course completion certificate. Read more about [Skills and proficiencies](/dynamics365/project-operations/resource-management/define-skills-proficiencies) to learn more.

A resource can have multiple characteristics. [Create characteristics](/field-service/set-up-characteristics), map it to a resource, and provide a proficiency rating.
  
- Change to the **Resources** area and go to **Resource** > **Resources**. Open a resource record and select **Related** > **Resource Characteristics**.  
  
- Select **Add New Bookable Resource Characteristics**.  
  
- Select a **Characteristic** from the lookup.

- (Optional) Select a **Rating Value** for skill proficiency. Depending on the [proficiency model of the characteristic](/dynamics365/field-service/set-up-characteristics#create-a-proficiency-model), it could be a 1-to-10 rating, or even represent the score on a certification exam.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
