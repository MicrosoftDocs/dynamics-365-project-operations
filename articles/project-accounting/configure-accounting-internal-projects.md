---
title: Configure accounting for internal projects
description: This article provides information about how to set up accounting practices for internal projects in Project Operations.
author: ryansandness
ms.author: ryansandness
ms.date: 05/24/2024
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Configure accounting for internal projects

_**Applies To:** Project Operations Integrated with ERP_

Internal projects allow companies track cost related to activities that aren't being billed to a customer. Examples of internal projects include:

- Developing a product, such as a mobile app, and tracking the cost associated with the development.
- Managing pre-sale time and expense. This pre-sale internal project can be converted later to a billable project if quote is won.

Any project not associated with a contract in Dynamics 365 Project Operations is treated as internal. Project cost and revenue profiles aren't used to determine accounting rules for the project. Internal project cost is always posted using profit and loss principles. Ledger accounts for postings are defined on the **Ledger posting setup** page.

- Time transactions are posted by debiting the **Cost** account and crediting the **Payroll allocation** account.
- Expense transactions are posted by debiting the **Cost** account and crediting the **Offset account for expense**.
- Item transactions are posted by debiting the **Cost** account and crediting the **Cost - Item** account.

After transactions are posted to the project, if the project is associated with a project contract, the system reverses all accumulated transactions and creates new billable transactions. The billable transactions follow the accounting rules defined in respective Project cost and revenue profile.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
