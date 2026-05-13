# OpenClaw Workshop — Google Calendar Agent Integration Guide

## Objective
In this workshop, participants will learn how to:

- Create an OpenClaw AI agent
- Connect the agent to Google Calendar using OAuth
- Authenticate using GOGCLI
- Allow the agent to:
  - View upcoming meetings
  - Read calendar schedules
  - Book future appointments automatically

---

# Prerequisites

Before starting the workshop, participants MUST prepare the following:

## 1. Create Google OAuth Credentials

Participants need to prepare a Google OAuth Consent configuration and download the OAuth Secret JSON file.

### Steps
https://console.cloud.google.com/apis/credentials/consent?project=decisive-plasma-496209-s8
1. Go to the Google Cloud Console:
   - https://console.cloud.google.com/
2. search google calendar api in the searchbar and enable Google Calendar API
4. Open OAuth Consent Screen
5. Click on get started
6. enter app information (OpenClaw App etc)
7. select your email in user support email
8. select external as audience
9. enter your email in contact information
10. Click agree and finish
11. click on create
12. click on clients
13. create a oauth client ID
14. Set application type as desktop app
15. set name to (OpenClaw App etc)
16. download the Client Secret json file and save it for later (important)
17. Click on Audience Section on the sidebar
18. add you email inside the test users section, and click on save

Example Client Secret JSON filename:

```bash
client_secret_xxxxx.json
```

Keep this file safe because it will be used during authentication.

---

# Enable GOGCLI Skill

## 1. Install GOGCLI

Inside OpenClaw terminal:

```bash
openclaw skills install gogcli
```

---

## 2. Check is enabled GOGCLI

Run:

```bash
openclaw gateway restart
openclaw onboard
```

And then, go to skills section, and make sure the skill "gogcli" is enabled

# Connect Jarvis-Calendar to Google Calendar

After authentication is completed, open your Open Claw agent (Open the agent that is connected to your telegram if possible) and send the following prompt.

---

## Prompt to Send

```text
<make sure to attach the secret key file(IMPORTANT)> /gog using this skill, Connect with my google calendar api so that you are able to connect with my google calendar and see my calendar schedule and book future meetings. Use the provided Secret key file and connect with my google calendar. for authentication link methods, make sure to use --remote to avoid any problems of authentication
```
Continue on doing the steps that OpenClaw Agent ask you to do.
---

# Expected Capabilities

Once connected successfully, the agent should be able to:

- Read your Google Calendar events
- View upcoming meetings
- Check schedule availability
- Create appointments
- Book future meetings
- Manage calendar workflows automatically

---

# Example Prompts After Setup

## View Upcoming Meetings

```text
Show my meetings for tomorrow
```

## Check Availability

```text
Do I have any free time this Friday afternoon?
```

## Create Appointment

```text
Book a meeting with John tomorrow at 3 PM for 1 hour
```

## Weekly Schedule

```text
Summarize my schedule for this week
```

---

# Troubleshooting

## Authentication Failed

Solution:
- Ensure your email is added under OAuth Test Users
- Re-download the OAuth Secret JSON file
- Use `--remote`

---

## Calendar Access Denied

Solution:
- Ensure Google Calendar API is enabled
- Make sure the correct Google account is used

---

## GOGCLI Not Found

Solution:

```bash
openclaw skills install gogcli
```

---

# Workshop Outcome

By the end of this workshop, participants will successfully:

- Configure Google OAuth
- Connect OpenClaw agents with Google Calendar
- Use GOGCLI authentication
- Build AI scheduling workflows with OpenClaw
