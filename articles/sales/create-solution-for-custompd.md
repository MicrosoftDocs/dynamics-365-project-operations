--- 

title: Create a solution for custom pricing dimensions 
description:  Create a solution for custom pricing dimension
author: Rumant
manager: tfehr 
ms.date: 11/05/2020  
ms.topic: article 
ms.service: project-operations 
ms.reviewer: kfend 
ms.author: rumant 
--- 

# Create a solution for custom pricing dimensions

 _**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing, Project Operations for stocked/production-based scenarios_ 

**Important**: All custom pricing dimension changes should be in a separate solution. This important best practice provides flexibility in the future to update or remove changes as needed, will help with re-use of your work, and makes it easier to port these changes to another instance. After you make the required changes, export this solution as a Managed solution, and import it into other instances to reuse your pricing setup.

## Create a solution for custom pricing dimensions
1.	Select Settings > Solutions, and then select New.
2.	Name the solution, <your organization name> pricing dimensions, enter the remaining required information, and then select Save.

! [Creation of custom pricing dimension solution] (./media/Creation-of-custom-pricing-dimension-solution.png)
 
## Add all required entities and related components to the Pricing dimension solution
You will need to add the following Project Service entities to your pricing solution. Complete the steps in this procedure to make some important schema changes in the pricing solution so that the entities become aware of the new pricing dimensions.
1.	Select Settings > Solutions, and then double-click <your organization name> pricing dimensions.
2.	In Solution Explorer, on the left navigation pane, select Add Existing > Entities.
3.	In the Solution Components dialog box, select the following entities:
      •	Actual
 
      •	Bookable Resource
 
      •	Estimate Line
      
      •	Project Task
      
      •	Invoice Line Detail
      
      •	Journal Line
      
      •	Project Contract Line Detail
      
      •	Project Team Member
      
      •	Quote Line Detail
      
      •	Role Price Markup
      
      •	Role Price
      
      •	Time Entry
 
 ! [Add existing entities custom pricing dimension solution] (./media/Existing-entities-to-PD-solution.png)
 
 
 ! [Entities Added] (./media/solution-component-selection.png)
 

**Note** Make sure to include all forms and views for each of the entities selected.

4.	When prompted to include any dependent entities for the selected entities, select No.

! [Entities Added] (./media/Do-not-include-required.png)
 

