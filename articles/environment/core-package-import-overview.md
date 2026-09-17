---
title: Core package import overview
description: Learn what the Project Operations core package import process does and the order of articles administrators follow to deploy Project Operations demonstration data into a Dynamics 365 environment.
ms.topic: overview
author: MichelleDevaney
ms.author: midevane
ms.reviewer: johnmichalak
ms.date: 09/17/2026
---

# Core package import overview

[!INCLUDE [banner](../includes/banner.md)]

The core package import process lets administrators deploy Project Operations demonstration data into a Dynamics 365 environment by using Package Deployer. The process imports two predefined data packages that add setup and sample transactional records, so you can explore Project Operations scenarios, demonstrate the application, and evaluate its capabilities without creating representative data manually.

> [!IMPORTANT]
> This demonstration data is for demonstration and evaluation purposes only. Deploy it only to non-production Dynamics 365 environments; it isn't intended for production use.

## What core package import does

Core package import deploys two packages into your environment: **PD - PO Core - Setup Data** and **PD - PO Core - Transactional Data**. The Setup data package creates the foundational setup records that Project Operations scenarios depend on. The Transactional data package then adds sample transactional records, such as projects, that build on those setup records.

You must import the Setup data package before the Transactional data package. The transactional records depend on records that the Setup package creates, so importing the packages out of order causes the import to fail. After you import and validate both packages, your environment contains the setup and sample transactional records needed to use the Project Operations demonstration scenarios.

## Steps in this process

Work through the following articles in order. Each article covers one step and ends by pointing you to the next one.

1. [Prerequisites for core package import](data-package-prerequisites.md) — confirm your sign-in role, internet access, and downloaded package files before you start.
1. [Import the Setup data package](import-setup-data-package.md) — import **PD - PO Core - Setup Data** by using Package Deployer, and validate the result.
1. [Import the Transactional data package](import-transactional-data-package.md) — import **PD - PO Core - Transactional Data** by using Package Deployer, and validate the result.
