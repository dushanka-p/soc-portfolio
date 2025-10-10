## ✅ Add Atomic Red Team to Microsoft Defender Exclusion List

1. Open PowerShell (as Administrator).
2. Create the Atomic folder:

   ```powershell
   New-Item -Path "C:\AtomicRedTeam" -ItemType Directory -Force
   ```
3. Add the folder to Defender exclusions:

   ```powershell
   Add-MpPreference -ExclusionPath "C:\AtomicRedTeam"
   ```
4. Confirm the folder is excluded:

   ```powershell
   (Get-MpPreference).ExclusionPath
   ```

---

## 📥 Download & Install Invoke-AtomicRedTeam

1. Reference install guide:
   [https://github.com/redcanaryco/invoke-atomicredteam/wiki/Installing-Invoke-AtomicRedTeam](https://github.com/redcanaryco/invoke-atomicredteam/wiki/Installing-Invoke-AtomicRedTeam)

2. Run the following in PowerShell to install the module and download all atomic tests:

   ```powershell
   IEX (IWR 'https://raw.githubusercontent.com/redcanaryco/invoke-atomicredteam/master/install-atomicredteam.ps1' -UseBasicParsing);
   Install-AtomicRedTeam -getAtomics
   ```

3. Import the module (must be run in every new session before using the framework):

   ```powershell
   Import-Module "C:\AtomicRedTeam\invoke-atomicredteam\Invoke-AtomicRedTeam.psd1" -Force
   ```

---

## 📋 View Test Descriptions (Brief of Each Test)

* To view all available tests for a technique along with their names and descriptions:

  ```powershell
  Get-AtomicTechnique -Technique T1078.001 | Select-Object -ExpandProperty AtomicTests | Select-Object Name, Description
  ```

* Alternatively, to view test details including test numbers:

  ```powershell
  Get-AtomicTechnique -Technique T1078.001
  ```

---

## 🧪 Check Prerequisites Before Running Tests

1. To check prerequisites for the full technique:

   ```powershell
   Invoke-AtomicTest T1078.001 -CheckPrereqs
   ```

2. To check prerequisites for a specific test number (example: Test 1):

   ```powershell
   Invoke-AtomicTest T1078.001 -TestNumbers 1 -CheckPrereqs
   ```

3. To **automatically install** required dependencies, use `-GetPrereqs`:

   ```powershell
   Invoke-AtomicTest T1078.001 -TestNumbers 1 -CheckPrereqs -GetPrereqs
   ```

---
