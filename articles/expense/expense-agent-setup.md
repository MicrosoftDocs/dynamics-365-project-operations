---
title: Expense Agent Installation and Setup
description: Learn about the steps to install and set up the Expense Agent.
author: alexeiantao
ms.author: alexeiantao
ms.date: 05/02/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Overview

[!INCLUDE[banner](../includes/banner.md)]

The Expense Agent brings together capabilities from Microsoft Dynamics 365 Project Operations, finance and operations apps, Microsoft Copilot Studio, Microsoft Power Automate, and Microsoft Dataverse to automate expense processing workflows using AI. The Expense Agen enables your system to process receipts and generate expense lines and reports for users to save time and reduce manual effort. It uses Microsoft Power Platform Connectors to integrate with Outlook, Microsoft Teams, user calendars, and the finance and operations apps environment via Dataverse virtual entities.

The Expense Agent includes multiple flows, three of which serve as core orchestrators:

1. **Process Emails** – Scans a configured mailbox folder every hour and stores the attachments as unattached receipts in Dynamics 365.
2. **Extract Receipt IDs** – Picks up newly added receipts and triggers the agent to extract details.
3. **Process Expense Report** – Converts extracted receipt data into structured expense lines and generates reports, based on the configuration set in the application.

The agent also supports Teams integration that allows you to send adaptive cards for review and submission of expenses.

The agent relies on several Power Platform connectors. These connectors are automatically referenced within the provided Microsoft Power Automate flows:

- **Outlook (Office 365)** – Accesses the shared mailbox to fetch receipts.
- **Dataverse (Virtual Entities)** – Integrates with Dynamics 365 Finance and Operations entities.
- **Microsoft Copilot Studio** – Invokes AI models to extract receipt information.
- **Microsoft Teams** – Sends adaptive cards for user interactions (if Teams integration is enabled).
- **Microsoft 365 Users** – Retrieves user calendar details (optional, if receipt parsing is context-aware).

Installing and setting up the Expense Agent involves the following steps:

1. Install Copilot for finance and operations apps.  
2. Activate the agent within Dynamics 365 Finance and Operations.
3. Create an expense user account for agent execution.  
4. Assign permissions in finance and operations apps and Dataverse.  
5. Set up a shared mailbox for email-based receipt collection.  
6. Configure and set up the agent, either manually or using Windows PowerShell.  
7. Enable Microsoft Teams integration (optional).

Each of these steps is described in detail in the sections that follow.

## Prerequisites

To complete the steps described in this article, you must have **System administrator** or **System customizer** access in the Power Platform admin center, **System administrator** access in Dynamics 365 Finance and Operations, and **Exchange administrator** access in Microsoft 365 to configure the shared mailbox. If you plan to enable Teams integration, you also need the required permissions in the **Teams admin center**.

### Step 1: Install Copilot for finance and operations apps

The Expense Agent is delivered as part of the **Copilot for Finance and Operations** package. Once this package is installed in your environment, all required assetsincluding the agent, environment variables, and Power Automate flowsbecome available automatically.

Learn more about enabling Copilot in your environment in [Enable Copilot capabilities in finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/copilot/enable-copilot).

### Step 2: Activate the Agent in finance and operations apps

To activate the Agent in finance and operations apps, follow these steps.

1. After installing the package, activate the Expense Agent from the finance and operations web application.
1. Go to **Feature Management** and ensure **(Production Ready Preview) Agent Management** is enabled.
1. Go to **Expense Management > Setup > Expense Management Parameters > (Production Ready Preview) Expense Entry Agent**.
1. Enable the agent for the current legal entity and configure the run frequency as either **daily** or **weekly**. You can also choose to group expenses by **Trip** or **Project** using the *Expense group by* setting.

### Step 3: Set up the Agent user

Create a dedicated expense agent user to ensure that the agent runs independently of any employee’s identity. This helps with security, manageability, and long-term maintainability. While it's possible to use an existing user account with sufficient privileges, using a system-owned identity is the preferred approach.

#### A. Create the user Microsoft Azure Active Directory (Azure AD DS)

