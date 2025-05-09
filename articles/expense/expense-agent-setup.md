---
title: Expense Entry feature of the Time and Expense Agent Installation and Setup (preview)
description: Learn about the steps to install and set up the Expense Entry feature of the Time and Expense Agent.
author: alexeiantao
ms.author: alexeiantao
ms.date: 05/09/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Expense Entry feature of the Time and Expense Agent Installation and Setup (preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

The Expense Entry feature of the Time and Expense Agent brings together capabilities from Microsoft Dynamics 365 Project Operations, finance and operations apps, Microsoft Copilot Studio, Microsoft Power Automate, and Microsoft Dataverse to automate expense processing workflows using AI. The Expense Agen enables your system to process receipts and generate expense lines and reports for users to save time and reduce manual effort. It uses Microsoft Power Platform Connectors to integrate with Outlook, Microsoft Teams, user calendars, and the finance and operations apps environment via Dataverse virtual entities.

The Expense Entry feature of the Time and Expense Agent includes multiple flows, three of which serve as core orchestrators:

1. **Process Emails** – Scans a configured mailbox folder every hour and stores the attachments as unattached receipts in Dynamics 365 Finance.
2. **Extract Receipt IDs** – Picks up newly added receipts and triggers the agent to extract details.
3. **Process Expense Report** – Converts extracted receipt data into structured expense lines and generates reports, based on the configuration set in the application.

The agent also supports Teams integration that allows you to send adaptive cards for review and submission of expenses.

The agent relies on several Power Platform connectors. These connectors are automatically referenced within the provided Microsoft Power Automate flows:

- **Outlook (Office 365)** – Accesses the shared mailbox to fetch receipts.
- **Dataverse (Virtual Entities)** – Integrates with Dynamics 365 Finance and Operations entities.
- **Microsoft Copilot Studio** – Invokes AI models to extract receipt information.
- **Microsoft Teams** – Sends adaptive cards for user interactions (if Teams integration is enabled).
- **Microsoft 365 Users** – Retrieves user calendar details (optional, if receipt parsing is context-aware).

Installing and setting up the Expense Entry feature of the Time and Expense Agent involves the following steps:

1. Install Copilot for finance and operations apps.  
2. Activate the agent within Dynamics 365 Finance and Operations.
3. Create an expense user account for agent execution.  
4. Assign permissions in finance and operations apps and Dataverse.  
5. Set up a shared mailbox for email-based receipt collection.  
6. Configure and set up the agent, either manually or using Windows PowerShell.  
7. Enable Microsoft Teams integration (optional).

Each of these steps is described in detail in the sections that follow.

## Prerequisites

To complete the steps described in this article, you must have **System administrator** or **System customizer** access in the Power Platform admin center, **System administrator** access in finance and operations apps, and **Exchange administrator** access in Microsoft 365 to configure the shared mailbox. If you plan to enable Teams integration, you also need the required permissions in the **Teams admin center**.

### Step 1: Install Copilot for finance and operations apps

The Expense Entry feature of the Time and Expense Agent is delivered as part of the **Copilot for finance and operations** package. Once this package is installed in your environment, all required assets including the agent, environment variables, and Power Automate flows become available automatically.

Learn more about enabling Copilot in your environment in [Enable Copilot capabilities in finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/copilot/enable-copilot).

### Step 2: Activate the agent in finance and operations apps

To activate the agent in finance and operations apps, follow these steps.

1. After installing the package, activate the Expense Entry feature of the Time and Expense Agent from the finance and operations web application.
1. Go to **Feature Management** and ensure **Agent Management** is enabled.
1. Go to **Expense Management > Setup > Expense Management Parameters > Expense Entry feature of the Time and Expense Agent**.
1. Enable the agent for the current legal entity and configure the run frequency as either **daily** or **weekly**. You can also choose to group expenses by **Trip** or **Project** using the *Expense group by* setting.

### Step 3: Set up the agent user

Create a dedicated expense agent user to ensure that the agent runs independently of any employee’s identity. This helps with security, manageability, and long-term maintainability. While it's possible to use an existing user account with sufficient privileges, using a system-owned identity is the preferred approach.

#### A. Create the user Microsoft Azure Active Directory (Azure AD DS)

1. Go to the [Azure portal](https://portal.azure.com/) and create a new user under **Microsoft Entra ID**.

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

To successfully configure and run the Expense Entry feature of the Time and Expense Agent, the designated agent user must be granted the following permissions:

#### Finance and operations roles

- **System Administrator**  
  Required to allow the agent to create and manage expense entries within the Finance and Operations environment.

#### Dataverse roles

- **System Customizer**  
- **Expense AI Agent Role**  
- **Finance and Operations Agent Configuration Role**

These roles enable the agent to interact with Power Automate flows, environment variables, and virtual entities connected to Dynamics 365 Finance.

#### Shared mailbox access

The agent user must also have the Microsoft Graph permission **Mail.Shared.Read** that allows the agent to read receipts from the configured shared mailbox during flow execution.

### Step 5: Set Up the shared mailbox

The Expense Entry feature of the Time and Expense Agent uses a shared mailbox to receive receipt emails. This mailbox must be created and configured in the Microsoft 365 Admin Center by a user with the **Exchange Admin** role.

To create and configure the shared mailbox, follow these steps.

1. Go to the [Microsoft 365 Admin Center](https://admin.microsoft.com/) and sign in with an Exchange Admin account.
1. In the left-hand navigation pane, select **Teams & Groups > Shared mailboxes**.  
   If you don’t see it immediately, select **Show all** to expand the list.
1. Select **Add a shared mailbox**.
1. Enter a name and email address for the shared mailbox.  
   *Recommended format:* expenseagent@contoso.com
1. Select **Save changes**. It may take a few minutes before member management becomes available.
1. Under **Next steps**, choose **Add members to this mailbox**.
1. Select the agent user (and any others who should monitor the mailbox), then select **Add** and **Close**.

Once the mailbox is set up, provide its email address and the folder path (default: Inbox) as environment variables when configuring the Expense Agent.

### Step 6: Set up the Expense Entry feature of the Time and Expense Agent

You can set up the Expense Entry feature of the Time and Expense Agent using one of two options:
 - Option 1: Using PowerShell Script (Recommended)
 - Option 2: Manual Setup Using Maker Portal (No PowerShell)

#### Option 1: Using PowerShell Script (recommended)

Setting up the agent manually involves creating and linking connections, enabling Power Automate flows, and publishing the solution—a process that can be time-consuming and error-prone. You can use a PowerShell script and configuration file (AgentConfig.json) to automate the setup.

The PowerShell script automates:

- Updating required environment variables.
- Linking Power Platform connections with solution connection references.
- Enabling all Power Automate flows required by the Expense Agent.
- Publishing the Copilot agents.
- Publishing the Dataverse solution.

##### Configuration File Example (AgentConfig.json)

Before running the script, configure the file with values relevant to your environment:

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
}
```

##### Create the connections

To create the connections, follow these steps.

1. Go to the [Power Apps Maker Portal](https://make.powerapps.com/) and select your environment.
1. Navigate to **Connections**.
1. Select **New connection** and select the appropriate connector (for example, Outlook, Teams, etc.).
1. Once created, copy the **connection ID** and paste it into the **AgentConfig.json** file under the appropriate connector entry.

##### Run the script

Once your configuration is ready, run the following script after inserting the required environment variables:

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

    # Step 2: Setup ennviornment variables
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
The script will:

- Set environment variables  
- Verify and link connection references  
- Enable Power Automate flows  
- Publish the required Copilot agents  
- Publish the Dataverse solution  

After the script runs successfully, the Expense Entry feature of the Time and Expense Agent is fully configured and ready to use.


#### Option 2: Manual Setup Using Maker Portal (No PowerShell)

If you prefer not to use the PowerShell script, you can manually configure the Expense Entry feature of the Time and Expense Agent through the Power Apps Maker Portal. This process involves updating environment variables, enabling Power Automate flows, and publishing the solution.

##### 1. Update Environment Variables

To configure the agent, update the following environment variables.

1. Go to the [Power Apps Maker Portal](https://make.powerapps.com/) and select your environment.
1. Select **Solutions**, then open the **Default Solution** (or the solution where the agent is installed).
1. Navigate to **Environment Variables**, and set the following values:

| Variable Name                             | Description                                                                                     |
|------------------------------------------|-------------------------------------------------------------------------------------------------|
| Expense Agent Outlook Folder Path      | Folder path within the shared mailbox to monitor (default is **Inbox**).                         |
| Expense Agent Shared Mailbox Address ID| Email address of the shared mailbox. Use **NA** if using the signed-in user's mailbox.            |
| Finance and Operations Instance Url    | Finance and Operations environment URL (for example, `https://xxxxx.operations.dynamics.com`).         |

##### 2. Enable Power Automate Flows

The Expense Entry feature of the Time and Expense Agent relies on the following Power Automate flows:

- expense entry retry check  
- expense configuration  
- get expense outlook folder 
- generate expense report  
- send expense report adaptive card  
- process emails  
- extract unattached receipt IDs for copilot invocation  
- extract unattached receipt output using Dataverse plugin  
- generate expense line  
- generate expense line without project ID and status ID  
- identify project IDs  
- user calendar events  
- process expense report using copilot

To enable these flows, follow these steps.

1. Go to [Power Automate](https://make.powerautomate.com/) and select your environment.
1. Select **My Flows** and locate each of the Expense Entry feature of the Time and Expense Agent flows in the previous list.
1. For each flow:
   - Select **Edit**.
   - Switch to the **Old Designer** by toggling off the **New Designer**.
   - Authenticate any required connections (until green checkmarks appear).
   - Select **Continue** → **Save**.
   - Select **Turn On** to enable the flow.

Repeat this process for each of the 13 flows listed.


##### 3. Publish the solution

After all variables and flows are configured:

1. In the **Power Apps Maker Portal**, go to **Solutions**.
1. Select your environment and solution.
1. Select **Publish all customizations**.

After you complete these steps, the Expense Entry feature of the Time and Expense Agent is fully configured and ready to use without requiring any scripts.

### Step 7: Enable the Expense Entry feature of the Time and Expense Agent

To enable Teams-based communication using the Expense Entry feature of the Time and Expense Agent, you must add the Microsoft Teams channel to the agent through the Power Apps Maker Portal. Adding the channel allows the agent to send adaptive cards and receive input via Teams.

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
   - Specific users within the organization  
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
