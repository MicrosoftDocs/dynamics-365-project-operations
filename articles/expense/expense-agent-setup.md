---
title: Set up the Expense Agent (preview)
description: Learn how to install and set up the Expense Agent to automate expense processing workflows by using AI.
author: ajitchandran
ms.author: ajitchandran
ms.date: 05/13/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Set up the Expense Agent (Preview)

[!INCLUDE [banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies to Dynamics 365 Project Operations Integrated with ERP and Dynamics 365 Project Operations for manufacturing**_

The Expense Agent brings together capabilities from Microsoft Dynamics 365 Project Operations, finance and operations apps, Microsoft Copilot Studio, Power Automate, and Dataverse to automate expense processing workflows by using AI. This feature helps save time and reduce manual effort by enabling your system to process receipts and generate expense lines and expense reports for users. It uses Microsoft Power Platform connectors for integration with Outlook, Microsoft Teams, user calendars, and the finance and operations apps environment via Dataverse virtual entities.

The Expense Agent includes multiple flows, three of which serve as core orchestrators:

- **Process Emails** – This flow scans a configured mailbox folder every hour and stores the attachments as unattached receipts in Dynamics 365 Finance.
- **Extract Receipt IDs** – This flow picks up unattached receipts and triggers the agent to extract receipt details and create an unattached expense line.
- **Process Expense Report** – This flow converts unattached expense lines and generates expense reports, based on the **Group reports by** configuration that you set in the application for each legal entity.

Additionally, the agent integrates with Microsoft Teams, enabling the use of adaptive cards for expense report review and submission.

The agent relies on several Microsoft Power Platform connectors. These connectors are automatically referenced in the Power Automate flows that are provided.

- **Outlook (Office 365)** – This connector accesses the shared mailbox to extract receipts.
- **Dataverse (Virtual Entities)** – This connector integrates with finance and operations apps via virtual entities.
- **Microsoft Copilot Studio** – This connector invokes AI models to extract receipt information.
- **Microsoft Teams** – This connector sends adaptive cards for user interactions (if Teams integration is enabled).
- **Microsoft 365 Users** – This connector retrieves user calendar details (optional, if receipt parsing is context-aware).

## Prerequisites

1. **Finance and operations environment:** You need at least version 10.0.45 (10.0.2345.170 and later), 10.0.46 (10.0.2428.108 and later), or 10.0.47 (10.0.2527.38 and later) of the finance and operations environment to install the agent.
1. **Roles required to set up the Expense Agent user:** To complete the steps in this article, you must be the system administrator of the organization and have the following roles to set up the expense agent user for installing the Expense Agent.

| System | Role | Comments |
|---|---|---|
| Power Platform admin center | System administrator | <ol><li>Go to [Power Platform admin center](https://admin.powerplatform.com/)</li> <li>Go to **Manage** on the left pane. Select **Environments**, and then select your environment.</li> <li>On the **Access** > **Users** section, select **See all**.</li> <li>Select a user then select **Manage roles**, and add the role.</li></ol> |
| Finance and operations | System administrator | <ol><li>Open the finance and operations URL for your environment environment.</li> <li>Go to **Module** > **System** **administration** > **Users**, and select a user.</li> <li>Select **Add role** – System administrator.</li></ol> |
| Microsoft 365 | Exchange Administrator and User Administrator | <ol><li>Go to [Microsoft 365 admin center](https://admin.microsoft.com/).</li> <li>Go to **Users** > **Active Users** > select the user.</li> <li>Select **Manage Roles**, then from **Roles** select **Exchange Administrator**.</li> <li>**Save** the changes.</li> <li>Follow same steps to add the **User Administrator** role.</li></ol> |
| Teams admin center | Teams Administrator | Required if you plan to enable Microsoft Teams integration |

## Steps to set up the Expense Agent

To install and set up the Expense Agent, follow these steps:

1. Install Copilot for finance and operations apps.
1. Enable the agent features in your environment.
1. Create an expense user for agent execution.
1. Set up a shared mailbox.
1. Set up the Expense Agent using the Agent deployment tool
1. Enable the Expense Agent in Microsoft Teams (Optional - if you need Microsoft Teams integration)

The following sections describe each step in detail.

### Step 1: Install Copilot for finance and operations apps

The Expense Agent is available as part of the Copilot for finance and operations apps package. When you install this package in your environment, you automatically get all required assets, including the agent, environment variables, and Power Automate flows.

To install the required app, follow these steps:

1. Go to the [**Power Platform admin center**](https://admin.powerplatform.com/) in your browser.
1. From the list of environments, select the environment name where you want to install the app.
1. On the environment's details page (**NOT** from the left-hand navigation), go to the **Resources** section and select **Dynamics 365 apps**.
1. Search for **Copilot for finance and operations apps** within the Dynamics 365 apps list. If it's already installed and an update is available, select the **Update** button.  
1. If the app isn't listed under Dynamics 365 apps, select **Install app**, select **Copilot for finance and operations apps**, and follow the prompts to complete the installation.
1. Copilot for Finance and Operations apps should be 1.0.3231.4 or later.

> [!NOTE]
> Learn more about how to enable Copilot in your environment in [Enable Copilot capabilities in finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/copilot/enable-copilot).

> [!TIP]
> To verify if the package was installed successfully, follow these steps:  
>
> 1. Go to Power Apps maker portal > select your environment > select Solutions > See history > search and select msdyn_ExpenseAI > Details.
> 1. Check the **Result** field.
>    1. If the result shows Success, the package was installed correctly.  
>    1. If the result doesn't show Success, the installation failed.
> 1. If the installation fails, delete msdyn_FnOCopilotAnchor (see the uninstall section) and install Copilot for finance and operations apps again.

### Step 2: Enable the agent features in your environment

After you install the Copilot for finance and operations apps package, activate the Expense Agent from within your Dataverse and finance and operations environment.

#### Enable feature in Dataverse

Turn on the Copilot feature flag in the Power Platform admin center. To turn on the Copilot feature flag, follow these steps:

1. Go to [Power Platform admin center](https://admin.powerplatform.com/).
1. Select **Environments** > select your environment > **Settings** > **Product** > select **Features**.
1. Confirm that the **Copilot** feature flag is turned on.

#### Enable feature in your finance and operations environment

To activate the agent in finance and operations apps, follow these steps:

1. Sign in to your **finance and operations environment**.
1. Go to **Feature Management**, and enable **Immersive Home feature** and **Agent Management** features.
1. To configure the Expense Agent (setup is per legal entity), go to **Expense Management** \> **Setup** \> **General** \> **Expense Management parameters**.
1. On the **Expense Entry Agent** tab, configure the parameters as shown in the following table.

| Parameters | Value | Comments |
|---|---|---|
| Enable Expense Agent for current legal entity | Yes | Toggle to **Yes** to enable the agent for the current legal entity. |
| Frequency | Daily or Weekly | Configure the frequency for automatically creating expense reports in your organization. |
| Group Reports by | Trip or Project | Configure to group expenses based on a project or a trip. |

### Step 3: Create an expense agent user for agent execution

Create a dedicated expense agent user to ensure that the agent runs independently of any employee's identity. This approach helps with security, manageability, and long-term maintainability. Although you can use an existing user account that has the required privileges, use a system-owned identity.

#### Create the Expense Agent user in Microsoft Entra ID

1. Sign in to the [Azure portal](https://portal.azure.com/).
1. From the available Azure services, select **Microsoft Entra ID**.
1. Under **Microsoft Entra ID**, create a new user.
1. Select **Add** > **User** > **Create new user**, and enter the following details.
   - User principal name
   - Choose the right domain
   - Display name
   - Password
   - Mark Account enabled
1. To view the details and complete the user creation process, select **Review + create**, and select **Create**.
1. From the User page (**Manage > Users**), select a user, and the view details page.
1. Select **Edit properties**, navigate to the **Settings** tab, and fill out appropriate usage location.

> [!NOTE]
> Depending upon your organization policy, you might be required to change your password and setup multifactor authentication (MFA). Follow steps as you normally do for changing password and setting up MFA.

#### Assign the required licenses to Expense Agent user

To successfully install Expense Agent, assign the following licenses to the expense agent user:

- Dynamics 365 Teams Members license
- Microsoft 365 Business Basic or any license that covers Microsoft Teams and Outlook (for example, Office 365 E5 with teams)
- Power Apps Premium

To assign licenses, follow these steps:

1. Sign into [Microsoft 365 admin center](https://admin.microsoft.com/) with a user who has access to assign licenses that is a user with License Administrator or higher.
1. Select **Billing** > **Licenses** > **Dynamics 365 Teams Members license**.
1. Select **+Assign licenses**.
1. Search for the expense agent user created in previous step.
1. Select Assign to complete the license assignment.
1. Follow steps 2 to 5 for the other licenses – Microsoft 365 Business Basic and Power Apps Premium as well.

> [!NOTE]
> Learn more about how to check and assign licenses in [Use the Active users page to assign or unassign licenses](/microsoft-365/admin/manage/assign-licenses-to-users#use-the-active-users-page-to-assign-or-unassign-licenses).

#### Add the user to the Power Platform environment

To add the user to the Power Platform environment, follow these steps:

1. Sign in to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and select the appropriate environment.

   > [!TIP]
   > This page provides information related to Environment ID for Dataverse, Environment URL for Dataverse, finance and operations URL. Store these values to use in later sections.
1. Go to **Access > Users > See all**.
1. Select **Add user**, enter the newly created agent user, and select **Add**.
1. On **Manage security roles** page, add the following roles.
   - Expense AI Agent Role
   - Finance and operations Agent Configuration Manager
   - System Customizer
1. To confirm the role assignments, select **Save**.

These roles provide access to Dataverse and Power Automate components that the agent needs to function.

> [!TIP]
> If the user already exists and you only need to assign roles, go to Power Platform admin center, and select the appropriate environment.<br/>
>
> 1. Go to **Access > Users > See all**.
> 1. Select the created agent user.
> 1. Select **Manage roles**, and assign the roles.

#### Assign the required role in finance and operations environment

To assign the ExpenseAgentRole role in finance and operations environment, follow these steps:

1. In the finance and operations environment, go to **System administration** > **Users**.
1. Create a user record for the agent user.
1. After creating the user, go to the user's roles section, select **Assign roles**, and search for **ExpenseAgentRole**.
1. Select **Save**.

> [!NOTE]
> ExpenseAgentRole is available in the finance and operations apps version from **10.0.44 (10.0.2263.81)** and **10.0.45 (10.0.2345.6)** and with **Copilot for finance and operations apps** version **1.0.3121.1**

#### Assign access to the shared mailbox access

The agent user must have the Mail.Read.Shared Microsoft Graph permission. This permission allows the agent to read receipts from the configured shared mailbox during flow execution.

To assign access to the shared mailbox access, follow these steps:

1. Go to [Microsoft Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer) and sign in by using the **created agent user**.  
1. Select the **user** icon on the top right corner > select **Consent to permissions**.  
1. Select the drop-down menu for **Mail** > look for **Mail.Read.Shared** > select **Consent**, and select **Accept**.

#### Summary of required roles for the Created Agent User

| Environment | Roles | Comments |
|---|---|---|
| Dataverse | <li>Expense AI Agent Role <li>finance and operations Agent Configuration Manager <li>System Customizer | The mentioned roles enable the agent to interact with Power Automate flows, environment variables, and virtual entities that are connected to Dynamics 365 Finance|
| Finance and operations | <li>ExpenseAgentRole <li>System user | This role is required for the agent to create and manage expense entries in the finance and operations apps environment. <br> <br/> _Note: ExpenseAgentRole is available in the finance and operations apps version from **10.0.44 (10.0.2263.81)** and **10.0.45 (10.0.2345.6)** and with **Copilot for finance and operations apps** version **1.0.3121.1**_ |
| Shared mailbox access using Graph explorer | Mail.Read.Shared | Microsoft Graph permission that allows the agent to read receipts from the configured shared mailbox during flow execution|

### Step 4: Set up the shared mailbox

The Expense Agent uses a shared mailbox to receive and process receipt emails. A user with the Exchange Administrator role needs to create and configure this mailbox in the Microsoft 365 Admin Center.

To create and configure the shared mailbox, follow these steps:

1. Sign in to the [Microsoft 365 Admin Center](https://admin.microsoft.com/) by using an Exchange Admin account.
1. In the left pane, select **Teams & Groups** > **Shared mailboxes.**  

   > [!TIP]
   > You might need to select **Show all** to expand the full list.

1. Select **Add a shared mailbox**.  
1. Enter a name and email address for the shared mailbox.  
1. Select **Save changes**.
1. Under **Next steps**, select **Add members to this shared mailbox**. (Member management might take a few minutes to become available.)
1. Select **Add members**
1. Select the created agent user and any others who should monitor the mailbox, and select **Add**.  
1. Select **Close**.

> [!NOTE]
> You use the email address of the shared mailbox in the next step. After you set up the shared mailbox, you must provide its email address and the folder path (by default set to Inbox) as environment variables when you configure the Time and Expense Agent. For more information, see **Step 5: Set up the Expense Agent**.

### Step 5: Set up the Expense Agent 

To set up the Expense Agent, follow the steps in [Use the Agent Deployment tool](/dynamics365/project-operations/expense/expense-agent-deployment-tool).

#### Publish the solution

After you finish configuring all environment variables and flows, follow these steps to publish the solution.

1. In Power Apps, go to **Solutions**.
1. Select your environment and solution.
1. Select **Publish all customizations**.

When you complete these steps, the Expense Agent is fully configured and ready to use.

### Step 6: Enable the Expense Agent in Microsoft Teams (Optional)

To enable Teams-based communication for the Expense Agent, add the Teams channel to the agent in Power Apps. The agent can then send adaptive cards through Teams.

#### Enable the Teams channel

To enable the Teams channel, follow these steps:

1. Sign in to [Copilot Studio](https://copilotstudio.microsoft.com/) and select the correct environment.
1. On the **Agents** tab, select **Expense Entry Agent**.
1. In the agent view, on the **Channels** tab, select **Teams and Microsoft 365 Copilot**.
1. Select **Add channel** to enable Teams integration and follow the steps in the _Configure Teams app availability_ section to configure who you want to share the app.

Learn more in [Open the configuration panel for the Teams + Microsoft 365 channel](/microsoft-copilot-studio/publication-add-bot-to-microsoft-teams#open-the-configuration-panel-for-the-microsoft-teams-channel).

#### Configure Teams app availability

To configure Teams app availability, follow these steps:

1. After the Teams app is created, select **Availability Options**.
1. Select who you want to share the app with:

    - Specific users within the organization
    - The entire organization
1. Submit the app for approval.

#### Publish the app in the Teams admin center

To publish the app in the Teams admin center, follow these steps:

1. Sign in to the [Teams admin center](https://admin.teams.microsoft.com/).
1. Go to **teams app > Manage apps**. Search for "expense" and select **Expense Entry Agent** app where App status is blocked.
1. Select **Publish** to unblock the app. Once the publish action completes successfully, ensure that the App status changes to unblocked.

Learn more in [Connect and configure an agent for Teams and Microsoft 365](/microsoft-copilot-studio/publication-add-bot-to-microsoft-teams).

When you complete these steps, your **Expense Agent** is ready to use.

> [!NOTE]
> You can also provide feedback on agent-generated expense lines and reports by using the thumbs up and thumbs down icons and the feedback pop-up within the Dynamics 365 Finance environment.

## Uninstall Expense Agent

To **uninstall** the Expense Agent, follow these steps:

1. Sign in to Microsoft Power Apps maker portal.
1. Select **Solutions**, search for **msdyn_ExpenseAI**, select the three dots, and select **Delete**.
1. Search for **msdyn_FnOCopilotAnchor** and delete the solution.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
