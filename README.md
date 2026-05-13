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

open-claw --version
```

---

# 7. Install Open Claw OnBoard Dashboard UI

Copy everything:

```bash
npm install -g @openclaw/onboard
```

Verify installation:

```bash
onboard --version
```

---

# 8. Get Your OpenRouter API Key

Open:

https://openrouter.ai

Then:

1. Sign in
2. Click your profile icon
3. Go to:
   - Keys
4. Create a new API key
5. Copy the API key

---

# 9. Find the MiniMax Model Name

Open:

https://openrouter.ai/models

Search for:

```text
MiniMax
```

Recommended models:

```text
minimax/minimax-m1
```

or

```text
minimax/minimax-text-01
```

---

# 10. Create Open Claw Config Folder

Copy everything:

```bash
mkdir -p ~/.open-claw
```

---

# 11. Create Configuration File

Open nano editor:

```bash
nano ~/.open-claw/config.json
```

Paste EVERYTHING below:

```json
{
  "provider": "openrouter",
  "model": "minimax/minimax-m1",
  "apiKey": "YOUR_OPENROUTER_API_KEY",
  "baseURL": "https://openrouter.ai/api/v1",
  "options": {
    "temperature": 0.7,
    "maxTokens": 4096
  }
}
```

Replace:

```text
YOUR_OPENROUTER_API_KEY
```

with your actual API key.

---

# 12. Save the File

Inside nano:

Save:

```text
Ctrl + O
```

Press Enter.

Exit:

```text
Ctrl + X
```

---

# 13. Test Open Claw in Terminal

Run:

```bash
open-claw chat
```

If successful, you can now chat with the AI in terminal.

Type something like:

```text
Hello
```

---

# 14. Start OnBoard Dashboard UI

Run:

```bash
onboard
```

You should see something like:

```text
Server running at http://localhost:3000
```

---

# 15. Open Dashboard in Browser

Open:

```text
http://localhost:3000
```

You should now see the Open Claw dashboard UI.

---

# 16. Connect Open Claw Inside OnBoard

Inside the dashboard:

1. Open Settings
2. Select:
   - Provider: OpenRouter
3. Model:
   - minimax/minimax-m1
4. Paste your API key
5. Save

You can now start chatting directly from the dashboard.

---

# 17. Access Windows Files from Ubuntu

Inside WSL:

```bash
cd /mnt/c/Users/YOUR_WINDOWS_USERNAME/Desktop
```

Example:

```bash
cd /mnt/c/Users/Adam/Desktop
```

This lets Open Claw access your Windows projects directly.

---

# 18. Create a Project Workspace

Example:

```bash
mkdir ~/openclaw-projects

cd ~/openclaw-projects
```

Initialize Open Claw:

```bash
open-claw init
```

---

# 19. Recommended VS Code Integration

Install:

VS Code:

https://code.visualstudio.com/

WSL Extension:

https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl

Then inside Ubuntu terminal:

```bash
code .
```

This opens the folder directly in VS Code using WSL.

---

# 20. Useful WSL Commands

## Shut Down WSL

Run in PowerShell:

```powershell
wsl --shutdown
```

---

## Check Installed Distros

```powershell
wsl -l -v
```

---

## Update WSL

```powershell
wsl --update
```

---

# 21. Troubleshooting

## "node: command not found"

Restart Ubuntu:

```bash
exit
```

Open Ubuntu again and run:

```bash
node -v
```

---

## "open-claw: command not found"

Run:

```bash
npm list -g --depth=0
```

If missing:

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

---

## Permission Errors

Run:

```bash
sudo npm install -g @openclaw/onboard
```

---

## Port Already in Use

Start OnBoard on another port:

```bash
onboard --port 4000
```

Then open:

```text
http://localhost:4000
```

---

# 22. Optional: Enable Faster File Performance

Instead of running projects directly from:

```text
/mnt/c/
```

store projects inside Linux home:

```bash
~/projects
```

This is usually much faster for Node.js applications.

---

# 23. Check Current RAM Usage in WSL

Run:

```bash
free -h
```

---

# 24. Completely Shut Down Open Claw + WSL

Close Ubuntu terminal and run in PowerShell:

```powershell
wsl --shutdown
```

---

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
