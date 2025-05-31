# 🪟 Windows Repair Guide

This repository contains a simple and effective step-by-step guide to repair corrupted or malfunctioning Windows system files using the built-in `DISM` and `SFC` tools.

These commands help restore system stability without needing to reinstall Windows.

---

## 🧰 Tools Used

- **DISM** (Deployment Image Servicing and Management)  
  Repairs the Windows image and the component store used by the system.

- **SFC** (System File Checker)  
  Scans and restores missing or corrupted system files.

> 💡 **Note:** All commands must be run in **Command Prompt (Admin)** or **PowerShell (Admin)**.

---

## 🛠 Step-by-Step Commands

### ✅ Step 1 – Quick check for known corruption  
Performs a fast check to see if the Windows image is flagged as corrupted.

```cmd
DISM /Online /Cleanup-Image /CheckHealth
```

---

### 🔍 Step 2 – Deep scan for corruption in the Windows image  
Scans the Windows image thoroughly for any corruption.

```cmd
DISM /Online /Cleanup-Image /ScanHealth
```

---

### 🔧 Step 3 – Repair the Windows image using Windows Update or local source  
Attempts to fix any corruption found in the image using Windows Update or an installation source.

```cmd
DISM /Online /Cleanup-Image /RestoreHealth
```

> 💡 To use a local ISO or `.wim` file instead of Windows Update:  
> `DISM /Online /Cleanup-Image /RestoreHealth /Source:D:\sources\install.wim /LimitAccess`

---

### 🧼 Step 4 – Scan and repair protected system files  
Scans for and replaces corrupted or missing Windows system files.

```cmd
sfc /scannow
```

---

## ✅ Final Notes

- Run all commands **in order** for best results.
- Restart your computer after the final step if prompted.
- These steps are safe and do **not delete your personal files**.

---
