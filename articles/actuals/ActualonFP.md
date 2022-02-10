---
# required metadata

title: Actuals Impact in a Fixed Price Engagement
description: This topic provides information the impact on the Actuals table at various events during the lifecylce of a Fixed Price engagement in Microsoft Dynamics 365 Project Operations.
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

#  Actuals Impact in a Fixed Price Engagement 

_**Applies to:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_


| **Event** | **Cost actual** | **Unbilled Sales actual** | **Billed Sales actual** | **Example** |
| --- | --- | --- | --- | --- |
| Time is created |   |   |   | Bob Kozack, from Fabrikam US Org Unit with a cost rate of 100 US per hour is working on a project "Arm Installation at Adatum".This project maps to a Fixed price billing method on the contract line. Here's a sample time entry from Bob Kozak: Bob Kozack - 8 hours |
| Time is submitted |   |   |   | Cost journal line is created for this time entry. Cost rate is defaulted on the journal entry |
| Time entry is recalled before it is approved |   |   |   |   |
| Time is approved| Created |   |   | **New Actuals Created:** <br> Cost Actual: Bob Kozack, 8hrs, 800 USD |
| Time approval is cancelled | Adjustment status on the original is updated to Adjusted <br> Reversal is Created with Adjustment status as Unadjustable |   |   | **Existing actuals updated:** <br> Cost Actual: Bob Kozack, 8hrs, 800 USD, _Adjusted_ <br>  **New Actuals Created for reversing previous financial impact:** <br>  Cost Actual: Bob Kozack, (8hrs), (800 USD), _Unadjustable_ |
| Time entry is recalled after it is approved | Adjustment status on the original is updated to Adjusted <br>  Reversal is Created with Adjustment status as Unadjustable |   |   | **Existing actuals updated:** Cost Actual: Bob Kozack, 8hrs, 800 USD, _Adjusted_ <br> **New Actuals Created for reversing previous financial impact:**  <br> Cost Actual: Bob Kozack, (8hrs), (800 USD), _Unadjustable_|
| Contract is confirmed | Old cost actuals are updated to Adjustment status Adjusted <br> Reversal cost actuals are created with Adjustment status as Unadjustable <br>  New cost actuals created after re-evaluating contractual rules |   |   | **Existing actuals updated:** <br> Cost Actual: Bob Kozack, 8hrs, 800 USD, _Adjusted_ **New Actuals Created for reversing previous financial impact:**<br>   Cost Actual: Bob Kozack, (8hrs), (800 USD), _Unadjustable_<br>  **New Actuals Created for re-evaluated financial impact**<br>  Cost Actual: Bob Kozack, 8hrs, 800 USD |
| Invoice is created | |   |   |   |
| Invoice is confirmed with a miletone |   |   | New milestone-based billed sales actuals are created | **Unchanged actuals:**<br>  Cost Actual: Bob Kozack, 8hrs, 800 USD <br> **New Actuals created for recording Billed Sales values:** <br>  Billed Sales Actual: Milestone, 5000 USD |
| Invoice is corrected to credit the milestone |   |   | Reversal billed sales actuals are created | **Unchanged actuals:** <br> Cost Actual: Bob Kozack, 8hrs, 800 USD **Existing Actuals Updated:** Billed Sales Actual: Milestone, 5000 USD, _Adjusted_ <br> **New Actuals created for reversing previous Billed Sales:** <br> Billed Sales Actual: Milestone, (5000 USD),_Unadjustable_ |
