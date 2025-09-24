---
title: Enable notifications for long-running processes
description: This article provides information about how Dynamics 365 Project Operations handles long running jobs.
author: abriccetti
ms.date: 09/24/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Enable notifications for long-running processes

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Core, Project Operations Integrated with ERP_

The time to complete certain operations in Dynamics 365 Project Operations ranges from a few seconds to several minutes, depending on the operation and data size. In these scenarios, the UI provides two options for its behavior while the operation completes. The **Enable notifications for long-running processes** setting in the **Project parameters** menu controls this behavior. If you set this option to **No**, a spinner displays and you can't use the UI until the job finishes or the UI times out after two minutes. UI timeouts don't cancel jobs, they continue to completion in the background. If you set the option to **Yes** and enable it for a specific job, a ribbon message displays stating that the long-running job started. When the job finishes, the you get an in-app notification.

## Available processes

When you set **Enable notifications for long-running processes** to **Yes**, the **Select jobs for notification** setting is unlocked. Specify which processes run asynchronously with the new notifications and which processes use the legacy UI lockout experience. The following processes are currently available for this feature (with more processes potentially added in the future):

- Closing a quote as won
- Closing a quote as lost
- Confirm an order (project contract)
- Confirm an invoice
- Create invoice
- Correct invoice
- Add invoice line details
- Copy price list
- Update estimate prices on project

When you set **Enable notifications for long-running processe** to **Yes**, you have two options for controlling which processes use this experience. You can individually add any item from the preceding list to the **Select jobs for notification** list to use the notification experience. Alternatively, leave this field blank to let all available processes use the notification experience. A blank **Select jobs for notification** list automatically applies the notifications experience to any newly added processes. If the list isn't blank, include any newly added process in **Select jobs for notification**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
