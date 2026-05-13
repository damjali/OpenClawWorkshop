# 🐧 OpenClaw + OpenRouter + OnBoard UI Setup Guide (Windows WSL)

This guide will help you:

- Install WSL Ubuntu
- Install OpenClaw
- Install OpenClaw OnBoard Dashboard UI
- Connect OpenRouter
- Configure AI models
- Launch the browser dashboard
- Learn common troubleshooting commands

Everything below is designed to be beginner-friendly and copy-paste friendly.

---

# 📋 System Requirements

Recommended:

- Windows 10 / Windows 11
- Minimum 8GB RAM
- Stable internet connection
- Administrator access on Windows

Recommended browser:
- Google Chrome
- Microsoft Edge

---

# 1️⃣ Install WSL (Windows Subsystem for Linux)

Open **PowerShell as Administrator** and run:

```powershell
wsl --install
```

Once WSL installation finishes:

> ⚠️ IMPORTANT: You MUST restart your computer before continuing.

---

## Optional: Fresh Ubuntu Installation

If you already have WSL installed but want a fresh Ubuntu environment:

```powershell
wsl --install -d Ubuntu
```

Restart your computer if prompted.

---

# 2️⃣ Open Ubuntu

After restarting:

1. Open Start Menu
2. Search:

```text
Ubuntu
```

3. Open Ubuntu

Ubuntu will ask you to create:

- Linux Username
- Linux Password

> ⚠️ Password will NOT appear while typing. This is normal.

---

# 3️⃣ Update Ubuntu

Copy and paste:

```bash
sudo apt update && sudo apt upgrade -y
```

This may take several minutes.

---

# 4️⃣ Install Required Dependencies

Copy everything below in ONE GO:

```bash
sudo apt install -y curl git build-essential

curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -

sudo apt install -y nodejs

node -v
npm -v
```

Expected output example:

```bash
v20.x.x
10.x.x
```

---

# 5️⃣ Install Homebrew (Linuxbrew)

Copy everything below ONE BY ONE:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Then:

```bash
test -d ~/.linuxbrew && eval "$(~/.linuxbrew/bin/brew shellenv)"
```

```bash
test -d /home/linuxbrew/.linuxbrew && eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
```

```bash
echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> ~/.bashrc
```

```bash
source ~/.bashrc
```

Verify brew installation:

```bash
brew --version
```

---

# 6️⃣ Verify Node.js is in PATH

Run:

```bash
which node
which npm
```

Expected output example:

```bash
/usr/bin/node
/usr/bin/npm
```

If nothing appears:
- Restart Ubuntu
- Re-run the commands

---

# 7️⃣ Install OpenClaw

Copy and paste:

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

After installation, verify:

```bash
openclaw --version
```

---

# 8️⃣ Launch OpenClaw OnBoard Dashboard

Run:

```bash
openclaw onboard
```

This launches the setup dashboard.

---

# 9️⃣ Create an OpenRouter Account

Open:

```text
https://openrouter.ai
```

Then:

1. Sign in
2. Go to homepage
3. Click:
   - "Get API Key"
4. Create a new key
5. Give it a name
6. Copy the API key

> ⚠️ Save your API key securely.

---

# 🔟 Configure OpenClaw OnBoard

Run again if needed:

```bash
openclaw onboard
```

Follow these recommended settings:

| Setup Step | Recommended Option |
|---|---|
| Personal / Shared | Yes for personal |
| Setup Mode | QuickStart |
| Config Handling | Update Values |
| Model Provider | OpenRouter |
| API Key | Paste OpenRouter API Key |
| Default Model | Enter Model Manually |
| Model Name | `openrouter/deepseek/deepseek-v4-flash` |
| Select Channel | Skip for now |
| Search Provider | DuckDuckGo |
| Configure Skills | No |
| Install Missing Dependencies | No |
| Hooks | Skip for now |
| Gateway Service | Restart |

---

# 1️⃣1️⃣ Open the Dashboard UI

Inside OnBoard:

1. Click:
   - "Open the Web UI"

2. Copy the generated Dashboard URL with Token

Example:

```text
http://localhost:3000/?token=xxxxxx
```

3. Paste into your browser

---

# ✅ Setup Complete

You now have:

- WSL Ubuntu
- Node.js
- Homebrew
- OpenClaw
- OpenClaw OnBoard Dashboard
- OpenRouter Integration
- AI Model Access
- Browser Dashboard UI

You can now use OpenClaw through:

- Terminal
- Browser Dashboard
- VS Code WSL Environment

---

# 🛠 Common OpenClaw Commands

---

## Start OnBoard Dashboard

```bash
openclaw onboard
```

---

## View Live Logs

Useful for troubleshooting crashes or setup issues.

```bash
openclaw logs --follow
```

Short version:

```bash
openclaw logs -f
```

---

## Restart OpenClaw Services

```bash
openclaw restart
```

---

## Check OpenClaw Version

```bash
openclaw --version
```

---

## Update OpenClaw

```bash
openclaw update
```

---

## Check Running Services

```bash
openclaw status
```

---

## Stop OpenClaw Services

```bash
openclaw stop
```

---

## Start OpenClaw Services

```bash
openclaw start
```

---

# 🤖 Agent Management Commands

---

## Create a New Agent

```bash
openclaw agents create
```

---

## List All Agents

```bash
openclaw agents list
```

---

## Delete an Agent

```bash
openclaw agents delete
```

---

## Open Agent Configuration

```bash
openclaw agents config
```

---

# 🧩 Skills Commands

---

## Install a Skill

Example:

```bash
openclaw skills install gogcli
```

---

## List Installed Skills

```bash
openclaw skills list
```

---

## Remove a Skill

```bash
openclaw skills remove <skill-name>
```

Example:

```bash
openclaw skills remove gogcli
```

---

# 🔍 Useful Linux Commands

---

## Check Current Directory

```bash
pwd
```

---

## List Files

```bash
ls
```

---

## List Hidden Files

```bash
ls -la
```

---

## Change Folder

```bash
cd folder-name
```

---

## Go Back One Folder

```bash
cd ..
```

---

## Clear Terminal

```bash
clear
```

---

# 🚨 Troubleshooting Guide

---

## Problem: `openclaw: command not found`

Solution:

Restart Ubuntu first.

If still not working:

```bash
source ~/.bashrc
```

Then verify:

```bash
which openclaw
```

---

## Problem: Node.js Not Found

Verify installation:

```bash
node -v
npm -v
```

If missing, reinstall Node.js.

---

## Problem: Dashboard Not Opening

Try:

```bash
openclaw restart
```

Then:

```bash
openclaw onboard
```

---

## Problem: WSL Running Slowly

Try shutting down WSL completely:

Inside PowerShell:

```powershell
wsl --shutdown
```

Then reopen Ubuntu.

---

# 🎯 Recommended Next Steps

After setup, you can:

- Connect Google Calendar
- Install GOGCLI
- Create AI agents
- Use AI browser automation
- Connect APIs
- Build autonomous workflows
- Integrate OpenRouter premium models
- Experiment with local AI tooling

---

# 📚 Additional Recommended Tools

Optional tools you may install later:

- VS Code
- Docker Desktop
- GitHub CLI
- Python
- Ollama
- Cursor IDE

---

# 🚀 You're Ready

You now have a fully working OpenClaw development environment on Windows WSL.
