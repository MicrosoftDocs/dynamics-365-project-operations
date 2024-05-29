---
title: Project Service Automation integration parameters
description: This article explains how to configure how default data is entered when you integrate Microsoft Dynamics 365 for Project Service Automation with Microsoft Dynamics 365 Finance.
author: tulsij
ms.author: tulsijhaveri
ms.date: 05/28/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067

---

# Project Service Automation integration parameters

[!include[banner](../includes/banner.md)]

On the **Project Service Automation integration parameters** page, you can configure how default data is entered when you integrate Dynamics 365 Project Service Automation with Dynamics 365 Finance. For projects to be successfully synchronized from Project Service Automation to Finance, you must set up the following fields.

To open the **Project Service Automation integration parameters** page, go to **Project management and accounting** \> **Setup** \> **Dynamics 365 for Project Service Automation integration parameters**. 

> [!NOTE]
> - Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in version 8.0.
> - Actuals integration is available in version 8.0.1 or later.


| Tab                    | Field                | Description |
|------------------------|----------------------|-------------|
| General                | Default project type | Select the default project type. When projects are synchronized from Project Service Automation, this value is used if you didn't provide a default value in the integration template. During synchronization, the **Project type** field of new projects is set to this value. However, the value might be updated when the project contract lines are synchronized from Project Service Automation. |
|                        | Time category        | Select the default time category. This value is used when hour estimates are synchronized from Project Service Automation. When the hour estimates and hour actuals are synchronized from Project Service Automation, the **Category** field of new project hour forecasts in Finance is set to this value. |
|                        | Fee category         | Select the default fee category. This value is used when fee actuals are synchronized from Project Service Automation. When the fee actuals are synchronized from Project Service Automation, the **Category** field of new fee transactions in Finance is set to this value. |
| Project group defaults | Project type         | Click **New** to add a row where you can select the project type to set the default project group for. A specific project type can be selected only one time in the configuration. |
|                        | Project group        | Select the default project group for the selected project type. When new projects are synchronized from Project Service Automation, the **Project group** field is set to the default value for the project type if you didn't provide a default value in the integration template. |
| Billing type defaults  | Billing type         | Click **New** to add a row where you can select the billing type to set the default line property for. A specific billing type can be selected only one time in the configuration. |
|                        | Line property        | Select the default line property for the selected billing type. When new hour estimates, new expense estimates, or new actuals are synchronized from Project Service Automation, the **Line property** field is set to the default value for the billing type. |
| Functionality locking  | Not applicable       | Select the functionality to disable in Finance for projects and contracts that originated from Project Service Automation. For example, you can turn off the ability to edit contracts and projects, create work breakdown structures, and enter timesheets in Finance. Accounting-related fields will continue to be enabled, even if they are made unavailable by the parameter setting. By default, all functionality is enabled. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
