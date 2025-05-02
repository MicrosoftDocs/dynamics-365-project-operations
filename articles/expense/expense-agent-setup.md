---
title: Expense Agent Installation and Setup
description: Steps to install and setup the Expense Agent.
author: alexeiantao
ms.author: alexeiantao
ms.date: 05/02/2025
ms.topic: conceptual
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Overview

[!INCLUDE[banner](../includes/banner.md)]

The Expense Agent brings together capabilities from Microsoft Dynamics 365 Finance and Operations, Microsoft Copilot Studio, Power Automate, and Dataverse to automate expense processing workflows using AI. It enables your system to process receipts and generate expense lines and reports for users—saving time and reducing manual effort. It uses standard Microsoft connectors to integrate with Outlook, Teams, user calendars, and the Finance and Operations environment via Dataverse virtual entities.

The Expense Agent includes multiple flows, three of which serve as core orchestrators:

1. **Process Emails** – Scans a configured mailbox folder every hour and stores the attachments as unattached receipts in Dynamics 365.
2. **Extract Receipt IDs** – Picks up newly added receipts and triggers the agent to extract details.
3. **Process Expense Report** – Converts extracted receipt data into structured expense lines and generates reports, based on the configuration set in the application.

The agent also supports Microsoft Teams integration, allowing adaptive cards to be sent for review and submission of expenses.

The agent relies on several Power Platform connectors. These are automatically referenced within the provided Power Automate flows:

- **Outlook (Office 365)** – Accesses the shared mailbox to fetch receipts.
- **Dataverse (Virtual Entities)** – Integrates with Dynamics 365 Finance and Operations entities.
- **Microsoft Copilot Studio** – Invokes AI models to extract receipt information.
- **Microsoft Teams** – Sends adaptive cards for user interactions (if Teams integration is enabled).
- **Microsoft 365 Users** – Retrieves user calendar details (optional, if receipt parsing is context-aware).

Installing and setting up the Expense Agent involves the following steps:

1. Install Copilot for Finance and Operations  
2. Activate the agent within Dynamics 365 Finance and Operations
3. Create an expense user account for agent execution  
4. Assign permissions in Finance and Operations and Dataverse  
5. Set up a shared mailbox for email-based receipt collection  
6. Configure and set up the agent, either manually or using PowerShell  
7. Enable Microsoft Teams integration (optional)

---

### Step 1: Install Copilot for Finance and Operations

The Expense Agent is delivered as part of the **Copilot for Finance and Operations** package. Once this package is installed in your environment, all required assets—including the agent, environment variables, and Power Automate flows—become available automatically.

For detailed guidance on enabling Copilot in your environment, refer to the official documentation:  
🔗 [Enable Copilot features in Finance and Operations](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/copilot/enable-copilot)

Each of these steps is described in detail in the sections that follow.
To complete the steps described in this article, you must have **System administrator** or **System customizer** access in the Power Platform admin center, **System administrator** access in Dynamics 365 Finance and Operations, and **Exchange administrator** access in Microsoft 365 to configure the shared mailbox. If you plan to enable Teams integration, you will also need the required permissions in the **Teams admin center**.

---

### Step 2: Activate the Agent in Finance and Operations

After installing the package, you can activate the Expense Agent from the Finance and Operations web application.

First, ensure that the **(Production Ready Preview) Agent Management** feature is enabled under **Feature Management**.

Then, navigate to:

**Expense Management > Setup > Expense Management Parameters > (Production Ready Preview) Expense Entry Agent**

This opens the configuration screen.

Enable the agent for the current legal entity and configure the run frequency as either **daily** or **weekly**. You can also choose to group expenses by **Trip** or **Project** using the *Expense group by* setting.

---

### Step 3: Set Up the Agent User

It is recommended to create a dedicated expense agent user to ensure that the agent runs independently of any employee’s identity. This helps with security, manageability, and long-term maintainability. While it is possible to use an existing user account with sufficient privileges, using a system-owned identity is the preferred approach.

#### A. Create the User in Azure AD

