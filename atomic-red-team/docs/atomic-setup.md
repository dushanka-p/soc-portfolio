## ✅ Add Atomic Red Team to Microsoft Defender Exclusion List

1. **Open PowerShell (as Administrator).**

2. **Create the Atomic folder:**
   *(Update the folder path as needed)*

   ```powershell
   New-Item -Path "<YOUR_ATOMIC_FOLDER_PATH>" -ItemType Directory -Force
   ```

   Example:

   ```powershell
   New-Item -Path "C:\AtomicRedTeam" -ItemType Directory -Force
   ```

3. **Add the folder to Defender exclusions:**

   ```powershell
   Add-MpPreference -ExclusionPath "<YOUR_ATOMIC_FOLDER_PATH>"
   ```

   Example:

   ```powershell
   Add-MpPreference -ExclusionPath "C:\AtomicRedTeam"
   ```

4. **Confirm the folder is excluded:**

   ```powershell
   (Get-MpPreference).ExclusionPath
   ```

---

## 📥 Download & Install Invoke-AtomicRedTeam

1. **Reference install guide:**
   [Install Guide on GitHub ↗️](https://github.com/redcanaryco/invoke-atomicredteam/wiki/Installing-Invoke-AtomicRedTeam)

2. **Install the module and download all atomic tests:**

   ```powershell
   IEX (IWR 'https://raw.githubusercontent.com/redcanaryco/invoke-atomicredteam/master/install-atomicredteam.ps1' -UseBasicParsing);
   Install-AtomicRedTeam -getAtomics
   ```

3. **Import the module** (run in every new session):
   *(Update the path if needed)*

   ```powershell
   Import-Module "<YOUR_ATOMIC_FOLDER_PATH>\invoke-atomicredteam\Invoke-AtomicRedTeam.psd1" -Force
   ```

   Example:

   ```powershell
   Import-Module "C:\AtomicRedTeam\invoke-atomicredteam\Invoke-AtomicRedTeam.psd1" -Force
   ```

---

## 📋 View Test Descriptions (Brief of Each Test)

* **To view all available tests for a technique (replace with your technique ID):**

  ```powershell
  Get-AtomicTechnique -Technique <TECHNIQUE_ID> | Select-Object -ExpandProperty AtomicTests | Select-Object Name, Description
  ```

  Example:

  ```powershell
  Get-AtomicTechnique -Technique T1078.001 | Select-Object -ExpandProperty AtomicTests | Select-Object Name, Description
  ```

* **Alternatively, to view all test details (including test numbers):**

  ```powershell
  Get-AtomicTechnique -Technique <TECHNIQUE_ID>
  ```

  Example:

  ```powershell
  Get-AtomicTechnique -Technique T1078.001
  ```

---

## 🧪 Check Prerequisites Before Running Tests

1. **Check prerequisites for the full technique:**

   ```powershell
   Invoke-AtomicTest <TECHNIQUE_ID> -CheckPrereqs
   ```

   Example:

   ```powershell
   Invoke-AtomicTest T1078.001 -CheckPrereqs
   ```

2. **Check prerequisites for a specific test number (replace with your test number):**

   ```powershell
   Invoke-AtomicTest <TECHNIQUE_ID> -TestNumbers <TEST_NUMBER> -CheckPrereqs
   ```

   Example:

   ```powershell
   Invoke-AtomicTest T1078.001 -TestNumbers 1 -CheckPrereqs
   ```

3. **Automatically install required dependencies:**

   ```powershell
   Invoke-AtomicTest <TECHNIQUE_ID> -TestNumbers <TEST_NUMBER> -CheckPrereqs -GetPrereqs
   ```

   Example:

   ```powershell
   Invoke-AtomicTest T1078.001 -TestNumbers 1 -CheckPrereqs -GetPrereqs
   ```

---

## 🧹 Cleanup

```powershell
Invoke-AtomicTest <TECHNIQUE_ID> -Cleanup
```

Example:

```powershell
Invoke-AtomicTest T1078.001 -Cleanup
```

---

**Usage:**

* Replace `<YOUR_ATOMIC_FOLDER_PATH>`, `<TECHNIQUE_ID>`, and `<TEST_NUMBER>` as needed for each technique/test.
