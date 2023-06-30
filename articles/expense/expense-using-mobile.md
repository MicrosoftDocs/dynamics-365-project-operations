---
# required metadata

title: Mobile Expense app (legacy)
description: This article provides information about the Expense management mobile workspace.
author: suvaidya
ms.date: 11/15/2021
ms.topic: article
ms.prod: 
#

# optional metadata

ms.search.form: 
audience: Application User
# ms.devlang: 
ms.reviewer: johnmichalak
ms.search.scope: 
# ms.tgt_pltfrm: 
# ms.custom: 
ms.search.region: 
# ms.search.industry: 
ms.author: shylaw
ms.search.validFrom: 
ms.dyn365.ops.version: 
---

# Mobile Expense app (legacy)

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

This article provides information about the **Expense management** mobile workspace. This workspace lets users capture and upload a receipt, so that they can attach it to an expense report later. Users can also quickly create an expense line by using an attached receipt, and create and manage their expense reports. Additionally, approvers can use the **Expense management** mobile workspace to view expense reports that are assigned to them, and either approve or reject those expense reports.

This mobile workspace is intended to be used with the Dynamics 365 Unified Ops mobile app.

Many organizations require that a copy of a receipt be attached to a travel-related or business-related expense report that an employee submits for reimbursement. The **Expense management** mobile workspace lets users quickly create new expense lines on the mobile device of their choice by using an attached photo of a receipt. Alternatively, users can capture a photo of a receipt and then attach it to an expense report later. Employees can also create and manage their expense reports, and then submit them for approval and reimbursement by using their mobile device.

Specifically, the **Expense management** mobile workspace lets users perform these tasks:

- Take a photo of a receipt. Upload the receipt photo and attach it to an expense report later.
- Upload a file as a captured receipt. You can then attach that file to an expense report later.
- Create a new expense line by using an attached receipt. You can then add the line item to an expense report later, and submit it for approval and reimbursement.

You can also use these features:

- Create a new expense report.
- Attach credit card transactions and other previously created expenses to an expense report.
- Create new expenses for an expense report.
- Attach a receipt to any expense for an expense report, either by taking a photo of the receipt or by uploading a file as a captured receipt.
- Depending on the company's expense policy, add the list of guests to an expense.
- Depending on the company's expense policy, itemize expenses.
- Submit an expense report for approval and reimbursement.
- Approve or reject expense reports that you're an assigned approver for.

## Prerequisites if you use Dynamics 365 Finance

If Finance has been deployed for your organization, the system administrator must publish the **Expense management** mobile workspace. 

## Download and install the Dynamics 365 Unified Ops mobile app
Download and install the Dynamics 365 Unified Ops mobile app:

