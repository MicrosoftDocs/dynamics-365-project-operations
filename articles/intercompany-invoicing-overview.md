---
# required metadata

title: Intercompany invoicing overview
description: This article provides information and examples about intercompany invoicing for projects.
author:  sigitac
manager: tfehr
ms.date: 11/05/2020 
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend
ms.author: sigitac

---

Your organization might have multiple divisions, subsidiaries, and other legal entities that transfer products and services to each other for projects. The legal entity that provides the service or product is called the _lending legal entity_, and the legal entity that receives the service or product is called the _borrowing legal entity_.

The following illustration shows a typical scenario where two legal entities, Contoso Robotics USA (the borrowing legal entity/ resourcing company) and Contoso Robotics UK (the lending legal entity/ owning company) share resources to deliver a project for customer Adventure works. For this scenario, Contoso Robotics USA is contracted to deliver the work to customer Adventure Works.

![](RackMultipart20201119-4-1k494c8_html_49ac0cb03196381.gif) ![](RackMultipart20201119-4-1k494c8_html_cddd4772c20951a8.png)

Project Operations uses the following flow to process intercompany transactions:

1. Intercompany time or expense transactions are recorded by resources from lending legal entity booking time and expense against projects in borrowing legal entity.
2. Time/ expense costs are recorded in lending company, using resourcing organizational unit cost price list.
3. Intercompany unbilled sale transactions are recorded in lending company, using contracting organizational unit cost price list.
4. Unbilled revenue is recorded in borrowing company using project contract sales price list. Customer can be billed as soon as unbilled revenue is recorded and doesn&#39;t have to wait until intercompany invoice processing is completed.
5. Intercompany customer invoices are created on a periodic basis in lending company either manually or by using a periodic automated process. Single invoice can be created per borrowing legal entity or separate invoices can be created by project.
6. At the time Intercompany customer invoice is posted in lending legal entity, corresponding pending vendor invoice is created in borrowing legal entity. Posting pending vendor invoice records cost to project subledger.

See the following diagram illustrating intercompany invoicing related accounting events and expected postings to general ledger.

![](RackMultipart20201119-4-1k494c8_html_a7e6527e976415bb.png)

Learn more about intercompany invoicing:

- Configure intercompany invoicing
- Record intercompany transactions
- Create intercompany customer and vendor invoices
