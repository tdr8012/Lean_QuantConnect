# QuantConnect Lean CLI Setup (Windows)

This guide explains how to install and configure the [QuantConnect Lean CLI](https://www.quantconnect.com/docs/v2/lean-cli/overview/what-is-the-lean-cli) for algorithmic trading locally on a Windows system using Python.

## ✅ Requirements

- Python 3.10 or later
- pip (Python package installer)
- GitHub account for repository access
- PowerShell or Command Prompt
- Internet connection

---

## 🛠 Installation Steps

### 1. Install Python

Download and install Python from [https://www.python.org/downloads/](https://www.python.org/downloads/).  
Make sure to check **"Add Python to PATH"** during installation.

### 2. Install Lean CLI

Open PowerShell and run:

```bash
py -m pip install --upgrade lean
```

> This installs the official QuantConnect Lean CLI (not Lean Theorem Prover).

---

## 🔍 Verify Installation

After installation, locate `lean.exe`:

```powershell
Get-ChildItem -Path $env:USERPROFILE -Recurse -Filter lean.exe -ErrorAction SilentlyContinue -Force | Where-Object { $_.FullName -like "*Scripts*" }
```

Example output:

```
C:\Users\your_user_name\AppData\Local\Programs\Python\Python313\Scripts\lean.exe
```

---

## 🛠 Add to PATH (if `lean` is not recognized)

1. Press `Windows + S`, type **"Environment Variables"**
2. Click **"Edit the system environment variables"**
3. Click **"Environment Variables..."**
4. Under **User variables**, select `Path` → click **Edit**
5. Click **New**, then paste your Scripts path, e.g.:

```
C:\Users\your_user_name\AppData\Local\Programs\Python\Python313\Scripts
```

6. Click **OK** and restart your terminal

---

## ✅ Run Lean CLI

```bash
lean --version
lean init
```

---

## 📂 Directory Example

If you run `lean init`, a starter Lean project will be initialized in your current directory.

---

## 💬 Troubleshooting

- Ensure `lean.exe` is found in a path that is in your system `PATH`
- Avoid installing "Lean Theorem Prover" which conflicts with CLI
- Use `py -m pip install lean` instead of `pip install lean` if `pip` alone doesn’t work
