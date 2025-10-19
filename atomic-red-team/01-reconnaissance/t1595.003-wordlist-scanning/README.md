## MITRE Technique ID — <Technique Name>

**MITRE ATT&CK Mapping:**  
- **Tactic:** <Tactic(s)>  
- **Technique:** <MITRE Technique ID> — <Technique Name>  
- **Link:** <a href="<MITRE ATT&CK Link>" target="_blank" rel="noopener noreferrer">MITRE ATT&CK <ID> ↗️</a>

---

## 🧪 Atomic Red Team Simulation by Me

This test is part of my personal SOC detection engineering and investigation workflow.  
I’m manually simulating a **<scenario/technique description>** on an **Azure VM**, writing the detection logic in **Microsoft Sentinel**, and confirming end-to-end incident response capability.

&nbsp;

> **Safety Notice:**  
> All testing and simulation is performed strictly within a controlled lab environment (Azure VM in a Cyber Range) that I fully manage. **Never run these techniques on production systems.**

---

## 📑 Quick Links

* [SOC Investigation Log & Timeline](./soc-investigation-log.md)

---

## 🎯 Objective

* Simulate <short summary of the adversary action/abuse scenario>
* Trigger a custom detection rule in Microsoft Sentinel
* Confirm an incident is created
* Begin triage and investigation like a real SOC analyst

---

## 🧰 Tools & Lab Environment

| Tool / Platform                     | Purpose                                             |
| ----------------------------------- | --------------------------------------------------- |
| **Microsoft Sentinel**              | Detection rules + Incident management               |
| **Log Analytics Workspace**         | Ingests Windows logs from VM                        |
| **Microsoft Defender for Endpoint** | Endpoint telemetry (optional, enabled if onboarded) |
| **Azure Virtual Machine**           | Victim host for test (Windows OS)                   |
| **PowerShell / CMD**                | Manual execution of Atomic test                     |
| **Event Viewer**                    | Local log validation                                |
| **KQL (Kusto Query Language)**      | Custom query logic for Sentinel analytics rules      |

> 🧪 The test is run **manually** in a Cyber Range VM I fully control.

---

## ⚙️ Atomic Test Details

### ✅ Test 1 — <Test Name/Description>

* **Technique:** <MITRE Technique ID>
* **Platform:** <Platform>
* **Atomic GUID:** `<Atomic GUID>`

#### Manual Execution:
```cmd
<commands used in the test>
````

---

### ✅ Test 2 — <Test Name/Description>

* **Atomic GUID:** `<Atomic GUID>`

```cmd
<commands used in this test>
```

---

## 🧼 Cleanup

```cmd
<cleanup commands>
```

---

## 🧠 My Detection Workflow

1. Create a **custom Sentinel rule** using KQL to detect:

   * <Detection logic points, e.g. event IDs, artifacts>
2. Run the test manually on the victim VM.
3. Monitor Sentinel → confirm **incident is created**.
4. Investigate the alert using full SOC workflow.

---

## 🕵️ SOC Investigation Log

[Jump to Detailed Log & Timeline](./soc-investigation-log.md)

* Review entities: host, user, account, IP
* Check logs in Sentinel
* Look for Defender/EDR alerts or other telemetry
* Validate actions taken in the simulation
* Look for any follow-up attacker actions
* Document findings

---

## 📍 Forensic Artifacts

| Artifact Type        | Expected Evidence                |
| -------------------- | -------------------------------- |
| Windows Events       | <Event IDs, e.g. 4722, 4732>     |
| Registry             | <Keys/values changed>            |
| Network Traffic      | <e.g., port activity, beaconing> |
| Process/Command Logs | <cmds or scripts run>            |

---

## ✅ Outcome Checklist

1. [ ] Sentinel rule created
2. [ ] Atomic test run on Azure VM
3. [ ] Incident successfully triggered
4. [ ] Investigation completed
5. [ ] VM cleaned up or reverted

---

## 📚 References

* <a href="<MITRE ATT&CK Link>" target="_blank" rel="noopener noreferrer">MITRE ATT&CK - <ID> ↗️</a>
* <a href="https://github.com/redcanaryco/atomic-red-team" target="_blank" rel="noopener noreferrer">Atomic Red Team - GitHub ↗️</a>
* <a href="https://learn.microsoft.com/en-us/azure/sentinel/" target="_blank" rel="noopener noreferrer">Microsoft Sentinel Documentation ↗️</a>
* <a href="https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/" target="_blank" rel="noopener noreferrer">Microsoft Defender for Endpoint Documentation ↗️</a>

---

## 📓 Detailed Investigation Log & Timeline

> *See [soc-investigation-log.md](./soc-investigation-log.md) in this folder for the full analyst log, timeline, artifacts, screenshots, and triage details for this test.*

---
