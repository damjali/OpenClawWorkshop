# 🤖 OpenClaw Telegram Bot Integration Guide

This guide will help you:

- Create a Telegram bot using BotFather
- Obtain your Telegram Bot API Token
- Connect Telegram to OpenClaw
- Pair Telegram with your OpenClaw instance
- Chat with your OpenClaw agent directly from Telegram

Everything below is designed to be copy-paste friendly.

---

# 📋 Prerequisites

Before starting, make sure you already have:

- OpenClaw installed
- OpenClaw OnBoard working
- A Telegram account
- Internet connection

---

# 1️⃣ Setup Telegram Bot

---

## Step 1 — Open Telegram

Open the Telegram application on:

- Desktop
- Mobile
- Browser

---

## Step 2 — Search for BotFather

Search for:

```text
BotFather
```

Official bot:

```text
@BotFather
```

---

## Step 3 — Start BotFather

Send:

```text
/start
```

---

## Step 4 — Create a New Bot

Send:

```text
/newbot
```

BotFather will ask for:

1. Bot Name
2. Bot Username

---

## Step 5 — Enter Bot Name

Example:

```text
Jarvis Assistant
```

---

## Step 6 — Enter Bot Username

⚠️ IMPORTANT:

The username:
- MUST be unique
- MUST end with:

```text
_bot
```

Example:

```text
jarvis_calendar_bot
```

---

## Step 7 — Copy Telegram Bot API Token

BotFather will generate a token similar to:

```text
123456789:AAEXAMPLE_TOKEN_HERE
```

Copy and save this token.

> ⚠️ Keep this token private.

---

# 2️⃣ Setup Telegram in OpenClaw

---

## Step 1 — Launch OpenClaw OnBoard

Run:

```bash
openclaw onboard
```

---

## Step 2 — Configure OnBoard Settings

Follow these settings carefully.

| Setup Step | Recommended Option |
|---|---|
| Personal / Shared | Yes |
| Setup Mode | Quick Start |
| Config Handling | Use Existing Values |
| Default Model | Keep Current |
| Select Channel | Telegram (Bot API) |
| Telegram Setup | Enter Telegram Bot Token |
| Bot Token | Paste your Telegram Bot Token |
| Search Provider | DuckDuckGo |
| Configure Skills | No |
| Hooks | Skip for now |

---

# 3️⃣ Pair Telegram With OpenClaw

After setup, Telegram will generate a:

```text
Pairing Code
```

Copy the pairing code.

Then run:

```bash
openclaw pairing approve telegram <Pairing Code>
```

Example:

```bash
openclaw pairing approve telegram ABC123
```

---

# 4️⃣ Restart OpenClaw Gateway

After pairing, restart the gateway service.

Run:

```bash
openclaw restart
```

Or restart directly from OnBoard.

---

# 5️⃣ Test Your Telegram Bot

Open Telegram and:

1. Search for your bot username
2. Open the bot chat
3. Press:

```text
Start
```

4. Send a message

Example:

```text
Hello Jarvis
```

If configured correctly, OpenClaw should reply.

---

# 6️⃣ Open OpenClaw Dashboard

To monitor logs or restart services, open the dashboard again:

```bash
openclaw onboard
```

Then open the Web UI from the dashboard.

---

# ✅ Setup Complete

You now have:

- Telegram Bot Integration
- OpenClaw Telegram Channel
- AI Chat Access Through Telegram
- OpenClaw Pairing System Enabled

You can now interact with your OpenClaw agent directly from Telegram.

---

# 🛠 Useful OpenClaw Commands

---

## Open Dashboard

```bash
openclaw onboard
```

---

## Restart OpenClaw

```bash
openclaw restart
```

---

## View Live Logs

```bash
openclaw logs --follow
```

Short version:

```bash
openclaw logs -f
```

---

## Check Service Status

```bash
openclaw status
```

---

## Stop Services

```bash
openclaw stop
```

---

## Start Services

```bash
openclaw start
```

---

# 🤖 Telegram Pairing Commands

---

## Approve Telegram Pairing

```bash
openclaw pairing approve telegram <Pairing Code>
```

---

## View Pairing Status

```bash
openclaw pairing list
```

---

# 🚨 Troubleshooting

---

## Problem: Bot Not Replying

Try restarting OpenClaw:

```bash
openclaw restart
```

Then test again.

---

## Problem: Invalid Telegram Token

Solution:
- Re-copy token from BotFather
- Ensure there are no spaces
- Paste token again during setup

---

## Problem: Pairing Failed

Solution:
- Re-run pairing command
- Ensure the pairing code is correct
- Restart OpenClaw after pairing

---

## Problem: Telegram Bot Not Found

Solution:
- Ensure the username ends with `_bot`
- Ensure the bot was created successfully in BotFather

---

# 🚀 Recommended Next Steps

After Telegram integration, you can:

- Connect Google Calendar
- Install GOGCLI
- Create custom AI agents
- Automate workflows
- Connect APIs
- Build autonomous assistants
- Use OpenRouter premium models

---

# 🎯 You're Ready

Your OpenClaw AI assistant can now communicate directly through Telegram.
