
# Atomic Red Team — One-time setup & per-session tips

> **⚠️ Safety:** Run these steps **only** in isolated lab VMs. Do NOT run on production or internet-exposed systems.

---

## 🧩 One-Time Setup (Run once per machine)

**1. Install the module** (internet access required)
```powershell
# Only run if you trust PSGallery and the machine is isolated
Install-Module -Name Invoke-AtomicRedTeam -Scope CurrentUser -Repository PSGallery -Force
````

**Offline alternative:** Download the module on a safe machine and copy the module folder to:
`$env:USERPROFILE\Documents\WindowsPowerShell\Modules\Invoke-AtomicRedTeam\<version>\`

**2. Allow PowerShell scripts to run (current user)**

```powershell
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned -Force
```

**3. Create a folder for single-test outputs (idempotent)**

```powershell
$installPath = 'C:\AtomicRedTeam\SingleTests'
New-Item -Path $installPath -ItemType Directory -Force | Out-Null
```

**4. Verify module installation**

```powershell
Get-Module -ListAvailable -Name Invoke-AtomicRedTeam | Select-Object Name,Version,Path
```

---

## 💻 Per-session commands (run each time you open PowerShell)

**1. Check if module is loaded**

```powershell
Get-Module -Name Invoke-AtomicRedTeam
```

**2. If nothing returns, import the module**

```powershell
Import-Module Invoke-AtomicRedTeam
```

**3. Confirm available commands**

```powershell
Get-Command -Module Invoke-AtomicRedTeam | Select-Object Name
```

**4. (Optional) View detailed help**

```powershell
Get-Help <CommandName> -Full
```

---

## ⚙️ Example: Run a single Atomic test (manual trigger)

```powershell
# Example: find commands and run one test manually
Get-Command -Module Invoke-AtomicRedTeam
Invoke-AtomicTest -AtomicTestName 'T1059.001' -Path $installPath -ShowDetails
```

> **Note:** run tests **manually**, one at a time. Do not automate bulk test runs.

---

## 🔁 Optional: Auto-import on PowerShell startup (COMMENTED — opt-in only)

> Recommended: keep this **commented**. Only enable if you deliberately want module auto-install on lab VMs.

```powershell
# # Auto-load Atomic Red Team module at startup (OPTIONAL - uncomment to enable)
# if (-not (Get-Module -ListAvailable -Name Invoke-AtomicRedTeam)) {
#     try {
#         Install-Module -Name Invoke-AtomicRedTeam -Scope CurrentUser -Force -ErrorAction SilentlyContinue
#     } catch {}
# }
# if (-not (Get-Module -Name Invoke-AtomicRedTeam)) {
#     Import-Module Invoke-AtomicRedTeam -ErrorAction SilentlyContinue
# }
```

---

## 🧠 Safety reminders

* ✅ Run only inside your isolated Cyber Range VM (snapshot revert point).
* 🔍 Use `Get-Module -ListAvailable` to confirm installation path/version.
* 🧰 Run Atomic tests **manually**, one-by-one (your current workflow).
* 🧼 The folder creation command is idempotent — safe to rerun.
* 🔐 Consider verifying module checksum/signature or using an offline module copy.

---

```

::contentReference[oaicite:0]{index=0}
```
