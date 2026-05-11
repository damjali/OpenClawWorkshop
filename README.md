# 🐧 Open Claw WSL Setup Guide (Windows)

This guide will help you install and run Open Claw on Windows using WSL (Windows Subsystem for Linux) with Ubuntu.

---

# 1. Install WSL (Windows Subsystem for Linux)

Open PowerShell as Administrator and run:

```powershell
wsl --install
```

## Optional: Install a Fresh Ubuntu Instance

If you already have WSL installed but want a fresh Ubuntu installation:

```powershell
wsl --install -d Ubuntu
```

## Restart Your Computer

You may be prompted to restart your PC after installation.

---

# 2. Open Ubuntu

After restarting:

1. Open the Start Menu
2. Search for:

```text
Ubuntu
```

3. Launch it

On the first launch, Ubuntu will ask you to:

- Create a username
- Create a password

> Note: Your password will not appear while typing.

Keep the Ubuntu terminal open for the next steps.

---

# 3. Update Ubuntu Packages

Run:

```bash
sudo apt update && sudo apt upgrade -y
```

---

# 4. Install Node.js and NPM

Open Claw requires Node.js.

Run the following commands:

```bash
# Install curl if missing
sudo apt install curl -y

# Add NodeSource repository for Node.js 20
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -

# Install Node.js and NPM
sudo apt-get install -y nodejs
```

---

# 5. Verify Installation

Check that Node.js and NPM are installed correctly:

```bash
node -v
npm -v
```

You should see version numbers printed.

---

# 6. Install Open Claw

Install Open Claw globally:

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

Verify installation:

```bash
open-claw --version
```

---

# 7. Get Your Gemini API Key

Open:

https://aistudio.google.com/app/apikey

Create a new API key and copy it.

---

# 8. Create Open Claw Configuration

Create the config directory:

```bash
mkdir -p ~/.open-claw
```

Open the config file editor:

```bash
nano ~/.open-claw/config.json
```

Paste this configuration:

```json
{
  "provider": "google",
  "model": "gemini-2.0-flash-lite-preview-02-05",
  "apiKey": "YOUR_GEMINI_API_KEY",
  "options": {
    "temperature": 0.7,
    "maxTokens": 4096
  }
}
```

Replace:

```text
YOUR_GEMINI_API_KEY
```

with your actual Gemini API key.

---

# 9. Save the File

Inside nano:

- Press `Ctrl + O`
- Press Enter to save
- Press `Ctrl + X` to exit

---

# 10. Start Using Open Claw

## Initialize Open Claw in a Project

Navigate to your project folder:

```bash
cd path/to/project
```

Then run:

```bash
open-claw init
```

---

## Start a Chat Session

```bash
open-claw chat
```

---

# 11. Access Your Windows Files from Ubuntu

Inside WSL Ubuntu, your Windows drives are located under:

```bash
/mnt/
```

Example:

```bash
cd /mnt/c/Users/YourName/Documents
```

This allows you to run Open Claw directly on your Windows project files.

---

# 12. Useful WSL Commands

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

# 13. Recommended VS Code Integration (Optional)

Install:

- VS Code  
  https://code.visualstudio.com/

- WSL Extension  
  https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl

This lets you edit WSL files directly inside VS Code.

---

# 14. Troubleshooting

## Node Command Not Found

Restart Ubuntu and run:

```bash
node -v
```

again.

---

## Permission Errors with NPM

You may need:

```bash
sudo npm install -g open-claw
```

---

## Open Claw Not Found

Try:

```bash
npm list -g --depth=0
```

to verify installation.

---

# ✅ Setup Complete

You can now use Open Claw inside WSL Ubuntu on Windows.
