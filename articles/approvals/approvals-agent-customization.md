---
title: Customize data sent to the Approvals Agent (preview)
description: Learn how to customize what data is sent to the Approvals agent. 
author: abriccetti
ms.author: abriccetti
ms.date: 10/21/2025
ms.topic: how-to
ms.custom: 
 - bap-template
ms.reviewer: johnmichalak
---

# Customize data sent to the Approvals Agent (preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

When the Approvals Agent is triggered, it receives a predefined set of data related to the submitted record. This article explains how to customize that data for customers who want the agent to make decisions based on data outside that predefined set. You can modify the Power Automate flow used to trigger the agent.

## Modify the trigger flow

The default Approvals agent trigger flow has three steps:

1. Call the GetApprovalDataSignals API to retrieve data signals for the specified number of approval records.
1. Parse these data signals into a JSON object.
1. In an apply to each loop, send each set of data signals (one per project approval record) as a message to the Approvals agent to initiate it.

To add information to the data signals, add steps to gather data and add it to the data signals inside the apply to each loop. The following section outlines an example of one such customization.

### Example of a customized trigger flow

In this environment, you customize the time entry record by adding a field called threshold value. You also add a rule to the policy document for time entries so only entries with a threshold value greater than 100 should be marked as ready for approval. To enable the agent to make this decision, you need to add the threshold value to the set of data signals sent to the agent.

To start, add a switch statement inside the Apply to each loop with the value of the entry type from the parsed JSON deciding which branch the flow takes. Because the customization in this environment is only to the time entry entity, the switch statement has only two paths: one if the entry is of type time, and one for all other entries (default). 

In the default branch, you can send the parsed JSON to the agent in the same manner as the unedited trigger flow. However, in the time entry branch, you need to add three extra steps. The threshold value exists in the time entry record, but only the ID of the project approval record is included in the default set of data signals. Therefore, first retrieve the project approval record by using the Get a row by ID action from the Dataverse connector and the ID from the data signals. Then, call get a row by ID again, this time using the ID of the linked time entry from the retrieved project approval record.

With the time entry record retrieved, all that remains is to append the threshold value to the data signals, and send that to the agent. You can append the value by using the compose action with the following argument: "addProperty(items('Apply_to_each'),'Threshold Value', outputs('Get_Time_Entry_from_Project_Approval')?['body/cradf_thresholdvalue'])" (where 'Get_Time_Entry_from_Project_Approval' is the title of the previous step and cradf_threshold value is the logical name of the customized column). All that remains is to send the new set of data signals to the agent by using the Execute Copilot action from the Microsoft Copilot Studio connector, ensuring to choose the Approvals agent and in the Body/message parameter add the output of the previous step.

The final result looks like this:

:::image type="content" source="media/customize-approvals-agent.png" alt-text="Screenshot of a finished customization to the approvals agent trigger flow.":::

Now the agent is able to make approvals decisions based on the custom column threshold value:

:::image type="content" source="media/customization-outcome.png" alt-text="Screenshot of an approval record which the agent has classified based on the custom data.":::
