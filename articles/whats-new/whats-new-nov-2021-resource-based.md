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


##

## Features included in this release

The following features are included in this release:

- Project Scheduling APIs now support the ability to create and delete Project buckets

##

## Project Operations dual-write maps updates

No updates for Project Operations Dual Write maps in this release. Please refer to [Project Operations dual-write map versions | Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-dual-write-maps) for current list and versions of Project Operations Dual Write maps.

You should always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance and Operations solution version. Certain features and capabilities might not work correctly if the latest version of the map is not activated. You can see the active version of the map in the  **Version**  column on the  **Dual-write**  page. You can activate a new version of the map by selecting  **Table map versions** , selecting the latest version, and then saving the selected version. If you have customized an out-of-the-box table map, reapply the changes. For more information, see [Application lifecycle management](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue with starting the map, follow instructions in the [Missing table columns issue on maps](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual Write troubleshooting guide.

## Quality updates

###

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing and Pricing | 2240080 | Payment terms field must not be duplicated on the Proforma invoice |
| Billing and Pricing | 2358236 | Invoice correction must allow corrections with zero price lines |
| Resource Management | 2410072 | Allow setting up resource assigned to the task as Project manager |
| Billing and Pricing | 2430234 | Fix cost performance calculation issue |
| Time and Expense | 2436978 | Allow enter time in hh:mm format |
| Billing and Pricing | 2448623 | Allow updating price lists after associating them with an organizational unit |
| Time and Expense | 2460396 | Allow deleting time entry by clearing the cell |
| Billing and Pricing | 2467386 | Allow deleting a project with task that was associated with a won quote |
| Time and Expense | 2461744 | "My failed approval" view only contains project approvals in "Submitted" stage |
| Time and Expense | 2464082 | Remove the link from project approvals to approval set when matching target status |
| Time and Expense | 2468108 | Schedule job should not set "processing" approval set status |
| Time and Expense | 2471503 | Delete approval sets that are 7 days old |
| Billing and Pricing | 2480687 | Quote Line reference must not be removed when creating Quote Line Milestone through UI |

### Project management and accounting on Dynamics 365 Finance

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Project management and accounting | [584732](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D584732&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476184727424%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=Ck7zeMqRwaf8DtVl4UiTMraKTu54htrnT2I%2Bsif%2B91c%3D&amp;reserved=0) | Vendor retainage results in project expense transactions not showing up |
| Project management and accounting | [593068](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D593068&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476184787161%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=IMdo79exCM6ADyN1%2FD7s4jyaWb3WM6BZbjEqjAJ8Flg%3D&amp;reserved=0) | Intercompany vendor invoice is broken when vendor invoice integration is turned on |
| Project management and accounting | [593382](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D593382&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476184807075%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=uKL%2Fl2JZI%2BhuYL%2BJl9rc9tTBonMrwKK18oQvNXRD37s%3D&amp;reserved=0) | The Terms of payment on the Project Invoices doesn&#39;t work as expected |
| Project management and accounting | [596263](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D596263&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476184856855%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=KRp2px%2F6fg3jwui2xFD6kfqSNZ3M91Jvtog7a8ktwwQ%3D&amp;reserved=0) | Project Management - When releasing vendor retention the voucher posting has incorrect additional lines |
| Project management and accounting | [598758](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D598758&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476184926547%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=6dEDVKWTG6ChBdCyruLQFysdAgqyaHf99pc3lEBhdfM%3D&amp;reserved=0) | Project Operations integration journal fails on posting due to missing dimensions for an account that is not being posted to |
| Project management and accounting | [602650](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D602650&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476185006200%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=bMXvG80actUIBT6o5C3Kpx7xQC7XnPO9okVznyIVrnc%3D&amp;reserved=0) | Project tab is not editable on pending vendor invoice when the Procurement category is assigned to the Item |
| Project management and accounting | [605121](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D605121&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476185046026%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=mQ3YjsNmrOZEWYEiGqwdYHtQiFHAjTlo2X1j%2FzySsVI%3D&amp;reserved=0) | Navigation pane missing if not logged in Project Operations Dataverse |
| Project management and accounting | [602728](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D602728&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476185245149%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=c5u%2FKf3hsKbmENgSCd5p2H5HhRA8BhWsyk1tk%2FxD77w%3D&amp;reserved=0) | Project invoiced revenue posting issue in applied retainer case: transactions on voucher do not balance |
| Project management and accounting | [603624](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D603624&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476185265061%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=3Fh4t3OgVkFQSzRu82P9Qh00thtlRNJjmcQSBxI6K%2FE%3D&amp;reserved=0) | Estimate creation after posting invoice proposal blocks import of correction lines |
| Project management and accounting | [606083](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D606083&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476185294938%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=SSAgiHMpZk2e13IDDc1SawaZZF5NObdIaq5cU2dJnAo%3D&amp;reserved=0) | Modifying full invoiced milestone record must not be possible |
| Travel and Expense | [575305](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D575305&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476184677646%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=dlfQUXcHh7t9pwZY4ZOT2S47C3Y%2FRsL2Yb%2BJpxNYpXw%3D&amp;reserved=0) | Able to see everyone&#39;s expense when searching for a category on the mobile app |
| Travel and Expense | [583101](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D583101&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476184707512%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=QsXmzAvMk%2FPHuk8MzpkrQil%2FHdAQgE479%2FNDmBwBtg0%3D&amp;reserved=0) | Incorrect amounts on Vendor transaction and Sales tax transaction posted from Expense created from Credit card transaction |
| Travel and Expense | [583760](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D583760&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476184717468%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=Kyn2sB5ARELNfumeCOQdFXAmJGWzxcKmb1LOyBbwVgU%3D&amp;reserved=0) | Expense Report - Irrelevant warning message pop up after refreshing the expense report pages |
| Travel and Expense | [598656](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D598656&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476185583665%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=OC7NDjdWmhgqYtw6UTSC6eCSosfuGfLIk8BLivnaQ2k%3D&amp;reserved=0) | wrong interim approve is used when you delete an interim approve and re-submit through Workflow |
| Travel and Expense | [612742](https://nam06.safelinks.protection.outlook.com/?url=https:%2F%2Ffix.lcs.dynamics.com%2FIssue%2FDetails%2F?bugId%3D612742&amp;data=04%7C01%7Cjespers%40microsoft.com%7Cf3623fb2bb5a448ee2ed08d9881c03f8%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637690476185663316%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=UEm4TMhTdD6VNMrCXkmakBxupUlzQVH0umZc3WSnzLw%3D&amp;reserved=0) | Posting error related to mileage setup |
