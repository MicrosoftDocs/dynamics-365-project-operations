---
title: Enable notifications for long-running processes
description: This article provides information about how D365 Project Operations handles long running jobs.
author: abriccetti
ms.date: 09/17/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Enable Notifications for long-running processes

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Core, Project Operations Integrated with ERP_

The time it takes to complete certain operations in D365 Project Operations can vary from a few seconds to several minutes, depending on the operation and the size of the data involved. In these scenarios there are two options for how the UI will behave while the operation completes based on the setting: "Enable notifications for long-running processes" in the project parameters menu. When this setting is set to no,users are shown a spinner and locked out of the UI until the job completes or teh UI times out after two minutes. UI time outs do not cancel jobs; they will continue to completion in the background. When the setting is set to yes, and the and enabled for the specific job the user will be shown a ribbon message stating the long-running job has been kicked off, and upon job completion they will receive an in-app notification of it's completion.

## Processes

When the "Enable notifications for long-running processes" setting is set to yes, an additional setting is unlocked: "Select jobs for notification". Here users can specify which processes they want to run asynchronously with the new notifications, and which they want to use the legacy UI lockout experience. The following processes are currently available for this process (with more to be added in the future):

- Closing a quote as won
- Closing a quote as lost
- Confirm an order (project contract)
- Confirm an invoice
- Create invoice
- Correct invoice
- Add invoice line details
- Copy price list
- Update estimate prices on project

  If the "Enable notifications for long-running processes" is set to yes, users have two options on controlling which processes use this experience. THey can individually add any item from above to the "Select jobs for notification" list and they will use the notification experience. Alternatively, they can leave this field blank and all available processes will use the notification experience. As new processes are added, a blank "Select jobs for notification" list will automatically use the notifications experience. If the list is not blank, any newly added process will need to be included in "Select jobs for notification".

[!INCLUDE[footer-include](../includes/footer-banner.md)]