1. Go to the [Azure Portal](https://portal.azure.com/) and create a new user under **Microsoft Entra ID** (formerly Azure Active Directory).

#### B. Add the User to the Power Platform Environment

1. Go to the [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/) and select the appropriate environment.
2. Click **See all users**, then **Add user**, and select the newly created agent user.

#### C. Assign Required Roles in the Power Platform Admin Center

1. In the same **Power Platform Admin Center**, select the environment.
2. Locate the agent user and click **Manage Roles**.
3. Assign the following roles:
   - **System Customizer**
   - **Expense AI Agent Role**
   - **Finance and Operations Agent Configuration Role**

These roles provide access to Dataverse and Power Automate components required for the agent to function.

#### D. Assign System Administrator Role in Finance and Operations

1. In the **Finance and Operations** portal, go to **System Administration > Users**.
2. Create a new user record for the agent user.
3. Assign the **System Administrator** role.
4. Click **Save** to persist the configuration.

---

### Step 4: User Permissions

To successfully configure and run the Expense Agent, the designated agent user must be granted the following permissions:

#### Finance and Operations Roles

- **System Administrator**  
  Required to allow the agent to create and manage expense entries within the Finance and Operations environment.

#### Dataverse Roles

- **System Customizer**  
- **Expense AI Agent Role**  
- **Finance and Operations Agent Configuration Role**

These roles enable the agent to interact with Power Automate flows, environment variables, and virtual entities connected to Dynamics 365 Finance.

#### Shared Mailbox Access

The agent user must also have the following Microsoft Graph permission:

- `Mail.Shared.Read` — Allows the agent to read receipts from the configured shared mailbox during flow execution.

---

### Step 5: Set Up the Shared Mailbox

The Expense Agent uses a shared mailbox to receive receipt emails. This mailbox must be created and configured in the Microsoft 365 Admin Center by a user with the **Exchange Admin** role.

#### To create and configure the shared mailbox:

1. Go to the [Microsoft 365 Admin Center](https://admin.microsoft.com/) and sign in with an Exchange Admin account.
2. In the left-hand navigation pane, select **Teams & Groups > Shared mailboxes**.  
   If you don’t see it immediately, select **Show all** to expand the list.
3. Click **Add a shared mailbox**.
4. Enter a name and email address for the shared mailbox.  
   *Recommended format:* `expenseagent@contoso.com`
5. Click **Save changes**. It may take a few minutes before member management becomes available.
6. Under **Next steps**, choose **Add members to this mailbox**.
7. Select the agent user (and any others who should monitor the mailbox), then click **Add** and **Close**.

Once the mailbox is set up, provide its email address and the folder path (default: `Inbox`) as environment variables when configuring the Expense Agent.

---

### Step 6: Expense Agent Setup

#### Option 1: Using PowerShell Script (Recommended)

Setting up the agent manually involves creating and linking connections, enabling Power Automate flows, and publishing the solution — a process that can be time-consuming and error-prone. To simplify this, you can use a PowerShell script and configuration file (`AgentConfig.json`) to automate the setup.

#### What the Script Does

The PowerShell script automates:

- Updating required environment variables
- Linking Power Platform connections with solution connection references
- Enabling all Power Automate flows required by the Expense Agent
- Publishing the Copilot agents
- Publishing the Dataverse solution

#### Configuration File Example (`AgentConfig.json`)

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
#### Creating the Connections

1. Go to the [Power Apps Maker Portal](https://make.powerapps.com/) and select your environment.
2. Navigate to **Connections**.
3. Click **New connection** and select the appropriate connector (e.g., Outlook, Teams, etc.).
4. Once created, copy the **connection ID** and paste it into the `AgentConfig.json` file under the appropriate connector entry.

#### Running the Script

Once your configuration is ready, execute the script using the following command:

```powershell
.\setup.ps1 -environmentId "<your-environment-id>" -dataverseUrl "<your-dataverse-url>" -ConfigModuleName "Expense"
```
**The script will:**

- Set environment variables  
- Verify and link connection references  
- Enable Power Automate flows  
- Publish the required Copilot agents  
- Publish the Dataverse solution  

Upon successful execution, the Expense Agent will be fully configured and ready to use.

---

#### Option 2: Manual Setup Using Maker Portal (No PowerShell)

If you prefer not to use the PowerShell script, you can manually configure the Expense Entry Agent through the Power Apps Maker Portal. This process involves updating environment variables, enabling Power Automate flows, and publishing the solution.

#### 1. Update Environment Variables

Update the following environment variables to configure the agent:

1. Go to the [Power Apps Maker Portal](https://make.powerapps.com/) and select your environment.
2. Click **Solutions**, then open the **Default Solution** (or the solution where the agent is installed).
3. Navigate to **Environment Variables**, and set the following values:

| Variable Name                             | Description                                                                                     |
|------------------------------------------|-------------------------------------------------------------------------------------------------|
| `Expense Agent Outlook Folder Path`      | Folder path within the shared mailbox to monitor (default is `Inbox`).                         |
| `Expense Agent Shared Mailbox Address Id`| Email address of the shared mailbox. Use `NA` if using the signed-in user's mailbox.            |
| `Finance and Operations Instance Url`    | Finance and Operations environment URL (e.g., `https://xxxxx.operations.dynamics.com`).         |

#### 2. Enable Power Automate Flows

The Expense Entry Agent relies on the following Power Automate flows:

- `expense entry retry check`  
- `expense configuration`  
- `get expense outlook folder`  
- `generate expense report`  
- `send expense report adaptive card`  
- `process emails`  
- `extract unattached receipt ids for copilot invocation`  
- `extract unattached receipt output using dataverse plugin`  
- `generate expense line`  
- `generate expense line without project id and status id`  
- `identify project ids`  
- `user calendar events`  
- `process expense report using copilot`

**To enable these flows:**

1. Go to [Power Automate](https://make.powerautomate.com/) and select your environment.
2. Click **My Flows** and locate each of the Expense Agent flows listed above.
3. For each flow:
   - Click **Edit**
   - Switch to the **Old Designer** by toggling off the "New Designer"
   - Authenticate any required connections (until green checkmarks appear)
   - Click **Continue** → **Save**
   - Click **Turn On** to enable the flow

Repeat this process for each of the 13 flows listed.


#### 3. Publish the Solution

After all variables and flows are configured:

1. In the **Power Apps Maker Portal**, go to **Solutions**.
2. Select your environment and solution.
3. Click **Publish all customizations**.

Upon completing these steps, the Expense Entry Agent will be fully configured and ready to use without requiring any scripts.

---

### Step 7: Expense Agent – Teams Enablement

To enable Teams-based communication using the Expense Entry Agent, you must add the Microsoft Teams channel to the agent through the Power Apps Maker Portal. This allows the agent to send adaptive cards and receive input via Teams.


#### Steps to Enable the Microsoft Teams Channel:

1. Go to the [Power Apps Maker Portal](https://make.powerapps.com/) and open the **Agents** tab.
2. Select **Expense Entry Agent**.
3. In the agent view, go to the **Channels** tab and select **Microsoft Teams**.
4. Click **Add channel** to enable Teams integration.  
   👉 [View Microsoft documentation for this step](https://learn.microsoft.com/en-us/microsoft-copilot-studio/publication-add-bot-to-microsoft-teams#open-the-configuration-panel-for-the-microsoft-teams-channel)

#### Configure Teams App Availability:

1. After the Teams app is created, click **Availability Options**.
2. Choose to share the app with:
   - Specific users within the organization, or  
   - The entire organization
3. Submit the app for approval.

#### Publish in Teams Admin Center:

1. Go to the [Teams Admin Center](https://admin.teams.microsoft.com/).
2. Publish the app for approved use.
3. Assign **App Setup Policies** to users.
4. If needed, update **Permission Policies** to allow agent access based on your organization’s Teams settings.

📘 For more information, refer to the official documentation:  
[Add a bot to Microsoft Teams](https://learn.microsoft.com/en-us/microsoft-copilot-studio/publication-add-bot-to-microsoft-teams)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
