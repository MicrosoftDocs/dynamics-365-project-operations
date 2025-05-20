---
title: Install and set up the Expense Entry feature of the Time and Expense Agent (preview)
description: Learn how to install and set up the Expense Entry feature of the Time and Expense Agent.
author: alexeiantao
ms.author: alexeiantao
ms.date: 05/13/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Install and set up the Expense Entry feature of the Time and Expense Agent (preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

The Expense Entry feature of the Time and Expense Agent brings together capabilities from Microsoft Dynamics 365 Project Operations, finance and operations apps, Microsoft Copilot Studio, Power Automate, and Dataverse to automate expense processing workflows by using AI. The feature helps save time and reduce manual effort by enabling your system to process receipts and generate expense lines and reports for users. It uses Microsoft Power Platform connectors for integration with Outlook, Microsoft Teams, user calendars, and the finance and operations apps environment via Dataverse virtual entities.

The Expense Entry feature of the Time and Expense Agent includes multiple flows, three of which serve as core orchestrators:

- **Process Emails** – This flow scans a configured mailbox folder every hour and stores the attachments as unattached receipts in Dynamics 365 Finance.
- **Extract Receipt IDs** – This flow picks up newly added receipts and triggers the agent to extract details.
- **Process Expense Report** – This flow converts extracted receipt data into structured expense lines and generates reports, based on the configuration that is set in the application.

In addition, the agent supports Teams integration, so that you can send adaptive cards for review and submission of expenses.

The agent relies on several Microsoft Power Platform connectors. These connectors are automatically referenced in the Power Automate flows that are provided.

- **Outlook (Office 365)** – This connector accesses the shared mailbox to fetch receipts.
- **Dataverse (Virtual Entities)** – This connector integrates with finance and operations apps entities.
- **Microsoft Copilot Studio** – This connector invokes AI models to extract receipt information.
- **Microsoft Teams** – This connector sends adaptive cards for user interactions (if Teams integration is enabled).
- **Microsoft 365 Users** – This connector retrieves user calendar details (optional, if receipt parsing is context-aware).

Installation and setup of the Expense Entry feature of the Time and Expense Agent involves the following steps:

1. Install Copilot for finance and operations apps.
1. Activate the agent in finance and operations apps.
1. Create an expense user account for agent execution.
1. Assign permissions in finance and operations apps and Dataverse.
1. Set up a shared mailbox for email-based receipt collection.
1. Configure and set up the agent, either manually or by using Windows PowerShell.
1. Optional: Enable Teams integration.

The sections that follow describe each step in detail.

## Prerequisites

To complete the steps that are described in this article, you must have **System administrator** or **System customizer** access in the Power Platform admin center, **System administrator** access in finance and operations apps, and **Exchange administrator** access in Microsoft 365 to configure the shared mailbox. If you plan to enable Teams integration, you must also have the required permissions in the Teams admin center.

## Step 1: Install Copilot for finance and operations apps

The Expense Entry feature of the Time and Expense Agent is available as part of the **Copilot for finance and operations** package. After this package is installed in your environment, all required assets, including the agent, environment variables, and Power Automate flows, automatically become available.

Learn more about how to enable Copilot in your environment in [Enable Copilot capabilities in finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/copilot/enable-copilot).

## Step 2: Activate the agent in finance and operations apps

After you install the **Copilot for finance and operations** package, activate the Expense Entry feature of the Time and Expense Agent from the finance and operations web application.

To activate the agent in finance and operations apps, follow these steps.

1. Go to **Feature Management**, and ensure that **Agent Management** is enabled.
1. Go to **Expense Management** \> **Setup** \> **Expense Management parameters** \> **Expense Entry feature of the Time and Expense Agent**.
1. Enable the agent for the current legal entity, and configure the run frequency as either **Daily** or **Weekly**. You can also use the **Expense group by** parameter to group expenses by trip or project.

## Step 3: Set up the agent user

Create a dedicated expense agent user to ensure that the agent runs independently of any employee's identity. This approach helps with security, manageability, and long-term maintainability. Although you can use an existing user account that has the required privileges, we recommend that you use a system-owned identity.

### Create the user in Azure Active Directory

1. Sign in to the [Azure portal](https://portal.azure.com/).
1. Under **Microsoft Entra ID**, create a new user.

### Add the user to the Power Platform environment

1. Sign in to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and select the appropriate environment.
1. Select **See all users**, select **Add user**, and select the newly created agent user.

### Assign required roles in the Power Platform admin center

1. In the Power Platform admin center, select the environment.
1. Find the agent user, and select **Manage Roles**.
1. Assign the following roles:

    - System Customizer
    - Expense AI Agent Role
    - Finance and Operations Agent Configuration Role

    These roles provide access to Dataverse and Power Automate components that the agent needs to function.

### Assign the System Administrator role in finance and operations apps

1. In finance and operations apps, go to **System administration** \> **Users**.
1. Create a user record for the agent user.
1. Assign the **System Administrator** role.
1. Select **Save** to save the configuration.

## Step 4: Grant user permissions

To successfully configure and run the Expense Entry feature of the Time and Expense Agent, you must grant the following permissions to the designated agent user.

### Finance and operations roles

- **System Administrator** — The agent must have this role to create and manage expense entries in the finance and operations apps environment.

### Dataverse roles

The following roles enable the agent to interact with Power Automate flows, environment variables, and virtual entities that are connected to Dynamics 365 Finance:

- System Customizer
- Expense AI Agent Role
- Finance and Operations Agent Configuration Role

### Shared mailbox access

The agent user must have the **Mail.Shared.Read** Microsoft Graph permission. This permission allows the agent to read receipts from the configured shared mailbox during flow execution.

## Step 5: Set up the shared mailbox

The Expense Entry feature of the Time and Expense Agent uses a shared mailbox to receive receipt emails. A user who has the **Exchange Admin** role must create and configure this mailbox in the Microsoft 365 admin center.

To create and configure the shared mailbox, follow these steps.

1. Sign in to the [Microsoft 365 Admin Center](https://admin.microsoft.com/) by using an Exchange Admin account.
1. In the left pane, select **Teams & Groups** \> **Shared mailboxes**.

    > [!TIP]
    > You might first have to select **Show all** to expand the list in the left pane.

1. Select **Add a shared mailbox**.
1. Enter a name and email address for the shared mailbox.

    The recommended format for the email address is `expenseagent@contoso.com`.

1. Select **Save changes**. Member management might take a few minutes to become available.
1. Under **Next steps**, select **Add members to this mailbox**.
1. Select the agent user and any others who should monitor the mailbox, and then select **Add**.
1. Select **Close**.

After the mailbox is set up, you must provide its email address and the folder path (by default, **Inbox**) as environment variables when you configure the Time and Expense Agent.

## Step 6: Set up the Expense Entry feature of the Time and Expense Agent

You have two options for setting up the Expense Entry feature of the Time and Expense Agent:

- **Option 1:** Use a PowerShell Script (recommended)
- **Option 2:** Do manual setup in Power Apps (no PowerShell)

### Option 1: Use a PowerShell script (recommended)

Manual setup of the agent involves creating and linking connections, enabling Power Automate flows, and publishing the solution. This process can be time consuming and is susceptible to errors. To automate the setup, you can use a PowerShell script and configuration file (AgentConfig.json).

The PowerShell script automates the following tasks:

- Update the required environment variables.
- Link Microsoft Power Platform connections with solution connection references.
- Enable all Power Automate flows that the Time and Expense Agent requires.
- Publish the Copilot agents.
- Publish the Dataverse solution.

#### Example configuration file (AgentConfig.json)

Before you run the PowerShell script, configure the **AgentConfig.json** file with values that are relevant to your environment.

```json
"modules": {
    "Expense": {
        "environmentVariables": {
            "msdyn_ExpenseFnoInstanceUrl": "https://xxxxx.operations.dynamics.com",
            "msdyn_ExpenseAgentOutlookFolderPath": "Inbox",
            "msdyn_ExpenseAgentMailboxAddressId": "NA"
        },
        "connectors": [
            {
                "Name": "shared_commondataserviceforapps",
                "id": "",
                "connectionRefName": "msdyn_sharedcommondataserviceforapps_2c2d4",
                "DisplayName": "Dataverse"
            },
            {
                "Name": "shared_teams",
                "id": "",
                "connectionRefName": "msdyn_sharedteams_8ea9c",
                "DisplayName": "Microsoft Teams"
            },
            {
                "Name": "shared_office365",
                "id": "",
                "connectionRefName": "msdyn_sharedoffice365_9b471",
                "DisplayName": "Office 365 Outlook"
            },
            {
                "Name": "shared_office365users",
                "id": "",
                "connectionRefName": "msdyn_sharedoffice365users_909b9",
                "DisplayName": "Office 365 Users"
            },
            {
                "Name": "shared_microsoftcopilotstudio",
                "id": "",
                "connectionRefName": "msdyn_sharedmicrosoftcopilotstudio_26d9d",
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
            "user calender events",
            "process expense report using copilot"
        ],
        "agents":[
            "msdyn_ExpenseEntryAgent",
            "msdyn_ExpenseReportAgent"
        ]
    }
}
```

#### Create the connections

To create the connections, follow these steps.

1. Sign in to [Power Apps](https://make.powerapps.com/), and select your environment.
1. Go to **Connections**.
1. Select **New connection**, and select the appropriate connector (for example, the Outlook or Teams connector).
1. After the connection is created, copy the **connection ID** value, and paste it under the appropriate connector entry in the **AgentConfig.json** file.

#### Run the script

When your configuration is ready, insert the required environment variables into the following script, and then run the script.

```powershell
Param(

    [Parameter(Mandatory=$true, HelpMessage="Dataverse environment id")]
    [string]$environmentId = "", 

    [Parameter(Mandatory=$true, HelpMessage="Dataverse environment URL")]
    [string]$dataverseUrl = "",

    [Parameter(Mandatory=$true, HelpMessage="Config Module Name")]
    [string]$ConfigModuleName = ""
)

# Install the required modules if not already installed
if (-not (Get-Module -ListAvailable -Name Microsoft.PowerApps.PowerShell)) {
    Install-Module -Name Microsoft.PowerApps.PowerShell -AllowClobber -Scope CurrentUser
}

if (-not (Get-Module -ListAvailable -Name Microsoft.PowerApps.Administration.PowerShell)) {
    Install-Module -Name Microsoft.PowerApps.Administration.PowerShell -AllowClobber -Scope CurrentUser
}

# Install the required modules if not already installed
if (-not (Get-Module -ListAvailable -Name Az.Accounts)) {
    Install-Module -Name Az.Accounts -AllowClobber -Scope CurrentUser
}

# Import required modules
Import-Module Az.Accounts
Import-Module Microsoft.PowerApps.PowerShell
Import-Module Microsoft.PowerApps.Administration.PowerShell

# global variable declaration
$filter = '$filter'

# Function to authenticate interactively and retrieve an access token
function Get-AccessToken {
    Write-Host "Authenticating interactively..." -ForegroundColor Green

    # Retrieve the access token for the Dataverse environment
    $accessToken = (Get-AzAccessToken -ResourceUrl "$dataverseUrl").Token
    Write-Host "Access token retrieved successfully." -ForegroundColor Green
    return $accessToken
}

# update the enviornment from user input
function Update-EnvironmentVariables {
    param (
        [string]$accessToken   # Access token for authentication
    )
    write-host "Updating environment variables..." -ForegroundColor Yellow

    foreach ($key in $environmentVariables.PSObject.Properties.Name) {
        $value = $environmentVariables.$key
        Write-Host "Updating environment variable: $key with value: $value" -ForegroundColor Yellow

        # Get the environment variable definition
        $envVarDefinition = Invoke-RestMethod -Method Get -Uri "$dataverseUrl/api/data/v9.2/environmentvariabledefinitions?$filter=schemaname eq '$key'" -Headers @{
            Authorization = "Bearer $accessToken"
        }

        if ($envVarDefinition.value -ne $null) {
            $envVarDefId = $envVarDefinition.value[0].environmentvariabledefinitionid

            # Get the environment variable value record
            $filterValue = [System.Web.HttpUtility]::UrlEncode("_environmentvariabledefinitionid_value eq $envVarDefId")
            $envVarValue = Invoke-RestMethod -Method Get -Uri "$dataverseUrl/api/data/v9.2/environmentvariablevalues?$filter=$filterValue" -Headers @{
                Authorization = "Bearer $accessToken"
            }

            if ($envVarValue.value -ne $null) {
                $envVarValueId = $envVarValue.value[0].environmentvariablevalueid

                # Update the environment variable value
                Invoke-RestMethod -Method Patch -Uri "$dataverseUrl/api/data/v9.2/environmentvariablevalues($envVarValueId)" -Headers @{
                    Authorization = "Bearer $accessToken"
                    "Content-Type" = "application/json"
                } -Body (@{ value = $value } | ConvertTo-Json -Depth 1)
            } else {
                Write-Host "Environment variable value not found for $key. Skipping..." -ForegroundColor Red
            }
        } else {
            Write-Host "Environment variable definition not found for $key. Skipping..." -ForegroundColor Yellow
        }
    }
}

# Function to publish the solution
function Publish-Solution {
    param (
        [string]$accessToken
    )

    Write-Host "Publishing All" -ForegroundColor Yellow

    # Construct the API endpoint for publishing the solution
    $uri = "$dataverseUrl/api/data/v9.2/PublishAllXml"


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

    Write-Host "Retrieving GUID for flow: $flowName" -ForegroundColor Yellow

    # Construct the API endpoint with a filter for the flow name
    $encodedFlowName = [System.Web.HttpUtility]::UrlEncode($flowName)
    $uri = "$dataverseUrl/api/data/v9.2/workflows?$filter=name eq '$encodedFlowName'"

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
        [string]$dataverseUrl,  # Dataverse environment URL
        [string]$accessToken,   # Access token for authentication
        [string]$flowId         # GUID of the flow to activate
    )

    Write-Host "Activating flow: $flowId" -ForegroundColor Yellow

    # Construct the request body
    $body = @{
        "statecode" = 1  # Activated
        "statuscode" = 2 # Activated
    } | ConvertTo-Json -Depth 1 -Compress

    # Construct the API endpoint
    $uri = "$dataverseUrl/api/data/v9.2/workflows($flowId)"

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
    $uri = "$dataverseUrl/api/data/v9.2/connectionreferences?$filter=connectionreferencelogicalname eq '$connectionRefLogicalName'"
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


# Function to update a connection reference with a connection ID
function Update-ConnectionReference {
    param (
        [string]$accessToken,
        [string]$connectionRefName,
        [string]$connectionId
    )

    Write-Host "Connection Update for connection reference: $connectionRefName with connection ID: $connectionId" -ForegroundColor Yellow

    $connectionRefId = Get-ConnectionRefIdFromLogicalName -accessToken $accessToken -connectionRefLogicalName $connectionRefName

    if ($connectionRefId -eq $null) {
        Write-Host "Connection reference not found for logical name: $connectionRefName" -ForegroundColor Red
        return
    }
    else {
        Write-Host "Connection reference ID: $connectionRefId" -ForegroundColor Green
    }

    $body = @{
        "connectionid" = "$connectionId"
    } | ConvertTo-Json -Depth 1

    $uri = "$dataverseUrl/api/data/v9.2/connectionreferences($connectionRefId)"
    write-host "Updating connection reference URI: $uri" -ForegroundColor Yellow

    Invoke-RestMethod -Method Patch `
            -Uri $uri `
            -Headers @{
            Authorization = "Bearer $accessToken"
            "Content-Type" = "application/json"
        } `
        -Body $body

    Write-Host "Connection reference updated successfully." -ForegroundColor Green
}

# Function iterate over connectionlist
function VerifyConnectorsExist {
    param (
        [array]$connectionList,
        [string]$accessToken
    )
    $connectionNames = New-Object System.Collections.ArrayList


    foreach ($connector in $connectors) {
        $connectorName = $connector.Name
        $connectorId = $connector.id

        $connectionRefName = $connector.connectionRefName
        # Write-Host "Verifying connector: $connectorName with id: $connectorId" -ForegroundColor Yellow

        foreach ($connection in $connectionList) {
            # Write-Host "Verifying connection: $connection" -ForegroundColor Yellow
            $connectorNameFromList = $connection.ConnectorName
            $connectionIdFromList = $connection.ConnectionId
            $connectionNameFromList = $connection.ConnectionName
            $statusesFromList = $connection.Statuses | ForEach-Object { $_.status }
            Write-Host "connections connectorNameFromList: $connectorNameFromList with status: $statusesFromList and Id: $connectionIdFromList " -ForegroundColor Yellow

            # Check if the name exists in the connection list and status is "Connected"
            if ($connectorName -eq $connectorNameFromList -and $statusesFromList -contains "Connected") {
                Write-Host "Connector $connectorName exists in the connection list with status 'Connected'." -ForegroundColor Green

                # Check if the connector ID is not empty
                if ($connectorId -ne "") {
                    Write-Host "Connector ID: $connectorId" -ForegroundColor Yellow
                    if ($connectionNameFromList -contains $connectorId) {
                        Write-Host "Matching connector ID found: $connectorId" -ForegroundColor Green
                        $connectionNames.Add(@($connectionNameFromList, $connectionRefName)) | Out-Null
                        $found = $true
                        break
                    }
                } else {
                    Write-Host "Connector ID is empty for $connectorName. Using existing connection." -ForegroundColor Green
                    $connectionNames.Add(@($connectionNameFromList, $connectionRefName)) | Out-Null
                    $found = $true
                    break
                }
            }
        }

        if (-not $found) {
            Write-Host "Connector $connectorName does not exist in the connection list or is not 'Connected'." -ForegroundColor Red
        }
    }
    return $connectionNames
}

# Load configuration from JSON file
function Load-Configuration {
    param (
        [string]$configFilePath,
        [string]$moduleName
    )

    if (-not (Test-Path $configFilePath)) {
        Write-Host "Configuration file not found: $configFilePath" -ForegroundColor Red
        throw "Configuration file not found."
    }

    $config = Get-Content -Path $configFilePath | ConvertFrom-Json
    if (-not $config.modules.$moduleName) {
        Write-Host "Module '$moduleName' not found in configuration." -ForegroundColor Red
        throw "Module not found."
    }

    Write-Host "Configuration for module '$moduleName' loaded successfully." -ForegroundColor Green
    return $config.modules.$moduleName
}

#  check connections present
function Check-Connections {
    param (
        [string]$accessToken,
        [string]$userId
    )

    Write-Host "Checking connections for environment id $environmentId" -ForegroundColor Yellow

    # Get the list of existing connections
    $connectionList = Get-PowerAppConnection -EnvironmentName $environmentId

    # Verify if the connectors exist and are connected
    $connectionOutput = VerifyConnectorsExist -connectionList $connectionList -accessToken $accessToken

    if ($connectionOutput.Count -eq 0) {
        Write-Host "No valid connections found. Please goto maker portal to create all the required connections." -ForegroundColor Red
        exit(0)
    } else {
        if ($connectionOutput.Count -eq  $connectors.Count) {
            Write-Host "All the connectors are present" -ForegroundColor Green
        } else {
            Write-Host "$($connectionOutput.Count) out of $($connectors.Count) Present. Please goto maker portal to create all the required connections." -ForegroundColor Red
            exit(0)
        }
        return $connectionOutput
    }
}

function Link-ConnectionReferences {
    param (
        [string]$accessToken,
        [array]$connectionOutput
    )

    foreach ($connection in $connectionOutput) {
        $connectionName = $connection[0]
        $connectionRefName = $connection[1]
        Write-Host "connectionName $connectionName connectionRefName $connectionRefName." -ForegroundColor Yellow

        # Update the connection reference with the connection ID
        if ( $connectionRefName -ne "") {
            Write-Host "Updating connection reference: $connectionRefName with connection ID: $connectionName" -ForegroundColor Yellow
            Update-ConnectionReference -accessToken $accessToken -connectionRefName $connectionRefName -connectionId $connectionName
        } else {
            Write-Host "No connection reference found for logical name: $connectionRefName. Skipping the linkage" -ForegroundColor Yellow
        }
    }

}

function Activate-Flows {
    param (
        [string]$accessToken,
        [array]$expenseAIFlows
    )

    foreach ($flowName in $expenseAIFlows) {
        Write-Host "Retrieving GUID for flow: $flowName" -ForegroundColor Yellow

        # Call the Get-FlowGuidByName function to get the flow GUID
        $flowGuid = Get-FlowGuidByName -dataverseUrl $dataverseUrl -accessToken $accessToken -flowName $flowName

        if ($flowGuid -ne $null) {
            Write-Host "Flow Name: $flowName, Flow GUID: $flowGuid" -ForegroundColor Green
            Activate-Flow -dataverseUrl $dataverseUrl -accessToken $accessToken -flowId $flowGuid
            # Write-Host "Flow Name: $flowName, Flow GUID: $flowGuid Activated" -ForegroundColor Green
        } else {
            Write-Host "Flow Name: $flowName not found." -ForegroundColor Red
        }
    }
}


# Function to retrieve the Agent ID by name
function Get-AgentIdBySchemaName {
    param (
        [string]$dataverseUrl,
        [string]$accessToken,
        [string]$agentSchemaName
    )

    Write-Host "Retrieving agent ID for agent schema: $agentSchemaName" -ForegroundColor Yellow

    # Construct the API endpoint to retrieve the bot
    $uri = "$dataverseUrl/api/data/v9.2/bots?$filter=schemaname eq '$agentSchemaName'"

    try {
        # Make the API call
        $response = Invoke-RestMethod -Method Get -Uri $uri -Headers @{
            Authorization = "Bearer $accessToken"
            "Content-Type" = "application/json"
        }

        if ($response.value.Count -gt 0) {
            $agentId = $response.value[0].botid
            Write-Host "Agent found: $agentSchemaName with ID: $agentId" -ForegroundColor Green
            return $agentId
        } else {
            Write-Host "No agent found with the name: $agentSchemaName" -ForegroundColor Red
            return $null
        }
    } catch {
        Write-Host "Failed to retrieve agent ID. Error: $($_.Exception.Message)" -ForegroundColor Red
        return $null
    }
}

# Function to publish a PVA bot
function Publish-Agent {
    param (
        [string]$dataverseUrl,
        [string]$accessToken,
        [string]$agentId
    )

    Write-Host "Publishing agent with ID: $agentId" -ForegroundColor Yellow

    # Construct the API endpoint for publishing the bot
    $uri = "$dataverseUrl/api/data/v9.2/bots($agentId)/Microsoft.Dynamics.CRM.PvaPublish"

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
        Write-Host "Publishing agent schema: $agentSchema" -ForegroundColor Yellow

        try {
                # Construct the API endpoint for publishing the agent schema
                $agentId = Get-AgentIdBySchemaName -dataverseUrl $dataverseUrl -accessToken $accessToken -agentSchemaName $agentSchema

                if ($agentId -ne $null) {
                    # Step 4: Publish the bot
                    Publish-Agent -dataverseUrl $dataverseUrl -accessToken $accessToken -agentId $agentId
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

    # Step 0: Load Configuration
    $configFilePath = ".\AgentConfig.json"
    $moduleName   = $ConfigModuleName # Change this to "Time" or "Approvals" as needed
    $moduleConfig = Load-Configuration -configFilePath $configFilePath -moduleName $moduleName
    $environmentVariables = $moduleConfig.environmentVariables
    $connectors = $moduleConfig.connectors
    $expenseAIFlows = $moduleConfig.flows
    $agentSchemas = $moduleConfig.agents

    # Step 1: Interactive login to Azure
    Connect-AzAccount -UseDeviceAuthentication
    $accessToken = Get-AccessToken
    $userId  = (Get-AzAccessToken).UserId
    write-host "User ID: $userId" -ForegroundColor Yellow

    # Step 2: Setup environment variables
    Update-EnvironmentVariables -accessToken $accessToken 
    Write-Host "Environment variables updated successfully!" -ForegroundColor Green

    # Step 3: Check active connections
    $connectionOutput = Check-Connections -accessToken $accessToken -userId $userId

    # Step 4: Link connection references
    Link-ConnectionReferences -accessToken $accessToken -connectionOutput $connectionOutput

    # Step 5: Activate flows
    Activate-Flows -accessToken $accessToken -expenseAIFlows $expenseAIFlows

    # step 6: publish the agents
    Publish-Agents -accessToken $accessToken -agentSchemas $agentSchemas

    # Step 7: Publish the solution 
    Publish-Solution -accessToken $accessToken

    Write-Host "Agent setup completed successfully!" -ForegroundColor Green

} catch {
    Write-Host "An error occurred: $_" -ForegroundColor Red
}
```

The preceding script performs these actions:

- Set environment variables.
- Verify and link connection references.
- Enable Power Automate flows.
- Publish the required Copilot agents.
- Publish the Dataverse solution.

After the script runs successfully, the Expense Entry feature of the Time and Expense Agent is fully configured and ready to use.

### Option 2: Do manual setup in Power Apps (no PowerShell)

If you prefer not to use the PowerShell script, you can manually configure the Expense Entry feature of the Time and Expense Agent through Power Apps. This process involves updating environment variables, enabling Power Automate flows, and publishing the solution.

#### Update environment variables

To update environment variables, follow these steps.

1. Sign in to [Power Apps](https://make.powerapps.com/), and select your environment.
1. Select **Solutions**, then open **Default Solution** (or the solution where the agent is installed).
1. Go to **Environment Variables**, and set the following values.

    | Variable name | Description |
    |---|---|
    | Expense Agent Outlook Folder Path | Specify the folder path to monitor in the shared mailbox (by default, **Inbox**). |
    | Expense Agent Shared Mailbox Address ID | Specify the email address of the shared mailbox. To use the mailbox of the signed-in user, enter **NA**. |
    | Finance and Operations Instance Url | Specify the URL of the finance and operations apps environment (for example, `https://xxxxx.operations.dynamics.com`). |

#### Enable Power Automate flows

The Expense Entry feature of the Time and Expense Agent relies on the following Power Automate flows:

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

After you complete these steps, the Expense Entry feature of the Time and Expense Agent is fully configured and ready to use.

## Step 7: Enable the Expense Entry feature of the Time and Expense Agent

To enable Teams-based communication through the Expense Entry feature of the Time and Expense Agent, you must add the Teams channel to the agent in Power Apps. The agent can then send adaptive cards and receive input via Teams.

### Enable the Teams channel

To enable the Teams channel, follow these steps.

1. Sign in to [Power Apps](https://make.powerapps.com/).
1. On the **Agents** tab, select **Expense Entry Agent**.
1. In the agent view, on the **Channels** tab, select **Microsoft Teams**.
1. Select **Add channel** to enable Teams integration. Learn more in [Open the configuration panel for the Teams + Microsoft 365 channel](/microsoft-copilot-studio/publication-add-bot-to-microsoft-teams#open-the-configuration-panel-for-the-microsoft-teams-channel).

### Configure Teams app availability

To configure Teams app availability, follow these steps.

1. After the Teams app is created, select **Availability Options**.
1. Select who you want to share the app with:

    - Specific users within the organization
    - The entire organization

1. Submit the app for approval.

### Publish the app in the Teams admin center

To publish the app in the Teams admin center, follow these steps.

1. Sign in to the [Teams admin center](https://admin.teams.microsoft.com/).
1. Publish the app for approved use.
1. Assign app setup policies to users.
1. As required, update permission policies to allow agent access based on your organization's Teams settings.

Learn more in [Connect and configure an agent for Teams and Microsoft 365](/microsoft-copilot-studio/publication-add-bot-to-microsoft-teams).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
