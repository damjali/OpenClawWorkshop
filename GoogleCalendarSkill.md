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

1. Go to the Google Cloud Console:
   - https://console.cloud.google.com/

2. Create a new project

3. Enable the following API:
   - **Google Calendar API**

4. Configure OAuth Consent Screen
   - User Type: External
   - Fill in required app information

5. Add your email under:
   - **Test Users**

6. Create OAuth Credentials
   - Type: Desktop App

7. Download the generated OAuth Secret JSON file

Example filename:

```bash
client_secret_xxxxx.json
```

Keep this file safe because it will be used during authentication.

---

# OpenClaw Setup

## 1. Create a New Agent

Inside OpenClaw, create a new agent named:

```text
Jarvis-Calendar
```

### Agent Configuration

Use:
- The SAME model configuration as your main OpenClaw session

---

# Enable GOGCLI Skill

## 1. Install GOGCLI

Inside OpenClaw terminal:

```bash
openclaw skills install gogcli
```

---

## 2. Authenticate GOGCLI

Before using the skill, authenticate first.

Run:

```bash
gogcli auth credentials --remote
```

### During Authentication

You will be asked to:

- Link your downloaded OAuth Secret JSON file
- Input your Google email address

Example:

```bash
gogcli auth credentials --remote --secret ./client_secret.json
```

> IMPORTANT:
> Always use `--remote` during workshop setup to avoid local authentication callback issues.

---

# Connect Jarvis-Calendar to Google Calendar

After authentication is completed, open your `Jarvis-Calendar` agent and send the following prompt.

---

## Prompt to Send

```text
/gog using this skill, Connect with my google calendar api so that you are able to connect with my google calendar and see my calendar schedule and book future meetings. Use the provided Secret key file <make sure to attach the secret key file> and connect with my google calendar. for authentication link methods, make sure to use --remote to avoid any problems of authentication
```

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
