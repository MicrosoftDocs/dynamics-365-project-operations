---
title: Set up the Expense Agent (preview)
description: Learn how to install and set up the Expense Agent to automate expense processing workflows by using AI.
author: ajitchandran
ms.author: ajitchandran
ms.date: 12/02/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Set up the Expense Agent (preview) 

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies to Dynamics 365 Project Operations Integrated with ERP and Dynamics 365 Project Operations for manufacturing**_

The Expense Agent brings together capabilities from Microsoft Dynamics 365 Project Operations, finance and operations apps, Microsoft Copilot Studio, Power Automate, and Dataverse to automate expense processing workflows by using AI. The feature helps save time and reduce manual effort by enabling your system to process receipts and generate expense lines and expense reports for users. It uses Microsoft Power Platform connectors for integration with Outlook, Microsoft Teams, user calendars, and the finance and operations apps environment via Dataverse virtual entities.

The Expense Agent includes multiple flows, three of which serve as core orchestrators:
- **Process Emails** – This flow scans a configured mailbox folder every hour and stores the attachments as unattached receipts in Dynamics 365 Finance.
- **Extract Receipt IDs** – This flow picks up unattached receipts and triggers the agent to extract receipt details and create an unattached expense line.
- **Process Expense Report** – This flow converts unattached expense lines and generates expense reports, based on the **Group reports by** configuration that is set in the application for each legal entity.

Additionally, the agent integrates with Microsoft Teams, enabling the use of adaptive cards for expense report review and submission.

The agent relies on several Microsoft Power Platform connectors. These connectors are automatically referenced in the Power Automate flows that are provided.

- **Outlook (Office 365)** – This connector accesses the shared mailbox to extract receipts.
- **Dataverse (Virtual Entities)** – This connector integrates with finance and operations apps via virtual entities.
- **Microsoft Copilot Studio** – This connector invokes AI models to extract receipt information.
- **Microsoft Teams** – This connector sends adaptive cards for user interactions (if Teams integration is enabled).
- **Microsoft 365 Users** – This connector retrieves user calendar details (optional, if receipt parsing is context-aware).


## Prerequisites

1. **Finance and operations environment:** The minimum finance and operations environment required to install the agent is version 10.0.44 or later.
1. **Roles required to set up the Expense Agent user:** To complete the steps in this article, you as the system administrator of the organization, must have the following roles to set up the expense agent user that is used to install the Expense Agent.

