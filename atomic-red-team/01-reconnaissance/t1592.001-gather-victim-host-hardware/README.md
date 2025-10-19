## MITRE Technique ID — T1592.001 Gather Victim Host Information: Hardware

**MITRE ATT&CK Mapping:**

* **Tactic:** Reconnaissance
* **Technique:** T1592.001 — Gather Victim Host Information: Hardware
* **Link:** <a href="https://attack.mitre.org/techniques/T1592/001/" target="_blank" rel="noopener noreferrer">MITRE ATT&CK T1592.001 ↗️</a>

---

## 🧪 Atomic Red Team Simulation by Me

This test is part of my personal SOC detection engineering and investigation workflow.
I’m manually simulating **hardware reconnaissance** activity using PowerShell to enumerate camera hardware on a Windows host.
The goal is to understand how adversaries collect host hardware details and how such activity could appear in telemetry for detection purposes.

 

> **Safety Notice:**
> All testing and simulation is performed strictly within a controlled lab environment (Azure VM in a Cyber Range) that I fully manage. **Never run these techniques on production systems.**

---

## 📑 Quick Links

* [SOC Investigation Log & Timeline](./soc-investigation-log.md)

---

## 🎯 Objective

* Simulate enumeration of victim host hardware using PowerShell
* Observe telemetry generated from the command execution
* Write a custom detection rule in Microsoft Sentinel
* Confirm incident creation and perform full SOC triage

---

## 🧰 Tools & Lab Environment

| Tool / Platform                     | Purpose                                             |
| ----------------------------------- | --------------------------------------------------- |
| **Microsoft Sentinel**              | Detection rules + Incident management               |
| **Log Analytics Workspace**         | Ingests Windows logs from VM                        |
| **Microsoft Defender for Endpoint** | Endpoint telemetry (optional, enabled if onboarded) |
| **Azure Virtual Machine**           | Victim host for test (Windows OS)                   |
| **PowerShell**                      | Manual execution of enumeration commands            |
| **Event Viewer**                    | Local validation of PowerShell logs                 |
| **KQL (Kusto Query Language)**      | Used for Sentinel detection logic                   |

> 🧪 The test is run **manually** in a Cyber Range VM I fully control.

---

## ⚙️ Atomic Test Details

### ✅ Test 1 — Enumerate PlugNPlay Camera

* **Technique:** T1592.001
* **Platform:** Windows
* **Atomic GUID:** `d430bf85-b656-40e7-b238-42db01df0183`

#### Manual Execution:

```powershell
Get-CimInstance -Query "SELECT * FROM Win32_PnPEntity WHERE (PNPClass = 'Image' OR PNPClass = 'Camera')"
```

---

## 🧼 Cleanup

No cleanup required. This command is read-only and does not modify system configuration.

---

## 🧠 My Detection Workflow

1. Create a **custom Sentinel rule** using KQL to detect PowerShell commands querying `Win32_PnPEntity` or related WMI classes.
2. Run the test manually on the victim VM.
3. Monitor Sentinel → confirm **incident creation**.
4. Investigate the alert using SOC workflow steps (entity enrichment, command line review, context validation).

---

## 🕵️ SOC Investigation Log

[Jump to Detailed Log & Timeline](./soc-investigation-log.md)

* Review PowerShell operational logs (Event ID 4104).
* Check for WMI activity targeting hardware classes.
* Validate source host and analyst account context.
* Correlate with Defender or other EDR telemetry if available.

---

## 📍 Forensic Artifacts

| Artifact Type        | Expected Evidence                                           |
| -------------------- | ----------------------------------------------------------- |
| Windows Events       | PowerShell Operational Log — Event ID 4104                  |
| Process/Command Logs | CIM/WMI queries referencing `Win32_PnPEntity` or `Camera`   |
| Security Logs        | Possible process creation (`powershell.exe` with CIM query) |
| Network Traffic      | None expected (local enumeration)                           |

---

## ✅ Outcome Checklist

1. [x] Sentinel rule created
2. [x] Atomic test run on Azure VM
3. [x] Incident successfully triggered
4. [x] Investigation completed
5. [x] VM cleaned up or reverted

---

## 📚 References

* <a href="https://attack.mitre.org/techniques/T1592/001/" target="_blank" rel="noopener noreferrer">MITRE ATT&CK - T1592.001 ↗️</a>
* <a href="https://github.com/redcanaryco/atomic-red-team" target="_blank" rel="noopener noreferrer">Atomic Red Team - GitHub ↗️</a>
* <a href="https://www.mandiant.com/resources/analyzing-dark-crystal-rat-backdoor" target="_blank" rel="noopener noreferrer">Mandiant - Dark Crystal RAT Analysis ↗️</a>
* <a href="https://learn.microsoft.com/en-us/azure/sentinel/" target="_blank" rel="noopener noreferrer">Microsoft Sentinel Documentation ↗️</a>
* <a href="https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/" target="_blank" rel="noopener noreferrer">Microsoft Defender for Endpoint Documentation ↗️</a>

---

## 📓 Detailed Investigation Log & Timeline

> *See [soc-investigation-log.md](./soc-investigation-log.md) for screenshots, KQL detection logic, Sentinel alert data, and triage notes.*

---