1. Go to the [Azure portal](https://portal.azure.com/) and create a new user under **Microsoft Entra ID** (formerly Azure Active Directory).

#### B. Add the user to the Power Platform environment

1. Go to the [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/) and select the appropriate environment.
1. Select **See all users**, then **Add user**, and select the newly created agent user.

#### C. Assign required roles in the Power Platform admin center

1. In the same **Power Platform admin center**, select the environment.
1. Locate the agent user and select **Manage Roles**.
1. Assign the following roles:
   - **System Customizer**
   - **Expense AI Agent Role**
   - **Finance and Operations Agent Configuration Role**

These roles provide access to Dataverse and Power Automate components required for the agent to function.

#### D. Assign system administrator role in finance and operations apps

1. In the **Finance and Operations** portal, go to **System Administration > Users**.
1. Create a new user record for the agent user.
1. Assign the **System Administrator** role.
1. Select **Save** to persist the configuration.

### Step 4: Grant user permissions

To successfully configure and run the Expense Agent, the designated agent user must be granted the following permissions:

#### Finance and operations roles

- **System Administrator**  
  Required to allow the agent to create and manage expense entries within the Finance and Operations environment.

#### Dataverse roles

- **System Customizer**  
- **Expense AI Agent Role**  
- **Finance and Operations Agent Configuration Role**

These roles enable the agent to interact with Power Automate flows, environment variables, and virtual entities connected to Dynamics 365 Finance.

#### Shared mailbox access

The agent user must also have the Microsoft Graph permission `Mail.Shared.Read` that allows the agent to read receipts from the configured shared mailbox during flow execution.

### Step 5: Set Up the shared mailbox

The Expense Agent uses a shared mailbox to receive receipt emails. This mailbox must be created and configured in the Microsoft 365 Admin Center by a user with the **Exchange Admin** role.

To create and configure the shared mailbox, follow these steps.

1. Go to the [Microsoft 365 Admin Center](https://admin.microsoft.com/) and sign in with an Exchange Admin account.
1. In the left-hand navigation pane, select **Teams & Groups > Shared mailboxes**.  
   If you don’t see it immediately, select **Show all** to expand the list.
1. Select **Add a shared mailbox**.
1. Enter a name and email address for the shared mailbox.  
   *Recommended format:* `expenseagent@contoso.com`
1. Select **Save changes**. It may take a few minutes before member management becomes available.
1. Under **Next steps**, choose **Add members to this mailbox**.
1. Select the agent user (and any others who should monitor the mailbox), then select **Add** and **Close**.

Once the mailbox is set up, provide its email address and the folder path (default: `Inbox`) as environment variables when configuring the Expense Agent.

### Step 6: Set up Expense Agent

You can set up Expense Agent using one of two options:
 - Option 1: Using PowerShell Script (Recommended)
 - Option 2: Manual Setup Using Maker Portal (No PowerShell)

#### Option 1: Using PowerShell Script (recommended)

Setting up the agent manually involves creating and linking connections, enabling Power Automate flows, and publishing the solution — a process that can be time-consuming and error-prone. You can use a PowerShell script and configuration file (`AgentConfig.json`) to automate the setup.

The PowerShell script automates:

- Updating required environment variables.
- Linking Power Platform connections with solution connection references.
- Enabling all Power Automate flows required by the Expense Agent.
- Publishing the Copilot agents.
- Publishing the Dataverse solution.

##### Configuration File Example (`AgentConfig.json`)

Before running the script, configure the file with values relevant to your environment:

```json
{
  "modules": {
    "Expense": {
      "environmentVariables": {
        "msdyn_ExpenseFnoInstanceUrl": "<your-finance-url>",
        "msdyn_ExpenseAgentOutlookFolderPath": "Inbox",
        "msdyn_ExpenseAgentMailboxAddressId": "NA"
      },
      "connectors": [
        {
          "Name": "shared_commondataserviceforapps",
          "id": "<your-dataverse-connection-id>",
          "connectionRefName": "msdyn_sharedcommondataserviceforapps_xxxx",
          "DisplayName": "Dataverse"
        },
        {
          "Name": "shared_office365",
          "id": "<your-outlook-connection-id>",
          "connectionRefName": "msdyn_sharedoffice365_xxxx",
          "DisplayName": "Office 365 Outlook"
        },
        {
          "Name": "shared_office365users",
          "id": "<your-user-connection-id>",
          "connectionRefName": "msdyn_sharedoffice365users_xxxx",
          "DisplayName": "Office 365 Users"
        },
        {
          "Name": "shared_teams",
          "id": "<your-teams-connection-id>",
          "connectionRefName": "msdyn_sharedteams_xxxx",
          "DisplayName": "Microsoft Teams"
        },
        {
          "Name": "shared_microsoftcopilotstudio",
          "id": "<your-copilot-connection-id>",
          "connectionRefName": "msdyn_sharedmicrosoftcopilotstudio_xxxx",
          "DisplayName": "Microsoft Copilot Studio"
        }
      ],
      "flows": [
        "expense entry retry check",
        "expense configuration",
        "get expense outlook folder",
        "generate expense report",
        "send expense report adaptive card",
        "process emails",
        "extract unattached receipt ids for copilot invocation",
        "extract unattached receipt output using dataverse plugin",
        "generate expense line",
        "generate expense line without project id and status id",
        "identify project ids",
        "user calendar events",
        "process expense report using copilot"
      ],
      "agents": [
        "msdyn_ExpenseEntryAgent",
        "msdyn_ExpenseReportAgent"
      ]
    }
  }
}
```

##### Create the connections

To create the connections, follow these steps.

1. Go to the [Power Apps Maker Portal](https://make.powerapps.com/) and select your environment.
1. Navigate to **Connections**.
1. Select **New connection** and select the appropriate connector (for example, Outlook, Teams, etc.).
1. Once created, copy the **connection ID** and paste it into the `AgentConfig.json` file under the appropriate connector entry.

##### Run the script

Once your configuration is ready, run the script using the following command:

```powershell
.\setup.ps1 -environmentId "<your-environment-id>" -dataverseUrl "<your-dataverse-url>" -ConfigModuleName "Expense"
```

The script will:

- Set environment variables  
- Verify and link connection references  
- Enable Power Automate flows  
- Publish the required Copilot agents  
- Publish the Dataverse solution  

After the script runs successfully, the Expense Agent is fully configured and ready to use.


#### Option 2: Manual Setup Using Maker Portal (No PowerShell)

If you prefer not to use the PowerShell script, you can manually configure the Expense Entry Agent through the Power Apps Maker Portal. This process involves updating environment variables, enabling Power Automate flows, and publishing the solution.

##### 1. Update Environment Variables

To configure the agent, update the following environment variables.

1. Go to the [Power Apps Maker Portal](https://make.powerapps.com/) and select your environment.
1. Select **Solutions**, then open the **Default Solution** (or the solution where the agent is installed).
1. Navigate to **Environment Variables**, and set the following values:

| Variable Name                             | Description                                                                                     |
|------------------------------------------|-------------------------------------------------------------------------------------------------|
| `Expense Agent Outlook Folder Path`      | Folder path within the shared mailbox to monitor (default is `Inbox`).                         |
| `Expense Agent Shared Mailbox Address Id`| Email address of the shared mailbox. Use `NA` if using the signed-in user's mailbox.            |
| `Finance and Operations Instance Url`    | Finance and Operations environment URL (for example, `https://xxxxx.operations.dynamics.com`).         |

##### 2. Enable Power Automate Flows

The Expense Entry Agent relies on the following Power Automate flows:

- `expense entry retry check`  
- `expense configuration`  
- `get expense outlook folder`  
- `generate expense report`  
- `send expense report adaptive card`  
- `process emails`  
- `extract unattached receipt ids for copilot invocation`  
- `extract unattached receipt output using Dataverse plugin`  
- `generate expense line`  
- `generate expense line without project id and status id`  
- `identify project ids`  
- `user calendar events`  
- `process expense report using copilot`

To enable these flows, follow these steps.

1. Go to [Power Automate](https://make.powerautomate.com/) and select your environment.
1. Select **My Flows** and locate each of the Expense Agent flows in the previous list.
1. For each flow:
   - Select **Edit**
   - Switch to the **Old Designer** by toggling off the "New Designer"
   - Authenticate any required connections (until green checkmarks appear)
   - Select **Continue** → **Save**
   - Select **Turn On** to enable the flow

Repeat this process for each of the 13 flows listed.


##### 3. Publish the solution

After all variables and flows are configured:

1. In the **Power Apps Maker Portal**, go to **Solutions**.
1. Select your environment and solution.
1. Select **Publish all customizations**.

After you complete these steps, the Expense Entry Agent is fully configured and ready to use without requiring any scripts.

### Step 7: Enable Expense Agent

To enable Teams-based communication using the Expense Entry Agent, you must add the Microsoft Teams channel to the agent through the Power Apps Maker Portal. Adding the channel allows the agent to send adaptive cards and receive input via Teams.

#### Enable the Microsoft Teams channel

To enable the Microsoft Teams Channel, follow these steps.

1. Go to the [Power Apps Maker Portal](https://make.powerapps.com/) and open the **Agents** tab.
1. Select **Expense Entry Agent**.
1. In the agent view, go to the **Channels** tab and select **Microsoft Teams**.
1. Select **Add channel** to enable Teams integration. Learn more in [View Microsoft documentation for this step](/microsoft-copilot-studio/publication-add-bot-to-microsoft-teams#open-the-configuration-panel-for-the-microsoft-teams-channel).

#### Configure Teams app availability

To configure Teams app availability, follow these steps.

1. After the Teams app is created, select **Availability Options**.
1. Choose to share the app with:
   - Specific users within the organization, or  
   - The entire organization
1. Submit the app for approval.

#### Publish in Teams admin center

To publish in Teams admin center, follow these steps.

1. Go to the [Teams Admin Center](https://admin.teams.microsoft.com/).
1. Publish the app for approved use.
1. Assign **App Setup Policies** to users.
1. If needed, update **Permission Policies** to allow agent access based on your organization’s Teams settings.

Learn more in [Add a bot to Microsoft Teams](/microsoft-copilot-studio/publication-add-bot-to-microsoft-teams).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
