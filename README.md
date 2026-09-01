# Intuz — Your automation partner, one workflow at a time.

<p align="center">
  <picture>
    <img alt="Banner Image" src="https://github.com/user-attachments/assets/210f97fc-0fce-404a-b647-7dfe1302cd37" />
  </picture>
</p>

# Send pre-meeting Slack briefings using Google Calendar, Notion, GitHub, and Jira

[Intuz](https://www.intuz.com/) helps organizations orchestrate AI, automation, and enterprise systems through scalable workflows. Our repository showcases proven implementations across healthcare, operations, customer support, document processing, sales, and back-office functions, enabling teams to accelerate automation initiatives without starting from scratch

[N8N Creator](https://n8n.io/creators/intuz/) · [Generative AI Development Services](https://www.intuz.com/generative-ai-development/) · [AI Consulting](https://www.intuz.com/ai-transformation-services/) · [For Custom Workflow Automation](https://www.intuz.com/get-started/)

---

## This n8n template

This n8n template from Intuz provides a complete and automated solution for preparing and delivering context-rich briefings directly to attendees before every meeting.

It acts as an AI-powered executive assistant, gathering relevant information from all your key work tools to ensure everyone arrives prepared and aligned.

## Who's this workflow for?

* Engineering Managers & Team Leads
* Product Managers & Project Managers
* Scrum Masters & Agile Coaches
* Any team that holds regular status, planning, or technical meetings.

## How it works

### 1. Trigger on New Calendar Event

The workflow starts automatically whenever a new meeting is created in a designated Google Calendar.

### 2. Fetch Previous Context

It immediately connects to Notion to retrieve the notes from the most recent past meeting, ensuring continuity.

### 3. Wait for the Right Moment

The workflow calculates a time 15 minutes before the meeting's scheduled start and pauses its execution until then.

### 4. Gather Real-Time Project Data

Just before the meeting, the workflow wakes up and:

* Extracts keywords from the meeting title.
* Searches GitHub for recent Pull Requests (PRs) relevant to those keywords.
* Searches Jira for any tickets or issues that match the meeting's topic.

### 5. Build the Intelligent Briefing

It assembles all the gathered information—previous notes from Notion, current PRs from GitHub, and relevant tickets from Jira—into a single, beautifully formatted Slack message.

### 6. Deliver to Each Attendee

The workflow identifies all attendees from the Google Calendar invite, finds their corresponding Slack profiles via email, and sends the personalized briefing as a Direct Message (DM) to each one, ensuring everyone is prepared just in time.

## Key Requirements to Use This Template

1. **n8n Instance:** An active n8n account (Cloud or self-hosted).
2. **Google Calendar Account:** To trigger the workflow on new events.
3. **Notion Account:** With a dedicated database for storing meeting notes.
4. **GitHub Account:** To search for relevant pull requests.
5. **Jira Cloud Account:** To search for relevant project tickets.
6. **Slack Workspace & App:** A Slack workspace where you have permission to install an app. You will need a Bot Token with the necessary permissions.

## Setup Instructions

### Google Calendar Trigger

In the **"Capture New Google Calendar Event"** node, connect your Google Calendar account and select the calendar you want to monitor.

### Notion Connection

* In the **"Get Last Meeting Notes"** node, connect your Notion account.
* Select the Notion Database ID that contains your meeting notes.

### GitHub & Jira Connections

* In the **"Get PRs from Repo"** node, connect your GitHub account and select the repository to search.
* In the **"Get Jira Issues Related to Meeting"** node, connect your Jira Cloud account. You can customize the JQL query if needed.

### Slack Configuration (Crucial Step)

1. **Create a Slack App:** Go to [api.slack.com/apps](https://api.slack.com/apps), create a new app, and install it to your workspace.
2. **Set Permissions:** In your app's **"OAuth & Permissions"** settings, add the following Bot Token Scopes:

   * `chat:write` — to send messages
   * `users:read.email` — this is critical for looking up attendees
3. Reinstall the app to your workspace.
4. **Get Bot Token:** Copy the **"Bot User OAuth Token"** (it starts with `xoxb-`).
5. **Connect in n8n:**

   * In the **"Get User Slack Info from Email"** node, click **"Header Parameters"** and replace `{{ slack oauth token }}` with your actual Bot Token.
   * In the **"Send Meeting Context in Slack DM"** node, connect your Slack credentials using the same Bot Token.

### Activate the Workflow

Save the workflow and toggle the **"Active"** switch to ON. Your automated pre-meeting bot is now live!

## Connect with us

* **Website:** [https://www.intuz.com/n8n-workflow-automation-templates/](https://www.intuz.com/n8n-workflow-automation-templates/)
* **Email:** [getstarted@intuz.com](mailto:getstarted@intuz.com)
* **LinkedIn:** [https://www.linkedin.com/company/intuz/](https://www.linkedin.com/company/intuz/)
* **Get Started:** [https://n8n.partnerlinks.io/intuz/](https://n8n.partnerlinks.io/intuz)

## For Custom Workflow Automation

[Click here - Get Started](https://www.intuz.com/get-started/)
