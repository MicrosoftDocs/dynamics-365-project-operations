---
title: Start using the Time Entry Agent (for Team Members)
description: This article explains how team members can start using the Time Entry Agent through MS Teams.
author: mohitmenon
ms.date: 04/29/2025
ms.topic: how-to
ms.custom: 
  - bap-ai-copilot 
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Start using the Time Entry Agent as a Team Member

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

Once all steps to [enable the time entry agent for end users](enable-time-entry-agent.md) are completed by a system administrator, team members can now start using the agent. The interface used by the agent to communicate with team members is via MS Teams, as a Teams app. To begin using the agent through Teams, each user must first:
- Add the "Time Entry Agent (Preview)" Teams app, then
- Give consent to the agent for time entry creation and set certain preferences 

## Add the Time Entry Agent (Preview) Teams App

When your organization enables the agent and shares it with you, the agent can be accessed as a Teams app by following these steps:
1. Navigate to your MS Teams app or Teams in the browser using the same credentials used to log into your Project Operations environment.
2. Navigate to the **Apps** section within Teams.
3. The **Time Entry Agent (Preview)** app can be found under _Built for your organization_ or _Added by your org_ sections. Select the **Add** button for this app.
4. A pop-up may appear with more details about the app, proceed to **Add** it.
5. Once added, the option to **Open** the app becomes available. Click **Open**. This step takes you to a Teams chat where all interactions with the Time Entry Agent occur.

The next step involves giving consent to allow the agent to create time entries on your behalf.

> [!IMPORTANT]
> Reach out to your system administrator if this app isn't visible under your Teams apps.

## Give consent to the agent and set preferences
 
On opening the Teams app, you must ideally receive a message titled as "Logging Time made easy" (see image). 

:::image type="content" source="../media/userstartercard1.png" alt-text="Screenshot showing the starter message in Teams.":::

### Give consent for agent to create time entries
If this message doesn't come up automatically the first time you're using the app, you may send **Agent user preferences** or **Agent settings** in chat. This step loads the expected message.

Follow these steps to provide the agent with consent.
- Select **Get Started** on the initial message.
- You are asked if you'd like to allow the agent to create time entries on your behalf. Select **Yes**.

### Set agent preferences 
You have now provided the agent with consent to generate time entries for you, and will be shown 4 more configurable preferences. These preferences are required to decide how the agent goes about creating these entries and sending you alerts. 
1. **Source of time entries:** This preference allows a user to pick what sources the agent should use while creating time entries for them. A user can include one or more sources by checking each box. 
  - **Note:** _ If multiple sources are selected, the order of priority considered by the agent is Task Assignments > Project Bookings > Last week's entries. Last week's entries are only used in cases where there's no information for Assignments or Bookings for that user._
2. **Generate External Comments**: This preference allows the user to decide if each time entry being created must also have the **External Comment** field generated or not. Selecting **Yes** implies that the agent generates an external comment for each time entry that doesn't have one populated (even if the entry was manually created by the user).
3. **Use Outlook calendar for external comments**: Selecting **Yes** here implies that the agent enhances external comments by using **relevant Outlook meeting** details.
  - Selecting **No** implies the agent just uses details of the time entry like Project, Task, Role, etc to generate a relatively generic external comment.
4. **Time Zone**: This time zone is used by the agent to know which time zone the user operates in, and all alerts are sent by considering this time zone.

After selecting your preferences for each question, select **Save preferences**. You should receive a confirmation message that summarizes your selections.

### Modify agent preferences at a later time

Users can modify their existing preferences by: 
- Sending **Update Agent preferences** or just **Agent preferences** in chat.
- This step will bring up a summary of your existing preferences and allow you to modify the selections in the form.
- Once your preferences are updated, select **Save preferences**. 


### Share Outlook calendar access with the agent user

This step is required if you have selected **Yes** for _Using Outlook calendar to generate better external comments_. The agent user requires access to the team member's Outlook calendar, to be able to view meeting titles and descriptions for generating better comments. This access can be shared by:
- Navigating to Outlook -> Calendar
- Under **My Calendars**, select the **overflow icon** (three dots) for the calendar used by you.
- Select **Sharing and permissions**, then type in the **email ID of the agent user **(you may need to get this email ID from your IT system administrator).
- Hit **Share**.

After completing all of these one-time setup instructions, you've successfully set up the Time Entry Agent for use as a team member. From here on, the experience of logging time entries look like this:
- Agent creates Draft time entries for you at the start of a week
- You receive an alert on Teams from the agent summarizing entries created
- Review created time entries either in Teams or on the Project Operations web app
- Modify entries if necessary and Submit for approval

Proceed to the [next section](reviewing-entries-created-by-time-agent.md) to know more about the Time Entry Agent's behavior and the experience of reviewing alerts.


 [!INCLUDE[footer-include](../includes/footer-banner.md)]