| System | Role | Comments |
|---|---|---|
| Power Platform admin center | System administrator | <ol><li>Go to [Power Platform admin center](https://admin.powerplatform.com/)</li> <li>Go to **Manage** on the left pane. Select **Environments**, and then select your environment.</li> <li>On the **Access** > **Users** section, select **See all**.</li> <li>Select a user then select **Manage roles**, and add the role.</li></ol> |
| Finance and operations | System administrator | <ol><li>Open the finance and operations URL for your environment environment.</li> <li>Go to **Module** > **System** **administration** > **Users**, and select a user.</li> <li>Select **Add role** – System administrator.</li></ol> |
| Microsoft 365 | Exchange Administrator and User Administrator | <ol><li>Go to [Microsoft 365 admin center](https://admin.microsoft.com/).</li> <li>Go to **Users** > **Active Users** > select the user.</li> <li>Select **Manage Roles**, then from **Roles** select **Exchange Administrator**.</li> <li>**Save** the changes.</li> <li>Follow same steps to add the **User Administrator** role.</li></ol> |
| Teams admin center | Teams Administrator | Required if you plan to enable Microsoft Teams integration |

## Steps to set up the Expense Agent 

To install and set up of the Expense Agent, follow these steps.

1. Install Copilot for finance and operations apps.
1. Enable the agent features in your environment.
1. Create an expense user for agent execution.
1. Set up a shared mailbox.
1. Set up the Expense Agent.
1. Enable the Expense Agent in Microsoft Teams (Optional - if you need Microsoft Teams integration)

The sections that follow describe each step in detail.

### Step 1: Install Copilot for finance and operations apps 

The Expense Agent is available as part of the Copilot for finance and operations apps package. After this package is installed in your environment, all required assets, including the agent, environment variables, and Power Automate flows automatically become available.

To install the required app, follow these steps. 

1. Go to the [**Power Platform admin center**](https://admin.powerplatform.com/) in your browser.
1. From the list of environments, select the environment name where you want to install the app.
1. On the environment’s details page (**NOT** from the left-hand navigation), go to the **Resources** section and select **Dynamics 365 apps**.
1. Search for **Copilot for finance and operations apps** within the Dynamics 365 apps list. If it's already installed and an update is available, select the **Update** button.  
1. If the app isn't listed under Dynamics 365 apps, select **Install app**, select **Copilot for finance and operations apps**, and follow the prompts to complete the installation.

> [!NOTE]
> Learn more about how to enable Copilot in your environment in [Enable Copilot capabilities in finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/copilot/enable-copilot).

> [!TIP]
>  To verify if the package was installed successfully, follow these steps.  
> 1. Go to Power Apps maker portal > select your environment > select Solutions > See history > search and select msdyn_ExpenseAI > Details.    
> 1. Verify the **Result** field.    
>    1. If the result shows Success, the package was installed correctly.  
>    1. If the result doesn't show Success, the installation failed.    
> 1. If the installation fails, then Delete msdyn_FnOCopilotAnchor (learn more in the uninstall section) and install Copilot for finance and operations apps again.

### Step 2: Enable the agent features in your environment

Now that the Copilot for finance and operations apps package is installed, the next step is to activate the Expense Agent from within your Dataverse and finance and operations environment.

#### Enable feature in Dataverse

The Copilot feature flag must be turned on in the Power Platform admin center. To turn on the Copilot feature flag, follow these steps.

1. Go to [Power Platform admin center](https://admin.powerplatform.com/).
1. Select **Environments** > select your environment > **Settings** > **Product** > select **Features**.
1. Confirm that the **Copilot** feature flag is turned on.

#### Enable feature in your finance and operations environment

To activate the agent in finance and operations apps, follow these steps.

1. Sign in to your **finance and operations environment**.
1. Go to **Feature Management**, and enable **Immersive Home feature** and **Agent Management** features.
1. To configure the Expense Agent (setup is per legal entity), go to **Expense Management** \> **Setup** \> **General** \> **Expense Management parameters**.
1. On the **Expense Entry Agent** tab, configure the parameters as shown in the following table.
   
| Parameters | Value | Comments |
|---|---|---|
| Enable Expense Agent for current legal entity | Yes | Toggle to **Yes** to enable the agent for the current legal entity. |
| Frequency | Daily or Weekly | Configure the frequency for automatically creating expense reports in your organization. |
| Group Reports by | Trip or Project | Configure to group expenses based on a project or a trip. |

### Step 3: Create an expense agent user for agent execution.

Create a dedicated expense agent user to ensure that the agent runs independently of any employee's identity. This approach helps with security, manageability, and long-term maintainability. Although you can use an existing user account that has the required privileges, we recommend that you use a system-owned identity.

#### Create the Expense Agent user in Azure Active Directory

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

To successfully install Expense Agent, the following licenses are required to be assigned to the expense agent user,
  - Dynamics 365 Teams Members license
  - Microsoft 365 Business Basic or any license that covers Microsoft Teams and Outlook (for example, Office 365 E5 with teams)
  - Power Apps Premium
    
To assign licenses, follow these steps.

1. Sign into [Microsoft 365 admin center](https://admin.microsoft.com/) with a user who has access to assign licenses that is a user with License Administrator or higher.
1. Select **Billing** > **Licenses** > **Dynamics 365 Teams Members license**.
1. Select **+Assign licenses**.
1. Search for the expense agent user created in previous step.
1. Select Assign to complete the license assignment.
1. Follow steps 2 to 5 for the other licenses – Microsoft 365 Business Basic and Power Apps Premium as well.

> [!NOTE]
> Learn more about how to check and assign licenses in [Use the Active users page to assign or unassign licenses](/microsoft-365/admin/manage/assign-licenses-to-users#use-the-active-users-page-to-assign-or-unassign-licenses).


#### Add the user to the Power Platform environment

To add the user to the Power Platform environment, follow these steps.

1. Sign in to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and select the appropriate environment.
   
   > [!TIP]
   > This page provides information related to Environment ID for Dataverse, Environment URL for Dataverse, finance and operations URL. Store these values to use in later sections.
1. Go to **Access > Users > See all**.
1. Select **Add user**, enter the newly created agent user, and select **Add**.
1. On Manage security roles page, add the following roles.
   - Expense AI Agent Role
   - Finance and operations Agent Configuration Manager
   - System Customizer
1. To confirm the role assignments, select **Save**.

These roles provide access to Dataverse and Power Automate components that the agent needs to function.

> [!TIP]
> If user already exists and only roles have to be assigned, go to Power Platform admin center, and select the appropriate environment.<br/>
> 1. Go to **Access > Users > See all**. 
> 1. Select the created agent user.
> 1. Select **Manage roles**, and assign the roles.


#### Assign the required role in finance and operations environment

To assign the ExpenseAgentRole role in finance and operations environment, follow these steps.

1. In the finance and operations environment, go to **System administration** > **Users**.
1. Create a user record for the agent user.
1. After creating the user, go to the user’s roles section, select **Assign roles**, and search for **ExpenseAgentRole**.
1. Select **Save**.

> [!NOTE]
> ExpenseAgentRole is available in the finance and operations apps version from **10.0.44 (10.0.2263.81)** and **10.0.45 (10.0.2345.6)** and with **Copilot for finance and operations apps** version **1.0.3121.1**

#### Assign access to the shared mailbox access

The agent user must have the Mail.Read.Shared Microsoft Graph permission. This permission allows the agent to read receipts from the configured shared mailbox during flow execution. 

To assign access to the shared mailbox access, follow these steps.

1. Go to [Microsoft Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer) and sign in using the **created agent user**.  
1. Select the **user** icon on the top right corner > select **Consent to permissions**.  
1. Select the drop-down menu for **Mail** > look for **Mail.Read.Shared** > select **Consent**, and select **Accept**.

#### Summary of required roles for the Created Agent User

| Environment | Roles | Comments |
|---|---|---|
| Dataverse | <li>Expense AI Agent Role <li>finance and operations Agent Configuration Manager <li>System Customizer | The mentioned roles enable the agent to interact with Power Automate flows, environment variables, and virtual entities that are connected to Dynamics 365 Finance|
| Finance and operations | <li>ExpenseAgentRole <li>System user | This role is required for the agent to create and manage expense entries in the finance and operations apps environment. <br> <br/> _Note: ExpenseAgentRole is available in the finance and operations apps version from **10.0.44 (10.0.2263.81)** and **10.0.45 (10.0.2345.6)** and with **Copilot for finance and operations apps** version **1.0.3121.1**_ |
| Shared mailbox access using Graph explorer | Mail.Read.Shared | Microsoft Graph permission that allows the agent to read receipts from the configured shared mailbox during flow execution| 


### Step 4: Set up the shared mailbox

The Expense Agent uses a shared mailbox to receive and process receipt emails. This mailbox needs to be created and configured by a user with the Exchange Administrator role in the Microsoft 365 Admin Center.

To create and configure the shared mailbox, follow these steps.
1. Sign in to the [Microsoft 365 Admin Center](https://admin.microsoft.com/) by using an Exchange Admin account.
1. In the left pane, select **Teams & Groups** > **Shared mailboxes.**  
   
   > [!TIP]
   > You may need to select **Show all** to expand the full list.

1. Select **Add a shared mailbox**.  
1. Enter a name and email address for the shared mailbox.  
1. Select **Save changes**. 
1. Under **Next steps**, select **Add members to this shared mailbox**. (Member management might take a few minutes to become available.)
1. Select **Add members**
1. Select the created agent user and any others who should monitor the mailbox, and select **Add**.  
1. Select **Close**.
    
> [!NOTE]
> The email address of the shared mailbox is used in the next step. After the shared mailbox is set up, you must provide its email address and the folder path (by default set to Inbox) as environment variables when you configure the Time and Expense Agent. Learn more in **Step 5: Set up the Expense Agent**. 

### Step 5: Set up the Expense Agent

You have two options for setting up the Expense Agent:
- **Option A:** Use a PowerShell Script **(recommended)**
- **Option B:** Do manual setup in Power Apps (no PowerShell)

> [!IMPORTANT]
> Before proceeding with the installation of the Expense Agent, ensure that agent is provisioned successfully in the Microsoft Copilot Studio.
> 
> To verify the agent is provisioned successfully, follow these steps.
> 1. Sign in to Microsoft Copilot Studio and select your environment.
> 1. Go to **Agents** and search for **ExpenseAgent-Line (Preview)**. 
> 1. Verify the Publish button is enabled.
> 1. If enabled, proceed with the installation. If disabled, wait until the agent is provisioned.
> 1. Repeat these steps to verify **Expense Entry Agent (Preview)** is enabled.

> [!TIP]
> If provisioning of the Copilot finance and operations app takes longer than 5–6 hours, it's recommended to uninstall and reinstall the app to resolve potential setup delays. Learn how to uninstall in the _Uninstall Expense Agent_ section at the end of this article.


#### Option A: Use a PowerShell script (recommended)

Manual setup of the agent involves creating and linking connections, enabling Power Automate flows, and publishing the solution. This process can be time consuming and is susceptible to errors. To automate the setup, you can use a PowerShell script after updating the required parameters.

The PowerShell script automates the following tasks:

- Update the required environment variables.
- Link Microsoft Power Platform connections with solution connection references.
- Enable all Power Automate flows that the Time and Expense Agent requires.
- Publish the Copilot agents.
- Publish the Dataverse solution.

Before running the script, you need to **create connections** as you need to provide the Connection ID for each connector in the install.ps1 file. To create these Connections, follow these steps using the created agent user.

1. Sign in to the [Power Apps maker portal](https://make.powerapps.com/) using the newly created agent user, and select your environment.
1. On the left pane, select **More** and select **Connections**.
1. Select **New connection** and search using the Connection Name from the following table (For example, **Office 365 Outlook**).
1. Select the appropriate connector from the list and create it.
1. Once the connection is created, note the user with which the connection was created. It should ideally be the **created agent user ID**. This needs to be updated in the installation file that we would be creating in the next step.
1. Repeat steps 3 and 4 for each of the remaining required connections listed in the following table.

| Connection Name | Connection URL Formats |
|---|---|
| Office 365 Outlook | https://make.powerapps.com/environments/environmentID/connections<br/>/**shared_office365**/connectionID/details |
| Office 365 Users | https://make.powerapps.com/environments/environmentID/connections<br/>/**shared_office365users**/connectionID/details |
| Microsoft Teams | https://make.powerapps.com/environments/environmentID/connections<br/>/**shared_teams**/connectionID/details |
| Microsoft Dataverse | https://make.powerapps.com/environments/environmentID/connections<br/>/**shared_commondataserviceforapps**/connectionID/details |
| Microsoft Copilot Studio (preview) | https://make.powerapps.com/environments/environmentID/connections<br/>/**shared_microsoftcopilotstudio**/connectionID/details |

#### Information you need to create the installation file

To create the installation file—install.ps1, have the following information available. (You can refer to the following table for reference.)

| Parameter | Other details |
|---|---|
| Dataverse environment ID | Enter the environment ID that you get from Power Platform admin center.<br/>  _Sample value: xxxx-xxxx-xxxx-xxx-xxxxxxxxxx_|
| Dataverse environment URL | Enter the Environment URL from Power Platform admin center.<br/> _Note: Ensure to have https:// at the start and no forward slash ‘/’ at the end._ <br/> _Sample value: https://org123.crm.contoso.com_ |
| Finance and operations instance URL | Enter the finance and operations environment details in the following format. <br/> _Sample value: https://org123.contoso.com_ <br/> _Note: Ensure **to have https://** at the start and **no** forward slash **‘/’** at the end._ |
| OutlookFolderPath | Enter the folder path created in the shared mailbox. If no other folder is created, it's set as Inbox by default. <br/> _Sample value: Inbox_ <br/>  As a best practice, it would be ideal to create a separate folder for expense management
| Mailbox Address ID | Enter the mail address of the newly created share mailbox <br/> _Sample value: expenseagent@contoso.com_ |
| Microsoft Dataverse connection name <br/> Microsoft Copilot Studio connection name <br/> Microsoft Office Outlook connection name <br/> Microsoft Office 365 Users connection name  <br/> Microsoft Teams connection name | Input to all the connection names would be the same ideally and would be the user email ID of the created agent user. <br/> <br/> _Sample value: createdexpenseagentuser@contoso.com_ |

#### Create the installation script file

Create an installation script file by copying the following code and insert the required environment variables into the script, and then run the script using PowerShell.

> [!NOTE]
> Make sure you place the installation script file on the local desktop. Do **NOT** store them in One Drive.

Create a PowerShell script file with the following code and make sure to update the mentioned parameters before running the script.

> [!TIP]
> When Mandatory = $true, the parameters are prompted interactively on the PowerShell screen, so there's no need to update them directly in the script file.
>
> If you'd prefer to avoid manual input and want the parameters to be predefined within the installation script, set Mandatory = $false in the Param section of the following sample code.

Copy the following code into your installation script file and save it as _**'Install.ps1'**_, and **make sure to update the variables in the respective parameter fields** in the param section. There are **10 variables to update**. 

> [!TIP]
> Use the previous table as a reference and replace all the sample values with your respective details.

```json
#requires -Version 7

Param(

   [Parameter(Mandatory=$true, HelpMessage="Dataverse environment id")]
   [string]$DataverseEnvironmentId = "xxxx-xxxx-xxxx-xxx-xxxxxxxxxx", 

   [Parameter(Mandatory=$true, HelpMessage="Dataverse environment URL")]
   [string]$DataverseUrl = "https://org123.crm.contoso.com",

   [Parameter(Mandatory=$true, HelpMessage="Finance and Operations instance URL")]
   [string]$D365FinanceAndOperationsUrl = "https://org123.contoso.com",

   [Parameter(Mandatory=$true, HelpMessage="OutlookFolderPath")]
   [string]$OutlookFolderPath = "Inbox",

   [Parameter(Mandatory=$true, HelpMessage="Mailbox Address Id")]
   [string]$MailboxAddressId = "expenseagent@contoso.com",

   [Parameter(Mandatory=$true, HelpMessage="Microsoft Dataverse connection name")]
   [string]$MicrosoftDataverseConnectionName = "createdexpenseagentuser@contoso.com",

   [Parameter(Mandatory=$true, HelpMessage="Microsoft Copilot Studio connection name")]
   [string]$MicrosoftCopilotStudioConnectionName = "createdexpenseagentuser@contoso.com",
   
   [Parameter(Mandatory=$true, HelpMessage="Microsoft Office Outlook connection name")]
   [string]$Office365OutlookConnectionName = "createdexpenseagentuser@contoso.com",

   [Parameter(Mandatory=$true, HelpMessage="Microsoft Office 365 Users connection name")]
   [string]$Office365UsersConnectionName = "createdexpenseagentuser@contoso.com",

   [Parameter(Mandatory=$true, HelpMessage="Microsoft Teams connection name")]
   [string]$MicrosoftTeamsConnectionName = "createdexpenseagentuser@contoso.com"

)


$flows = @(
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
    "user calender events",
    "process expense report using copilot"
)


$agents = @(
    "msdyn_ExpenseEntryAgent",
    "msdyn_ExpenseReportAgent"
)


# Check PS version
if ($PSVersionTable.PSVersion.Major -lt 7) {
    Write-Error 'This script requires at least PowerShell version 7' -ErrorAction Stop
}

# Install the required modules if not already installed or if the version is not 1.0.40
if (-not (Get-Module -ListAvailable -Name Microsoft.PowerApps.PowerShell | Where-Object { $_.Version -ge [Version]"1.0.40" })) {
    Write-Host "Microsoft.PowerApps.PowerShell version 1.0.40 not found. Installing..." -ForegroundColor Yellow
    Install-Module -Name Microsoft.PowerApps.PowerShell -RequiredVersion 1.0.40 -Force -AllowClobber -Scope CurrentUser
} else {
    Write-Host "Microsoft.PowerApps.PowerShell version 1.0.40 is already installed." -ForegroundColor Green
}

if (-not (Get-Module -ListAvailable -Name Microsoft.PowerApps.Administration.PowerShell | Where-Object { $_.Version -ge [Version]"2.0.147" })) {
    Install-Module -Name Microsoft.PowerApps.Administration.PowerShell -RequiredVersion 2.0.147 -Force -AllowClobber -Scope CurrentUser
}

# Install the required modules if not already installed
if (-not (Get-Module -ListAvailable -Name Az.Accounts | Where-Object { $_.Version -ge [Version]"5.0.1"})) {
    Install-Module -Name Az.Accounts -RequiredVersion 5.0.1 -Force -AllowClobber -Scope CurrentUser
}

# Import required modulesds
Import-Module Az.Accounts
Import-Module Microsoft.PowerApps.PowerShell
Import-Module Microsoft.PowerApps.Administration.PowerShell

# global variable declaration
$filter = '$filter'


function Get-AccessToken {
    # Retrieve the access token for the Dataverse environment
    $accessToken = (Get-AzAccessToken -ResourceUrl "$DataverseUrl" -AsSecureString).Token
    Write-Host "Access token for $userId retrieved successfully." -ForegroundColor Green
    return $accessToken
}

function Get-AccessTokenPlainText {
    param(
        [Parameter(Mandatory=$true, HelpMessage="Access token for authentication")]
        [securestring]$accessToken
    )
    # Retrieve the access token for the Microsoft Copilot Studio environment
    $token = [Runtime.InteropServices.Marshal]::PtrToStringAuto(
    [Runtime.InteropServices.Marshal]::SecureStringToBSTR($accessToken))
    return $token
}

function update-EnvironmentVaribleValue {
        param (
        [string]$accessToken,
        [string]$env_key,
        [string]$env_value   # Access token for authentication
    )

    try 
    {
        # Get the environment variable definition
        $envVarDefinition = Invoke-RestMethod -Method Get -Uri "$DataverseUrl/api/data/v9.2/environmentvariabledefinitions?$filter=schemaname eq '$env_key'" -Headers @{
            Authorization = "Bearer $accessToken"
        }

        if ($envVarDefinition.value -ne $null) {
            $envVarDefId = $envVarDefinition.value[0].environmentvariabledefinitionid

            # Get the environment variable value record
            $filterValue = [System.Web.HttpUtility]::UrlEncode("_environmentvariabledefinitionid_value eq $envVarDefId")
            $envVarValue = Invoke-RestMethod -Method Get -Uri "$DataverseUrl/api/data/v9.2/environmentvariablevalues?$filter=$filterValue" -Headers @{
                Authorization = "Bearer $accessToken"
            }

            if ($envVarValue.value -ne $null) {
                $envVarValueId = $envVarValue.value[0].environmentvariablevalueid
                # Update the environment variable value
                Invoke-RestMethod -Method Patch -Uri "$DataverseUrl/api/data/v9.2/environmentvariablevalues($envVarValueId)" -Headers @{
                    Authorization = "Bearer $accessToken"
                    "Content-Type" = "application/json"
                } -Body (@{ value = $env_value } | ConvertTo-Json -Depth 1)
                Write-Host "Environment variable updated with name $env_key and value $env_value" -ForegroundColor Green
            } else {
                Write-Host "Environment variable value not found for $env_key. Skipping..." -ForegroundColor Red
            }
        } 
        else {
            Write-Host "Environment variable definition not found for $env_key. Skipping..." -ForegroundColor Yellow
        }
  }
  catch {
        Write-Host "Failed to update environment variable $env_key. Error: $($_)" -ForegroundColor Red
        throw $_  # Re-throw the error to stop the script if this step is critical
    }

}

function update_EnvironmentVariablesForExpense {
        param (
        [string]$accessToken   # Access token for authentication
    )

    write-host "Updating environment variables..." -ForegroundColor Yellow

    try 
    {
        update-EnvironmentVaribleValue -accessToken $accessToken -env_key "msdyn_ExpenseFnoInstanceUrl" -env_value $D365FinanceAndOperationsUrl
        update-EnvironmentVaribleValue -accessToken $accessToken -env_key "msdyn_ExpenseAgentOutlookFolderPath" -env_value $OutlookFolderPath
        update-EnvironmentVaribleValue -accessToken $accessToken -env_key "msdyn_ExpenseAgentMailboxAddressId" -env_value $MailboxAddressId
        
    }
    Catch {
        Write-Host "Failed to update environment variables. Error: $($_)" -ForegroundColor Red -ErrorAction Stop
    }
}

# Function to publish the solution
function Publish-Solution {
    param (
        [string]$accessToken
    )

    Write-Host "Publishing All" -ForegroundColor Yellow

    # Construct the API endpoint for publishing the solution
    $uri = "$DataverseUrl/api/data/v9.2/PublishAllXml"


    # Make the API call
    try {
        Invoke-RestMethod -Method Post `
            -Uri $uri `
            -Headers @{
                Authorization = "Bearer $accessToken"
                "Content-Type" = "application/json"
            }

        Write-Host "Publish All - Success!" -ForegroundColor Green
    } catch {
        Write-Host "Failed to publish. Error: $($_.Exception)" -ForegroundColor Red
        
    }
}

function Get-FlowGuidByName {
    param (
        [string]$accessToken,   # Access token for authentication
        [string]$flowName       # Name of the flow to search for
    )

    #Write-Host "Retrieving GUID for flow: $flowName" -ForegroundColor Yellow

    # Construct the API endpoint with a filter for the flow name
    $encodedFlowName = [System.Web.HttpUtility]::UrlEncode($flowName)
    $uri = "$DataverseUrl/api/data/v9.2/workflows?$filter=name eq '$encodedFlowName'"

    try {
        # Make the API call
        $response = Invoke-RestMethod -Method Get `
            -Uri $uri `
            -Headers @{
                Authorization = "Bearer $accessToken"
                "Content-Type" = "application/json"
            }

        # Check if the flow was found
        if ($response.value.Count -gt 0) {
            $flow = $response.value[0]
            Write-Host "Flow found: $($flow.name) with GUID: $($flow.workflowid)" -ForegroundColor Green
            return $flow.workflowid
        } else {
            Write-Host "No flow found with the name: $flowName" -ForegroundColor Red
            return $null
        }
    } catch {
        Write-Host "Failed to retrieve flow GUID. Error: $($_.Exception.Message)" -ForegroundColor Red
        return $null
    }
}


# Function to activate a Power Automate flow
function Activate-Flow {
    param (
        [string]$DataverseUrl,  # Dataverse environment URL
        [string]$accessToken,   # Access token for authentication
        [string]$flowId         # GUID of the flow to activate
    )

    # Construct the request body
    $body = @{
        "statecode" = 1  # Activated
        "statuscode" = 2 # Activated
    } | ConvertTo-Json -Depth 1 -Compress

    # Construct the API endpoint
    $uri = "$DataverseUrl/api/data/v9.2/workflows($flowId)"

    # Make the API call
    try {
        Invoke-RestMethod -Method Patch `
            -Uri $uri `
            -Headers @{
                Authorization = "Bearer $accessToken"
                "Content-Type" = "application/json"
            } `
            -Body $body

        Write-Host "Flow activated successfully." -ForegroundColor Green
    } catch {
        Write-Host "Failed to activate flow. Error: $($_.Exception.Message)" -ForegroundColor Red
    }
}

function Get-ConnectionRefIdFromLogicalName  {
    param (
        [string]$accessToken,
        [string]$connectionRefLogicalName
    )
    $uri = "$DataverseUrl/api/data/v9.2/connectionreferences?$filter=connectionreferencelogicalname eq '$connectionRefLogicalName'"
    $response = Invoke-RestMethod -Method Get `
    -Uri $uri `
    -Headers @{
        Authorization = "Bearer $accessToken"
        "Content-Type" = "application/json"
    }

    if ($response -ne $null) {
        write-host "Connection reference id found: $($response.value[0].connectionreferenceid) " -ForegroundColor Green
        return $response.value[0].connectionreferenceid
    }
    else {
        Write-Host "No connection reference found for logical name: $connectionRefLogicalName" -ForegroundColor Red
        return $null
    }
}

function Get-ConnectionId {
    param (
        [string]$userProvidedName,
        [string]$providerName
    )

    try {
        $matchedConnectionId = $null
        # Added -ErrorAction Stop to ensure the catch block is triggered on failure
        $connections = Get-PowerAppConnection -EnvironmentName $DataverseEnvironmentId -ConnectorNameFilter $providerName -ErrorAction Stop
        
        foreach ($con in $connections) {
            if (($con.ConnectionName -eq $userProvidedName) -or ($con.DisplayName -eq $userProvidedName)) {
                $matchedConnectionId = $con.ConnectionName
                break
            }
        }

        if ($null -eq $matchedConnectionId) {
            # Use 'throw' to create a terminating error that the calling function can catch
            throw "Unable to find connection '$userProvidedName' for provider '$providerName'."
        }

        return $matchedConnectionId
    }
    catch {
        # Catch any errors from Get-PowerAppConnection or the 'throw' statement above
        Write-Error "Failed to get connection ID for '$userProvidedName'. Error: $_"
        throw # Re-throw the error to stop the script if this step is critical
    }
}

function Get-ConnectionReferenceId {
    param(
        [string]$connectionReferenceLogicalName,
        [securestring]$accessToken
    )

    try {
        $uri = "$DataverseUrl/api/data/v9.2/connectionreferences?$filter=connectionreferencelogicalname eq '$connectionReferenceLogicalName'"
        
        # Added -ErrorAction Stop for clarity, though Invoke-RestMethod often terminates on HTTP errors
        $response = Invoke-RestMethod -Method Get -Uri $uri -Authentication Bearer -Token $accessToken -ContentType 'application/json' -ErrorAction Stop
            
        if ($null -eq $response -or $response.value.Count -eq 0) {
            throw "Connection reference not found for logical name '$connectionReferenceLogicalName'."
        }

        $connectionReferenceDisplayName = $response.value[0].connectionreferencedisplayname
        $connectionReferenceId = $response.value[0].connectionreferenceid

        Write-Host "updating connection $connectionReferenceDisplayName for logical name $connectionReferenceLogicalName)"
        return $connectionReferenceId
    }
    catch {
        Write-Error "Failed to get connection reference ID for '$connectionReferenceLogicalName'. Error: $_"
        throw # Re-throw to notify the calling function
    }
}

function Set-ConnectionReferenceConnection {
    param (
        [string]$connectionReferenceLogicalName,
        [string]$userProvidedConnectionName,
        [string]$providerName,
        [securestring]$accessToken
    )

    try {

        # These functions will now throw terminating errors if they fail
        $connectionReferenceId = Get-ConnectionReferenceId -connectionReferenceLogicalName $connectionReferenceLogicalName -accessToken $accessToken
        $connectionId = Get-ConnectionId -userProvidedName $userProvidedConnectionName -providerName $providerName

        $body = @{
            "connectionid" = "$connectionId"
        } | ConvertTo-Json -Depth 1

        $uri = "$DataverseUrl/api/data/v9.2/connectionreferences($connectionReferenceId)"
        # Write-Host "Updating connection reference URI: $uri with connection id $connectionId"

        Invoke-RestMethod -Method Patch -Uri $uri -Authentication Bearer -Token $accessToken -ContentType 'application/json' -Body $body -ErrorAction Stop
    
        Write-Host "Connection reference updated successfully." -ForegroundColor Green
    }
    catch {
        # This block will catch errors from any of the functions called within the try block
        Write-Error "Failed to set connection reference for '$connectionReferenceLogicalName'. Error: $_"
        throw
    }
}

function Activate-Flows {
    param (
        [string]$accessToken,
        [array]$expenseAIFlows
    )

    foreach ($flowName in $expenseAIFlows) {
         Write-Host "Activating flow: $flowName" -ForegroundColor Yellow

        # Call the Get-FlowGuidByName function to get the flow GUID
        $flowGuid = Get-FlowGuidByName -dataverseUrl $DataverseUrl -accessToken $accessToken -flowName $flowName

        if ($flowGuid -ne $null) {
            # Write-Host "Flow Name: $flowName, Flow GUID: $flowGuid" -ForegroundColor Green
            Activate-Flow -dataverseUrl $DataverseUrl -accessToken $accessToken -flowId $flowGuid
            # Write-Host "Flow Name: $flowName, Flow GUID: $flowGuid Activated" -ForegroundColor Green
        } else {
            Write-Host "Flow Name: $flowName not found." -ForegroundColor Red
        }
    }
}


# Function to retrieve the Agent ID by name
function Get-AgentIdBySchemaName {
    param (
        [string]$DataverseUrl,
        [string]$accessToken,
        [string]$agentSchemaName
    )

    Write-Host "Retrieving agent ID for agent schema: $agentSchemaName" -ForegroundColor Yellow

    # Construct the API endpoint to retrieve the bot
    $uri = "$DataverseUrl/api/data/v9.2/bots?$filter=schemaname eq '$agentSchemaName'"

    try {
        # Make the API call
        $response = Invoke-RestMethod -Method Get -Uri $uri -Headers @{
            Authorization = "Bearer $accessToken"
            "Content-Type" = "application/json"
        }

        if ($response.value.Count -gt 0) {
            $agentId = $response.value[0].botid
            return $agentId
        } else {
            Write-Host "No agent found with the name: $agentSchemaName" -ForegroundColor Red
            return $null
        }
    } catch {
        Write-Host "Failed to retrieve agent ID. Error: $($_)" -ForegroundColor Red
        return $null
    }
}


# Function to provision a Microsoft Copilot Studio bot
function Provision-Agent {
    param (
        [string]$DataverseUrl,
        [string]$accessToken,
        [string]$agentId
    )

    # Construct the API endpoint for publishing the bot
    $uri = "$DataverseUrl/api/data/v9.2/bots($agentId)/Microsoft.Dynamics.CRM.PvaProvision"

    try {
        # Make the API call
        Invoke-RestMethod -Method Post -Uri $uri -Headers @{
            Authorization = "Bearer $accessToken"
            "Content-Type" = "application/json"
        }

        Write-Host "Agent Provisioning successfully!" -ForegroundColor Green
        # Add 30 second delay to allow the publish process to complete
        Start-Sleep -Seconds 30
    } catch {
        Write-Host "Failed to Provision Agent. Error: $($_.Exception.Message)" -ForegroundColor Red
    }
}


# Function to publish a Microsoft Copilot Studio bot
function Publish-Agent {
    param (
        [string]$DataverseUrl,
        [string]$accessToken,
        [string]$agentId
    )

    Write-Host "Publishing agent with ID: $agentId" -ForegroundColor Yellow

    # Construct the API endpoint for publishing the bot
    $uri = "$DataverseUrl/api/data/v9.2/bots($agentId)/Microsoft.Dynamics.CRM.PvaPublish"

    try {
        # Make the API call
        Invoke-RestMethod -Method Post -Uri $uri -Headers @{
            Authorization = "Bearer $accessToken"
            "Content-Type" = "application/json"
        }

        Write-Host "Agent published successfully!" -ForegroundColor Green
        # Add 30 second delay to allow the publish process to complete
        Start-Sleep -Seconds 30
    } catch {
        Write-Host "Failed to publish Agent. Error: $($_.Exception.Message)" -ForegroundColor Red
        # try provisioing the agent
        Write-Host "Attempting to provision agent with ID: $agentId" -ForegroundColor Yellow
        Start-Sleep -Seconds 20
        Provision-Agent -dataverseUrl $DataverseUrl -accessToken $accessToken -agentId $agentId
        # Add 30 second delay to allow the publish process to complete
        Start-Sleep -Seconds 30
        
        # Try publishing again after provisioning
        try {
            Invoke-RestMethod -Method Post -Uri $uri -Headers @{
                Authorization = "Bearer $accessToken"
                "Content-Type" = "application/json"
            }
            Write-Host "Agent published successfully after provisioning!" -ForegroundColor Green
            Start-Sleep -Seconds 30
        } catch {
            Write-Host "Failed to publish Agent after provisioning. Error: $($_)" -ForegroundColor Red
        }
    }
}


function Publish-Agents {
    param (
        [string]$accessToken,
        [array]$agentSchemas
    )

    if (-not $agentSchemas -or $agentSchemas.Count -eq 0) {
        Write-Host "No agent schemas provided. Skipping agent publishing." -ForegroundColor Yellow
        return
    }

    foreach ($agentSchema in $agentSchemas) {
        #Write-Host "Publishing agent schema: $agentSchema" -ForegroundColor Yellow

        try {
                # Construct the API endpoint for publishing the agent schema
                $agentId = Get-AgentIdBySchemaName -dataverseUrl $DataverseUrl -accessToken $accessToken -agentSchemaName $agentSchema

                if ($agentId -ne $null) {
                    # Step 4: Publish the bot
                    Publish-Agent -dataverseUrl $DataverseUrl -accessToken $accessToken -agentId $agentId
                } else {
                    Write-Host "Agent not found. Cannot proceed with publishing.Skipping the step" -ForegroundColor Yellow
                }
        }
        catch {
            Write-Host "An error occurred while publishing agent schema: $agentSchema. Error: $_" -ForegroundColor Red
        }
    }

}


# Main script execution
try {

    $expenseAIFlows = $flows
    $agentSchemas = $agents

    # Step 1: Interactive login to Azure
    Connect-AzAccount -UseDeviceAuthentication
    $accessToken = Get-AccessToken
    $accessTokenPlainText = Get-AccessTokenPlainText -accessToken $accessToken

    # Step 2: Setup ennviornment variables
    update_EnvironmentVariablesForExpense -accessToken $accessTokenPlainText 
    Write-Host "Environment variables updated successfully!" -ForegroundColor Green

    # Step 3: Check active connections
    Set-ConnectionReferenceConnection -userProvidedConnectionName $MicrosoftDataverseConnectionName -providerName "/providers/Microsoft.PowerApps/apis/shared_commondataserviceforapps" -connectionReferenceLogicalName "msdyn_sharedcommondataserviceforapps_2c2d4" -accessToken $accessToken

    Set-ConnectionReferenceConnection -userProvidedConnectionName $MicrosoftCopilotStudioConnectionName -providerName "/providers/Microsoft.PowerApps/apis/shared_microsoftcopilotstudio" -connectionReferenceLogicalName "msdyn_sharedmicrosoftcopilotstudio_26d9d" -accessToken $accessToken

    Set-ConnectionReferenceConnection -userProvidedConnectionName $Office365OutlookConnectionName -providerName "/providers/Microsoft.PowerApps/apis/shared_office365" -connectionReferenceLogicalName "msdyn_sharedoffice365_9b471" -accessToken $accessToken

    Set-ConnectionReferenceConnection -userProvidedConnectionName $MicrosoftTeamsConnectionName -providerName "/providers/Microsoft.PowerApps/apis/shared_teams" -connectionReferenceLogicalName "msdyn_sharedteams_8ea9c" -accessToken $accessToken

    Set-ConnectionReferenceConnection -userProvidedConnectionName $Office365UsersConnectionName -providerName "/providers/Microsoft.PowerApps/apis/shared_office365users" -connectionReferenceLogicalName "msdyn_sharedoffice365users_909b9" -accessToken $accessToken
    

    # Step 4: Activate flows
    Activate-Flows -accessToken $accessTokenPlainText -expenseAIFlows $expenseAIFlows

    # step 5: publish the agents
    Publish-Agents -accessToken $accessTokenPlainText -agentSchemas $agentSchemas

    # Step 6: Publish the solution 
    Publish-Solution -accessToken $accessTokenPlainText

    Write-Host "Agent setup completed successfully!" -ForegroundColor Green

} catch {
    Write-Host "An error occurred: $_" -ForegroundColor Red
}

```

To trigger the PowerShell file, follow these steps.

1. Open PowerShell _(Minimum version required - PowerShell 7)_.
1. Go to the location where the  file is saved. _(Use the command cd \<file location\>)_.
1. Trigger the installation script. _(Use command '.\Install.ps1')_.
1. follow the instructions to sign in to Azure.
1. After successfully logging in, you might need to authorize one more time. _(Use the **created agent user id.**)_.

Wait for the script to run completely and look for a message **Agent setup completed successfully!**

> [!NOTE]
> The preceding script performs these actions:
> - Set environment variables.
> - Verify and link connection references.
> - Enable Power Automate flows.
> - Publish the required Copilot agents.
> - Publish the Dataverse solution.

After the script runs successfully, Expense Agent is fully configured and ready to use.

### Option B: Do manual setup in Power Apps (no PowerShell)

If you prefer not to use the PowerShell script, you can manually configure the Expense Agent through Power Apps. This process involves updating environment variables, enabling Power Automate flows, and publishing the solution.

#### Update environment variables

To update environment variables, follow these steps.

1. Sign in to [Power Apps](https://make.powerapps.com/), and select your environment.
1. Select **Solutions**, then open **Default Solution** (or the solution where the agent is installed).
1. Go to **Environment Variables**, and set the following values.

    | Variable name | Description |
    |---|---|
    | Expense Agent Outlook Folder Path | Specify the folder path to monitor in the shared mailbox (by default, **Inbox**). |
    | Expense Agent Shared Mailbox Address ID | Specify the email address of the shared mailbox. To use the mailbox of the signed-in user, enter **NA**. |
    | Finance and Operations Instance Url | Specify the URL of the finance and operations apps environment (for example, `https://org123.contoso.com`). |

#### Enable Power Automate flows

The Expense Agent relies on the following Power Automate flows:

- Expense entry retry check
- Expense configuration
- Get expense outlook folder
- Generate expense report
- Send expense report adaptive card
- Process emails
- Extract unattached receipt IDs for copilot invocation
- Extract unattached receipt output using Dataverse plugin
- Generate expense line
- Generate expense line without project ID and status ID
- Identify project IDs
- User calendar events
- Process expense report using copilot

To enable the flows, follow these steps.

1. Sign in to [Power Automate](https://make.powerautomate.com/), and select your environment.
1. Select **My Flows**.
1. For each of the 13 flows in the previous list, follow these steps:

    1. Find the flow.
    1. Select **Edit**.
    1. Switch to the **Old Designer** view by turning off the **New Designer** option.
    1. Authenticate any required connections (until green check marks appear).
    1. Select **Continue**, and then select **Save**.
    1. Select **Turn On** to enable the flow.

#### Publish the solution

After you finish configuring all environment variables and flows, follow these steps to publish the solution.

1. In Power Apps, go to **Solutions**.
1. Select your environment and solution.
1. Select **Publish all customizations**.

After you complete these steps, the Expense Agent is fully configured and ready to use.

### Step 6: Enable the Expense Agent in Microsoft Teams (Optional)

To enable Teams-based communication for the Expense Agent, you must add the Teams channel to the agent in Power Apps. The agent can then send adaptive cards and receive input via Teams.

#### Enable the Teams channel

To enable the Teams channel, follow these steps.

1. Sign in to [Copilot Studio](https://copilotstudio.microsoft.com/) and select the correct environment.
1. On the **Agents** tab, select **Expense Entry Agent**.
1. In the agent view, on the **Channels** tab, select **Teams and Microsoft 365 Copilot**.
1. Select **Add channel** to enable Teams integration and follow the steps in the _Configure Teams app availability_ section to configure who you want to share the app.

Learn more in [Open the configuration panel for the Teams + Microsoft 365 channel](/microsoft-copilot-studio/publication-add-bot-to-microsoft-teams#open-the-configuration-panel-for-the-microsoft-teams-channel).

#### Configure Teams app availability

To configure Teams app availability, follow these steps.

1. After the Teams app is created, select **Availability Options**.
1. Select who you want to share the app with:

    - Specific users within the organization
    - The entire organization
1. Submit the app for approval.

#### Publish the app in the Teams admin center

To publish the app in the Teams admin center, follow these steps.

1. Sign in to the [Teams admin center](https://admin.teams.microsoft.com/).
1. Go to teams app > Manage apps. Search for expense and select "Expense Entry Agent" app where App status is blocked.
1. Select **Publish** to unblock the app. Once publish action is completed successfully, ensure that App status changes to unblocked.

Learn more in [Connect and configure an agent for Teams and Microsoft 365](/microsoft-copilot-studio/publication-add-bot-to-microsoft-teams).

With these steps completed, your **Expense Agent** is now fully set up and ready to go.

> [!NOTE]
> You can also provide feedback on agent-generated expense lines and reports using the thumbs up/down icons and the feedback pop-up within the Dynamics 365 Finance environment.

## Uninstall Expense Agent 

To **uninstall** the Expense Agent, follow these steps.

1. Sign in to Microsoft Power Apps maker portal
1. Select **Solutions**, search for **msdyn_ExpenseAI**, select the three dots, and select **Delete**.
1. Similarly search for **msdyn_FnOCopilotAnchor** and delete the solution.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
