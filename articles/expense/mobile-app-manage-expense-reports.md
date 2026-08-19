---
title: Manage expense reports by using the Dynamics 365 expense management mobile app
description: Learn how to manage expense reports efficiently with the Dynamics 365 expense management mobile app. Create, submit, and track reports on the go.
author: ajitchandran
ms.date: 08/19/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: ajitchandran
---

# Manage expense reports by using the Dynamics 365 expense management mobile app

[!INCLUDE [banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations for manufacturing-based scenarios_

This article explains how to manage expense reports by using the Dynamics 365 expense management mobile app.

The **Reports** tab of the Dynamics 365 expense management mobile app shows all expense reports for the employee for the selected company. It's subdivided into three tabs that group the expense reports based on their status:

* **Draft** – This tab shows all the expense reports that are in **Draft** or **Rejected** status. The app highlights rejected expense reports in red to indicate that they're rejected.
* **In review** – This tab shows all the expense reports that are in **In review** status.
* **Approved** – This tab shows all the expense reports that are in **Approved** or **Processed for payment** status.

## Create an expense report

To create an expense report, follow these steps:

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Reports** tab, on the **Draft** tab, select the plus sign (**+**) button.
1. Optional: Enter a name for the expense report.
1. Optional: Enter a description.
1. Optional: Enter the location.
1. Select **Attach expenses**.
1. In the list of expenses, select one or more expenses.
1. Select **Done**.
1. Select **Save Draft** to save the report as a draft. Alternatively, select **Submit** to save the report and submit it for review.

### Create expenses from an expense report

> [!NOTE]
>
> * The **Create expenses from expense report** feature is available from Expense Mobile App Version: 3.2.3257.440 and Dynamics 365 Finance versions: 10.0.44 (10.0.2263.184 or later), 10.0.45 (10.0.2345.125 or later), and 10.0.46 (10.0.2428.61 or later).

To enable **Create expenses from report**, follow these steps:

1. Go to **Expense Management** > **Setup** > **General** > **Expense management parameters**.
1. Under **GENERAL**, enable **Create expenses from report**.

To create an expense from within an expense report, follow these steps:

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Reports** tab, on the **Draft** tab, select the report where you want to create an expense.
1. Select **+ Attach expenses** to open a new form with all the existing expenses.
1. Select **Create new expense** to create a new expense line.
1. The app automatically selects this expense. Select **Done** to add the line to the expense report.

## Delete expense reports

To delete expense reports, follow these steps:

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Reports** tab, on the **Draft** tab, select **Multi select**.
1. Select one or more expense reports.
1. Select **Delete**.
1. In the confirmation message box, select **Delete**.

After you delete an expense report, the app moves all the expenses that were attached to it to the list of unattached expenses. You can view these expenses on the **Expenses** tab.

## Submit an expense report for review

To submit an expense report for review, follow these steps:

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Reports** tab, on the **Draft** tab, open the expense report that you want to submit for review.
1. Select **Submit**.

After you submit an expense report, the app moves it to **In review** status. The report is available on the **In review** tab.

## Recall an expense report

To recall an expense report, follow these steps:

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Reports** tab, on the **In review** tab, open the expense report that you want to recall.
1. Select **Withdraw**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
