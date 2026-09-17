---
title: Prerequisites for core package import
description: Review the sign-in, connectivity, and user name requirements administrators must confirm before importing Project Operations Core demonstration data packages.
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
ms.reviewer: johnmichalak
ms.date: 09/17/2026
---

# Prerequisites for core package import

[!INCLUDE [banner](../includes/banner.md)]

Before you import either the Setup data package or the Transactional data package, confirm that your sign-in, connectivity, and downloaded files meet the requirements described in this article. Completing these checks first helps you avoid interruptions partway through the import process described in [Import the Setup data package](import-setup-data-package.md) and [Import the Transactional data package](import-transactional-data-package.md).

## Confirm sign-in and access requirements

Have the following ready before you start:

* A valid Dynamics 365 sign-in with the **System Administrator** or **System Customizer** security role.
* Internet access, which is required for online environments.
* The deployment package files, downloaded to the computer you'll run the import from.

## Check that the user has a full name

Package Deployer runs under the signed-in user, and that user must have both a first name and a last name set. Follow these steps to confirm the account is ready:

1. Open the user record for the account you'll use to run the import.
1. Confirm that the **First name** and **Last name** fields are both filled in.
1. If either field is blank, add the missing value and save the record before continuing.

:::image type="content" source="media/core-package-new-user.png" alt-text="Screenshot of a user record showing the First name and Last name fields.":::

## Next steps

Continue to [Import the Setup data package](import-setup-data-package.md).
