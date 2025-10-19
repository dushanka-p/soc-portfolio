# T1595.003 — Active Scanning: Wordlist Scanning

**MITRE ATT&CK Mapping:**  
- **Tactic:** Reconnaissance  
- **Technique:** T1595.003 — Active Scanning: Wordlist Scanning  
- **Link:** <a href="https://attack.mitre.org/techniques/T1595/003/" target="_blank" rel="noopener noreferrer">MITRE ATT&CK T1595.003 ↗️</a>

---

## 🧪 Atomic Red Team Simulation by Me

This test is part of my personal SOC detection engineering and investigation workflow.  
I’m simulating **web server and cloud storage wordlist scanning** on a controlled lab target, developing detection logic in Microsoft Sentinel/Splunk, and confirming detection/investigation procedures.

&nbsp;

> **Safety Notice:**  
> All scanning is performed strictly within a lab environment (Cyber Range VM or local sandbox). **Never run these techniques on production or unauthorized systems.**

---

## 📑 Quick Links

* [SOC Investigation Log & Timeline](./soc-investigation-log.md)

---

## 🎯 Objective

* Simulate adversary-style content and directory enumeration using wordlist scanning tools (Dirb, GoBuster, custom scripts).
* Trigger a detection rule based on high-volume 404s, scanning patterns, or known scanning tool signatures.
* Investigate the scan in SIEM and document findings using a full SOC workflow.

---

## 🧰 Tools & Lab Environment

| Tool / Platform                     | Purpose                                               |
| ----------------------------------- | ----------------------------------------------------- |
| **Dirb / DirBuster / GoBuster**     | Directory/content enumeration                          |
| **Microsoft Sentinel / Splunk**     | Detection rules, incident management                   |
| **Azure VM / Local VM**             | Victim web server (Windows, Linux, or macOS)           |
| **KQL/SPL**                         | Custom detection queries                               |
| **PowerShell / WebServerScan.ps1**  | Atomic Red Team test execution                         |
| **Wordlists (SecLists, custom)**    | Directories/filenames to scan                          |
| **Web Server Logs**                 | Artifact review, source for detection                  |

> 🧪 The test is run **manually** in a Cyber Range VM or sandbox.

---

## ⚙️ Atomic Test Details

### ✅ Test 1 — Web Server Wordlist Scan

* **Technique:** T1595.003  
* **Platform:** Windows, Linux, macOS  
* **Atomic GUID:** `89a83c3e-0b39-4c80-99f5-c2aa084098bd`

#### Manual Execution (PowerShell):
```powershell
Import-Module "PathToAtomicsFolder/T1595.003/src/WebServerScan.ps1"
Invoke-WordlistScan -Target "http://localhost" `
    -Wordlist "PathToAtomicsFolder/T1595.003/src/wordlist.txt" `
    -Timeout 5 `
    -OutputFile "$env:TMPDIR/wordlist_scan.txt"
Write-Host "Scan complete. Results saved to: $env:TMPDIR/wordlist_scan.txt"
````

*You can replace `"http://localhost"` and wordlist path with your actual test values.*

---

## 🧼 Cleanup

No system changes are made by the scan itself.
Just remove any generated output files if needed:

```powershell
Remove-Item "$env:TMPDIR/wordlist_scan.txt"
```

---

## 🧠 My Detection Workflow

1. **Create detection rules** (in Sentinel/Splunk) to identify:

   * High volume of 404/403 errors in a short window from a single source
   * Known scanning tool user-agents (`Dirb`, `GoBuster`, etc.)
   * Unusual request patterns or bursts in web server logs
2. Run the Atomic test or manual scan on the victim VM/web server.
3. Monitor SIEM for alerts/incidents.
4. Investigate the activity using a SOC analyst workflow, validate artifacts, and document findings.

---

## 🕵️ SOC Investigation Log

[Jump to Detailed Log & Timeline](./soc-investigation-log.md)

* Review source IP, host, and timestamps in server/SIEM logs.
* Check web server access/error logs for scanning patterns.
* Look for multiple 404s, directory enumeration attempts.
* Identify tool signatures (user agent, request pattern).
* Document findings and lessons learned.

---

## 📍 Forensic Artifacts

| Artifact Type        | Expected Evidence                               |
| -------------------- | ----------------------------------------------- |
| Web Server Logs      | Repeated 404/403s, enumeration requests         |
| SIEM Detection       | Alert on excessive errors or scanning patterns  |
| Network Traffic      | Multiple HTTP requests to varied endpoints      |
| Process/Command Logs | Evidence of scan tool execution on test machine |

---

## ✅ Outcome Checklist

1. [ ] Detection rule created (Sentinel/Splunk)
2. [ ] Atomic test or manual scan run on lab web server
3. [ ] Incident/alert triggered
4. [ ] Investigation completed, evidence collected
5. [ ] VM/web server cleaned up

---

## 📚 References

* <a href="https://attack.mitre.org/techniques/T1595/003/" target="_blank" rel="noopener noreferrer">MITRE ATT&CK - T1595.003 ↗️</a>
* <a href="https://github.com/redcanaryco/atomic-red-team" target="_blank" rel="noopener noreferrer">Atomic Red Team - GitHub ↗️</a>
* <a href="https://github.com/danielmiessler/SecLists" target="_blank" rel="noopener noreferrer">SecLists Wordlists ↗️</a>
* <a href="https://www.kali.org/tools/dirb/" target="_blank" rel="noopener noreferrer">Dirb (Kali Linux) ↗️</a>
* <a href="https://gobuster.github.io/" target="_blank" rel="noopener noreferrer">GoBuster Documentation ↗️</a>

---

## 📓 Detailed Investigation Log & Timeline

> *See [soc-investigation-log.md](./soc-investigation-log.md) in this folder for the full analyst log, timeline, artifacts, screenshots, and triage details for this test.*

---
