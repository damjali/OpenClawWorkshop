# 🐧 Open Claw + OpenRouter + OnBoard UI Setup Guide (Windows WSL)

This guide will help you:

- Install WSL Ubuntu
- Install Open Claw
- Install Open Claw OnBoard Dashboard UI
- Connect OpenRouter
- Use MiniMax models
- Start chatting with the model from the browser dashboard

Everything below is designed to be copy-paste friendly.

---

# 1. Install WSL (Windows Subsystem for Linux)

Open PowerShell as Administrator and run:

```powershell
wsl --install
```

If you already have WSL but want a fresh Ubuntu install:

```powershell
wsl --install -d Ubuntu
```

Restart your computer if prompted.

---

# 2. Open Ubuntu

After restarting:

1. Open Start Menu
2. Search:

```text
Ubuntu
```

3. Open it

Ubuntu will ask for:

- Username
- Password

> Password will not show while typing.

---

# 3. Update Ubuntu

Copy and paste:

```bash
sudo apt update && sudo apt upgrade -y
```

---

# 4. Install Required Dependencies

Copy everything below in ONE GO:

```bash
sudo apt install -y curl git build-essential

curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -

sudo apt install -y nodejs

node -v
npm -v
```

You should see version numbers.

---

# 5. Verify Node.js is in PATH

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

If nothing appears, restart Ubuntu and try again.

---

# 6. Install Open Claw

Copy everything:

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

---

# 7. Run Claw OnBoard Dashboard UI

Copy everything:

```bash
openclaw onboard
```
---

# 8. Get Your OpenRouter API Key

Open:

https://openrouter.ai

Then:

1. Sign in, and then go to the home page
2. Click "get API key"
3. Go to:
   - New Key
4. Create a new API key, give it a name
5. Copy the API key

---

# 14. Start OnBoard Dashboard UI

Run:

```bash
openclaw onboard
```

1. Click "Yes" for personal-by default and shared/multi-user use requires lockdown
2. "QuickStart" for Setup Mode
3. "Update Values" for Config handling
4. "OpenRouter" for Model/auth Provider
5. Paste your OpenRouter API Key
6. "Enter Model Manually" for Default Model
7. Since we will be using OpenRouter's Minimax-2.5 MOdel, paste in "openrouter/minimax/minimax-m2.5" inside "Default Model"
8. "DuckDuckGo" for Search Provider
9. "Yes" for Configure Skills Now
10. Install all missing skills dependencies
11. "Yes" for HomeBrew install Command
12. Enable all for Hooks
13. "Restart" for Gateway Service. If theres no option for Restart, then click on "Reinstall"
14. Click "Open the Web UI" for "How do you want to hatch your bot?"
15. Copy the Dashboard Link (With Token) inside the "Dashboard Ready" section and open it inside your browser

# ✅ Setup Complete

You now have:

- WSL Ubuntu
- Node.js
- Open Claw
- OnBoard Dashboard UI
- OpenRouter integration
- MiniMax model support

You can now interact with AI through:

- Terminal
- Browser dashboard UI
- VS Code WSL environment