- [For Android phones](https://go.microsoft.com/fwlink/?linkid=850662)
- [For iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## Sign in to the mobile app
1. Start the app on your mobile device.
2. Enter your Dynamics 365 URL.
4. The first time that you sign in, you're prompted for your user name and password. Enter your credentials.
5. After you sign in, the available workspaces for your company are shown. If your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.

## Capture a receipt by using the Expense management mobile workspace

1. On your mobile device, open the **Expense management** workspace.
2. Select **Capture receipt**.
3. Select **Take photo** or **Choose image**.
4. Follow one of these steps:

    - If you selected **Take photo**, follow these steps:

        1. You're taken to the camera on your mobile device, so that you can take a photo of the receipt. 
        2. When you've finished taking a photo, select **OK** to accept the photo.
        3. Optional: Enter a name for the photo, and enter any notes.

    - If you selected **Choose image**, follow these steps:

        1. Select an image in the list.
        2. Optional: Enter a name for the image, and enter any notes.

5. Select **Done**.

## Quickly enter expenses by using the Expense management mobile workspace

1. On your mobile device, open the **Expense management** workspace.
2. Select **Quick expense entry**.
3. Select the expense category. You see a list of expense categories that are loaded into your app for offline use. By default, 50 items are loaded, but a developer can change this number. For more information, developers should see [Mobile platform](/dynamics365/fin-ops-core/dev-itpro/mobile-apps/platform/mobile-platform-getting-started). If your category isn't in the list, select **Search** to do an online search. Search by expense category, or switch to search by expense type.
4. Enter the transaction date of the expense.
5. Optional: Enter the merchant for the expense.
6. Enter the amount of the expense.
7. Select the currency of the expense. You see a list of the currency codes that are loaded into your app for offline use. By default, 400 currencies are loaded, but a developer can change this number. For more information, developers should see [Mobile platform](/dynamics365/fin-ops-core/dev-itpro/mobile-apps/platform/mobile-platform-getting-started). If your currency isn't in the list, select **Search** to do an online search. Search by currency, or switch to search by name.
8. Select **Take photo** or **Choose image**.
9. Follow one of these steps:

    - If you selected **Take photo**, you're taken to the camera on your mobile device, so that you can take a photo of the receipt. When you've finished taking a photo, select **OK** to accept the photo.
    - If you selected **Choose image**, select an image in the list.

10. Select **Done**.

## Approve an expense report by using the Expense management mobile workspace

1. On your mobile device, open the **Expense management** workspace.
2. **Expense approvals** shows the number of expense reports that are assigned to you for approval. The number is updated approximately every 30 minutes. Select **Expense approvals**.

    The list of expense reports that are assigned to you for approval is shown.

3. Select an expense report to view the expense details for it.
4. Select an expense to view the details for it. The information that is shown for an expense includes any receipt, guest, and itemization details.
5. Back on the **Expense report** page, select to approve or reject the expense report.
6. Enter any comments for the approval action.
7. Select **Done**.

## Create a new expense report and submit it for approval by using the Expense management mobile workspace

1. On your mobile device, open the **Expense management** workspace.
2. Select **Expense entry**.
3. Select **New report**, or select an existing expense report in the list.
4. For new expense reports, enter the purpose and any additional information that is available. This information varies, depending on that way that expense management is configured for your company.
5. Select **Done**.
6. To add existing expenses, such as credit card transactions, to the expense report, select **Attach**.
7. Select one or more expenses in the list.
8. Select **Done**.
9. To add a new expense to the expense report, select **New expense**.
10. Select the category for the expense. You see a list of expense categories that are loaded into your app for offline use. By default, 50 items are loaded, but a developer can change this number. For more information, developers should see [Mobile platform](/dynamics365/fin-ops-core/dev-itpro/mobile-apps/platform/mobile-platform-getting-started). If your category isn't in the list, select **Search** to do an online search. Search by expense category, or switch to search by expense type.
11. Optional: Enter the merchant for the expense.
12. Enter the transaction date of the expense.
13. Enter the amount of the expense.
14. Select the currency of the expense. You see a list of the currency codes that are loaded into your app for offline use. By default, 400 currencies are loaded, but a developer can change this number. For more information, developers should see [Mobile platform](/dynamics365/fin-ops-core/dev-itpro/mobile-apps/platform/mobile-platform-getting-started). If your currency isn't in the list, select **Search** to do an online search. Search by currency, or switch to search by name.
15. Select **Done**.
16. To add more details to the expense, select **Add more details**. The fields that are available depend on the configuration of expense management for your company.
17. If company policy requires a receipt for the expense, select **Receipts**, and then follow these steps:

    1. Select **Capture receipt** or **Attach receipt**.
    2. Follow one of these steps:

        - If you selected **Capture receipt**, follow these steps:

            1. Select **Take photo** or **Choose image**.
            2. Follow one of these steps:

                - If you selected **Take photo**, follow these steps:

                    1. You're taken to the camera on your mobile device, so that you can take a photo of the receipt. When you've finished taking a photo, select **OK** to accept the photo.
                    2. Optional: Enter a name for the photo, and enter any notes.

                - If you selected **Choose image**, follow these steps:

                    1. Select an image in the list.
                    2. Optional: Enter a name for the image, and enter any notes.

            3. Select **Done**.

        - If you selected **Attach receipt**, follow these steps:

            1. Select one or more images in the list.
            2. Select **Done**.

    3. Select the **Back** button to return to the expense details.

18. If company policy requires guests for the expense, select **Guests**, and then follow these steps:

    1. Select **Guest**, **Previous guests**, or **Coworkers**.
    2. Follow one of these steps:

        - If you selected **Guest**, follow these steps:

            1. Enter the name of the guest.
            2. Optional: Enter the organization and/or country/region of the guest.
            3. Optional: Enter the title of the guest.
            4. Select **Done**.

        - If you selected **Previous guests**, follow these steps:

            1. Select one or more previous guests in the list. You see a list of previous guests that you've added to previous expense reports that are loaded into your app for offline use. By default, 50 items are loaded, but a developer can change this number. For more information, developers should see [Mobile platform](/dynamics365/fin-ops-core/dev-itpro/mobile-apps/platform/mobile-platform-getting-started). If your previous guest isn't in the list, select **Search** to do an online search. Search by name, or switch to search by organization, country, or title.
            2. Select **Done**.

        - If you selected **Coworkers**, follow these steps:

            1. Select one or more coworkers in the list. You see a list of coworkers that are loaded into your app for offline use. By default, 50 items are loaded, but a developer can change this number. For more information, developers should see [Mobile platform](/dynamics365/fin-ops-core/dev-itpro/mobile-apps/platform/mobile-platform-getting-started). If your coworker isn't in the list, select **Search** to do an online search. Search by name, or switch to search by company or title.
            2. Select **Done**.

    3. Select the **Back** button to return to the expense details.

19. If company policy requires that the expense be itemized, select **Itemize**, and then follow these steps:

    1. Select the first date to itemize.
    2. Select **Add itemization**.
    3. Select the subcategory for the expense itemization. You see a list of expense subcategories that are loaded into your app for offline use. By default, 50 items are loaded, but a developer can change this number. For more information, developers should see [Mobile platform](/dynamics365/fin-ops-core/dev-itpro/mobile-apps/platform/mobile-platform-getting-started). If your subcategory isn't in the list, select **Search** to do an online search. Search by expense subcategory name.
    4. Enter the transaction amount for the itemization.
    5. Edit the transaction date if it's required.
    6. Select **Done**.
    7. Repeat the preceding steps until you've finished adding all itemizations for the selected date.
    8. For additional days, you can select **Copy to next day** to copy the itemizations to the next day. Alternatively, you can select the date to itemize and then add itemizations as you did for the first date.
    9. After you've finished itemizing the expense, select the **Back** button to return to the expense details.

20. Select the **Back** button to return to the **Expense report** page.
21. Repeat the preceding steps until you've finished adding all expenses.
22. Select **Submit**.
23. Enter any comments for the approver.
24. Select **Done**.

## Frequently asked questions

### Why doesn't the Expense mobile app enter the payment method by default?

Organizations can customize the **Default payment method** setting for each expense category as it's created. Additionally, when you set up payment methods, you can set the **Default payment method** field to **Import only**.

When **Import only** is enabled for a payment method, the payment method isn't entered by default. It will be blank in expense categories where this payment method is set up. This behavior is consistent in both the web experience and the mobile experience.
	
When **Import only** isn't enabled for a payment method, the set value is entered by default for expense categories where this payment method is set up. However, there is a known issue where the default value isn't entered in the Expense mobile app. To work around this issue, manually select a payment method before you save the expense report. 

### Why can't I add or edit financial dimensions in the Expense mobile app?

Entry of dimensions and distributions isn't supported. To work around this limitation, you can have these fields set by default in the mobile app by setting up the default financial dimensions per project or employee.

### Why do I sometimes see a synchronization error in the Expense mobile app?

If the expense lines don't meet the policy requirements, and the user submits the expense report without addressing the policy warning, the mobile data isn't synced to the server, and a synchronization failure occurs. All expense reports that are submitted after a synchronization failure occurs will remain in a failed state and cause more synchronization failures. The only way to fix this situation is to manually delete the synchronization notifications. This issue has been addressed by stopping the submission of expense reports when policy warnings haven't been addressed, so that the synchronization errors are avoided.

### Why isn't project and category validation correctly reflected in the Expense mobile app?

This validation isn't currently supported. However, support might be added in the future. 

### What document types are supported in the Expense mobile app?

The Expense mobile app supports only images. It doesn't currently support PDFs or other documents.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
