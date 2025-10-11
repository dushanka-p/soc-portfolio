# T1078.001 — Valid Accounts: Default Accounts

**MITRE ATT&CK Mapping:**  
- **Tactic:** Initial Access  
- **Technique:** T1078.001 — Valid Accounts: Default Accounts  
- **Link:** <a href="https://attack.mitre.org/techniques/T1078/001/" target="_blank" rel="noopener noreferrer">MITRE ATT&CK T1078.001 ↗️</a>

---

## 🧪 Atomic Red Team Simulation by Me

This test is part of my personal SOC detection engineering and investigation workflow.  
I’m manually simulating a **default account abuse scenario** on an **Azure VM**, writing the detection logic in **Microsoft Sentinel**, and confirming end-to-end incident response capability.

&nbsp;

> **Safety Notice:**  
> All testing and simulation is performed strictly within a controlled lab environment (Azure VM in a Cyber Range) that I fully manage. **Never run these techniques on production systems.**


## 📑 Quick Links

* [SOC Investigation Log & Timeline](./soc-investigation-log.md)

## 🎯 Objective

* Simulate abuse of the default `Guest` account to gain local admin + RDP access.
* Trigger a custom detection rule in Microsoft Sentinel.
* Confirm an incident is created.
* Begin triage and investigation like a real SOC analyst.

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

### ✅ Test 1 — Enable Guest + RDP + Admin

* **Technique:** T1078.001  
* **Platform:** Windows  
* **Atomic GUID:** `99747561-ed8d-47f2-9c91-1e5fde1ed6e0`

#### Manual Execution:
```cmd
net user guest /active:yes
net user guest Password123!
net localgroup Administrators guest /add
net localgroup "Remote Desktop Users" guest /add
reg add "HKLM\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections /t REG_DWORD /d 0 /f
reg add "HKLM\SYSTEM\CurrentControlSet\Control\Terminal Server" /v AllowTSConnections /t REG_DWORD /d 1 /f
````

---

### ✅ Test 2 — Activate Guest Only

* **Atomic GUID:** `aa6cb8c4-b582-4f8e-b677-37733914abda`

```cmd
net user guest /active:yes
```

---

## 🧼 Cleanup

```cmd
net user guest /active:no
net localgroup Administrators guest /delete
net localgroup "Remote Desktop Users" guest /delete
reg delete "HKLM\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections /f
reg delete "HKLM\SYSTEM\CurrentControlSet\Control\Terminal Server" /v AllowTSConnections /f
```

---

## 🧠 My Detection Workflow

1. Create a **custom Sentinel rule** using KQL to detect:

   * Guest account activation (Event ID 4722)
   * Group membership change (Event ID 4732)
   * Registry changes related to RDP
2. Run the test manually on the victim VM.
3. Monitor Sentinel → confirm **incident is created**.
4. Investigate the alert using full SOC workflow.

---

## 🕵️ SOC Investigation Log

[Jump to Detailed Log & Timeline](./soc-investigation-log.md)

* Review entities: host, user, account, IP
* Check `SecurityEvent` logs in Sentinel
* Look for Defender alerts or RDP telemetry
* Validate Guest was added to `Administrators`
* Look for any follow-up attacker actions
* Document findings

---

## 📍 Forensic Artifacts

| Artifact Type        | Expected Evidence                            |
| -------------------- | -------------------------------------------- |
| Windows Events       | 4722 (enabled account), 4732 (group change)  |
| Registry             | RDP keys modified (AllowTSConnections, etc.) |
| Network Traffic      | Port 3389 activity (if RDP attempted)        |
| Process/Command Logs | `net user`, `net localgroup`, `reg add`      |

---

## ✅ Outcome Checklist

1. [ ] Sentinel rule created
2. [ ] Atomic test run on Azure VM
3. [ ] Incident successfully triggered
4. [ ] Investigation completed
5. [ ] VM cleaned up or reverted

---

## 📚 References

* <a href="https://attack.mitre.org/techniques/T1078/001/" target="_blank" rel="noopener noreferrer">MITRE ATT&CK - T1078.001 ↗️</a>
* <a href="https://github.com/redcanaryco/atomic-red-team" target="_blank" rel="noopener noreferrer">Atomic Red Team - GitHub ↗️</a>
* <a href="https://learn.microsoft.com/en-us/azure/sentinel/" target="_blank" rel="noopener noreferrer">Microsoft Sentinel Documentation ↗️</a>
* <a href="https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/" target="_blank" rel="noopener noreferrer">Microsoft Defender for Endpoint Documentation ↗️</a>

---

## 📓 Detailed Investigation Log & Timeline

> *See [soc-investigation-log.md](./soc-investigation-log.md) in this folder for the full analyst log, timeline, artifacts, screenshots, and triage details for this test.*

---

```

Let me know if you need this for any other documentation or want a boilerplate template!
```
