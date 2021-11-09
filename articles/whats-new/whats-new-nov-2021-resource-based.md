---
title: What's new November 2021 - Project Operations for resource/non-stocked based scenarios
description: This topic provides information about the quality updates available in the November 2021 release of Project Operations for resource/non-stocked based scenarios.
author: sigitac
ms.date: 11/09/2021
ms.topic: article
ms.prod:
ms.reviewer: kfend 
ms.author: sigitac
---

# What's new November 2021 - Project Operations for resource/non-stocked based scenarios

*Applies To: Project Operations for resource/non-stocked based scenarios*

This topic applies to the following Dynamics 365 Project Operations components and versions:

   - Project Operations in Microsoft Dataverse environment version 4.26.0.145
   - Project management and accounting in Dynamics 365 Finance environment version 10.0.22

## Features included in this release

The following features are included in this release:

- Project Scheduling APIs now support the ability to create and delete Project buckets.

## Project Operations dual-write maps updates

There are no updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](/dynamics365/project-operations/environment/resource-dual-write-maps).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Certain features and capabilities might not work correctly if the latest version of the map isn't activated. You can see the active version of the map on the **Dual-write** page in the **Version** column. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you have customized an out-of-the-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue starting the map, follow instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing and Pricing | 2240080 | The **Payment terms** field must not be duplicated on the **Proforma invoice**. |
| Billing and Pricing | 2358236 | Invoice correction must allow corrections with zero price lines. |
| Resource Management | 2410072 | Allow set up of a resource that's assigned to the task as a Project manager. |
| Billing and Pricing | 2430234 | Fix cost performance calculation issue. |
| Time and Expense | 2436978 | Allow time to be entered in a hh:mm format. |
| Billing and Pricing | 2448623 | Allow price lists to be updated after they are associated with an organizational unit. |
| Time and Expense | 2460396 | Allow a time entry to be deleted by clearing the cell. |
| Billing and Pricing | 2467386 | Allow a project with task to be deleted even when the task is associated with a won quote. |
| Time and Expense | 2461744 | The **My failed approval**" view only contains project approvals in the **Submitted** stage. |
| Time and Expense | 2464082 | Remove the link from project approvals to the approval set when matching a target status. |
| Time and Expense | 2468108 | The Schedule job should not set a **Processing** approval set status. |
| Time and Expense | 2471503 | Delete approval sets that are seven days old. |
| Billing and Pricing | 2480687 | The quote line reference must not be removed when creating a quote line milestone. |

### Project management and accounting on Dynamics 365 Finance

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Project management and accounting | [584732](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D584732&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476184727424%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=Ck7zeMqRwaf8DtVl4UiTMraKTu54htrnT2I%2Bsif%2B91c%3D&amp;reserved=0) | Retained vendor amounts in project expense transactions aren't showing up in the transaction list. |
| Project management and accounting | [593068](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D593068&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476184787161%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=IMdo79exCM6ADyN1%2FD7s4jyaWb3WM6BZbjEqjAJ8Flg%3D&amp;reserved=0) | Intercompany vendor invoice is broken when vendor invoice integration is turned on. |
| Project management and accounting | [593382](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D593382&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476184807075%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=uKL%2Fl2JZI%2BhuYL%2BJl9rc9tTBonMrwKK18oQvNXRD37s%3D&amp;reserved=0) | The terms of payment on project invoices doesn't work as expected. |
| Project management and accounting | [596263](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D596263&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476184856855%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=KRp2px%2F6fg3jwui2xFD6kfqSNZ3M91Jvtog7a8ktwwQ%3D&amp;reserved=0) | When releasing vendor retention, the voucher posting has additional lines that are incorrect. |
| Project management and accounting | [598758](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D598758&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476184926547%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=6dEDVKWTG6ChBdCyruLQFysdAgqyaHf99pc3lEBhdfM%3D&amp;reserved=0) | When posted, the Project Operations integration journal fails because of missing dimensions for an account that isn't being posted to. |
| Project management and accounting | [602650](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D602650&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476185006200%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=bMXvG80actUIBT6o5C3Kpx7xQC7XnPO9okVznyIVrnc%3D&amp;reserved=0) | The **Project** tab isn't editable on a pending vendor invoice when the procurement category is assigned to the item. |
| Project management and accounting | [605121](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D605121&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476185046026%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=mQ3YjsNmrOZEWYEiGqwdYHtQiFHAjTlo2X1j%2FzySsVI%3D&amp;reserved=0) | The navigation pane is missing if you aren't logged in to Project Operations Dataverse. |
| Project management and accounting | [602728](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D602728&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476185245149%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=c5u%2FKf3hsKbmENgSCd5p2H5HhRA8BhWsyk1tk%2FxD77w%3D&amp;reserved=0) | When you post revenue from a Project invoice in applied retainer case, transactions on the voucher don't balance which causes an issue. |
| Project management and accounting | [603624](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D603624&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476185265061%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=3Fh4t3OgVkFQSzRu82P9Qh00thtlRNJjmcQSBxI6K%2FE%3D&amp;reserved=0) | Creating an estimate after you post an invoice proposal blocks correction lines from import. |
| Project management and accounting | [606083](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D606083&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476185294938%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=SSAgiHMpZk2e13IDDc1SawaZZF5NObdIaq5cU2dJnAo%3D&amp;reserved=0) | Modifying a fully invoiced milestone record shouldn't be possible. |
| Travel and Expense | [575305](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D575305&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476184677646%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=dlfQUXcHh7t9pwZY4ZOT2S47C3Y%2FRsL2Yb%2BJpxNYpXw%3D&amp;reserved=0) | All expense reports are visible when you search for a category on the Expense mobile app. |
| Travel and Expense | [583101](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D583101&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476184707512%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=QsXmzAvMk%2FPHuk8MzpkrQil%2FHdAQgE479%2FNDmBwBtg0%3D&amp;reserved=0) | Incorrect amounts on vendor transactions and sales tax transactions are posted from an expense that's created from a credit card transaction. |
| Travel and Expense | [583760](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D583760&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476184717468%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=Kyn2sB5ARELNfumeCOQdFXAmJGWzxcKmb1LOyBbwVgU%3D&amp;reserved=0) | An irrelevant warning occurs when you refresh the **Expense report** page. |
| Travel and Expense | [598656](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D598656&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476185583665%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=OC7NDjdWmhgqYtw6UTSC6eCSosfuGfLIk8BLivnaQ2k%3D&amp;reserved=0) | The wrong interim approver is used when you delete an interim approver and then re-submit an expense report through the workflow. |
| Travel and Expense | [612742](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D612742&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476185663316%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=UEm4TMhTdD6VNMrCXkmakBxupUlzQVH0umZc3WSnzLw%3D&amp;reserved=0) | A posting error that's related to mileage setup occurs. |
