---
title: Configure accounting for internal projects
description: This article provides information about how to set up accounting practices for internal projects in Project Operations.
author: ryansandness
ms.author: ryansandness
ms.date: 02/26/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Configure accounting for internal projects

_**Applies To:** Project Operations Integrated with ERP_

By using internal projects, companies can track costs related to activities that aren't billable to a customer. Examples of internal projects include:

- Developing a product, such as a mobile app, and tracking the costs associated with the development.
- Managing pre-sale time and expenses. This pre-sale internal project can later convert to a billable project if the quote is won.

Dynamics 365 Project Operations treats any project not associated with a contract as internal. Project cost and revenue profiles don't determine accounting rules for the project. Always post internal project costs by using profit and loss principles. Define ledger accounts for postings on the **Ledger posting setup** page.

- Time transactions post by debiting the **Cost** account and crediting the **Payroll allocation** account.
- Expense transactions post by debiting the **Cost** account and crediting the **Offset account for expense**.
- Item transactions post by debiting the **Cost** account and crediting the **Cost - Item** account.

After you post transactions to the project, if you associate the project with a project contract, the system reverses all accumulated transactions and creates new billable transactions. The billable transactions follow the accounting rules defined in the respective project cost and revenue profile.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
