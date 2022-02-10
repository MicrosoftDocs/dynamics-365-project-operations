---
# required metadata

title: Actuals Impact duirng the Pre-Sales stage of an engagement 
description: This topic provides information the impact on the Actuals table at various events while the engagment is in the Pre-Sales stage in Microsoft Dynamics 365 Project Operations.
author: rumant
ms.date: 04/01/2021
ms.topic: overview
ms.prod: 
#
# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: tonyafehr
ms.search.scope: 
# ms.tgt_pltfrm: 

ms.assetid: 
ms.search.region: 
ms.search.industry: 
ms.author: rumant
ms.search.validFrom: 2020-10-01
---

#  Actuals Impact duirng the Pre-Sales stage of an engagement 

_**Applies to:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_


| **Event** | **Cost actual** | **Example** |
| --- | --- | --- |
|Time is created |   | Bob Kozack, from Fabrikam US Org Unit with a cost rate of 100 US per hour is working on a project "Arm Installation at Adatum".This project maps to a Fixed price billing method on the contract line. Here's a sample time entry from Bob Kozak: Bob Kozack - 8 hours |
|Time is submitted |   | Cost journal line is created for this time entry. Cost rate is defaulted on the journal entry |
|Time entry is recalled before it is approved |   |   |
|Time is approved| Created | **New Actuals Created:**<br> Cost Actual: Bob Kozack, 8hrs, 800 USD |
|Time approval is cancelled | Adjustment status on the original is updated to Adjusted<br> Reversal is Created with Adjustment status as Unadjustable | **Existing actuals updated:**<br>Cost Actual: Bob Kozack, 8hrs, 800 USD, _Adjusted_<br>**New Actuals Created for reversing previous financial impact:**<br> Cost Actual: Bob Kozack, (8hrs), (800 USD), _Unadjustable_ |
|Time entry is recalled after it is approved | Adjustment status on the original is updated to Adjusted<br> Reversal is Created with Adjustment status as Unadjustable | **Existing actuals updated:**<br>Cost Actual: Bob Kozack, 8hrs, 800 USD, _Adjusted_<br>**New Actuals Created for reversing previous financial impact:**<br> Cost Actual: Bob Kozack, (8hrs), (800 USD), _Unadjustable_ |
|Quote is Won and Contract is created | Old cost actuals are updated to Adjustment status Adjusted<br> Reversal cost actuals are created with Adjustment status as Unadjustable New cost actuals created after re-evaluating contractual rules|**Existing actuals updated:**<br>Cost Actual: Bob Kozack, 8hrs, 800 USD, _Adjusted_<br>**New Actuals Created for reversing previous financial impact:** <br>Cost Actual: Bob Kozack, (8hrs), (800 USD), _Unadjustable_<br> **New Actuals Created for re-evaluated financial impact when Quote is Won and contract is created**<br> Cost Actual: Bob Kozack, 8hrs, 800 USD<br> Unbilled Sales Actual: Bob Kozack, 8hrs, 1600 USD |

[!INCLUDE[footer-include](../includes/footer-banner.md)]

