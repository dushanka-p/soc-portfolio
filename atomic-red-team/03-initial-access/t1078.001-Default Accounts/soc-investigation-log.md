
# 🕵️ SOC Investigation Log  
**Technique:** [TXXXX.XXX — Technique Name]  
**Test Folder:** `TXXXX.XXX-[short-name]/`  
**Date of Test:** [YYYY-MM-DD]  
**Analyst:** [Your Name or Alias]

---

## 🎯 Incident Summary

| Field                 | Value                                |
|----------------------|--------------------------------------|
| Alert Name           | [Name of Sentinel alert]             |
| MITRE ID             | [TXXXX.XXX]                          |
| Alert Source         | Microsoft Sentinel                   |
| Detection Rule Type  | [Scheduled / Custom]                 |
| Triggered By         | [e.g., Event ID, Registry, Process]  |
| Alert Severity       | [High / Medium / Low]                |
| Affected Host        | [VM Hostname or IP]                  |
| Username / Account   | [guest / attacker_sim / etc.]        |

---

## 🧠 Triage Questions

- Was the behavior expected in this lab?
- Which artifacts prove the technique worked?
- Did it cause any follow-up processes or network activity?
- Was the user elevated or used for RDP?
- Any lateral movement or signs of privilege escalation?

---

## 📂 Timeline (Key Events)

| Time (UTC)     | Event Description                                  |
|----------------|----------------------------------------------------|
| [e.g., 10:05]  | Guest account enabled via `net user`               |
| [e.g., 10:06]  | Guest added to Administrators group                |
| [e.g., 10:07]  | Registry modified to enable RDP                    |
| [e.g., 10:08]  | Sentinel alert triggered                           |

---

## 🔍 Artifacts Observed

| Artifact Type         | Evidence Found                              |
|-----------------------|---------------------------------------------|
| Security Events       | [4722, 4732]                                 |
| Command Line          | `net user`, `net localgroup`, `reg add`     |
| Registry Keys         | `HKLM\SYSTEM\...\fDenyTSConnections`         |
| Defender Logs         | [Any related MDE telemetry]                 |
| Network Logs (optional) | [RDP/3389 connection attempt]             |

---

## 🧼 Cleanup Verification

- [ ] Guest account disabled
- [ ] Removed from Admin group
- [ ] RDP registry reverted
- [ ] VM snapshot restored (if used)

---

## 🧪 Notes & Improvements

- [Detection rule improvements or logic tuning ideas]
- [EDR/Defender coverage observations]
- [Any false positive considerations]
- [Follow-up test ideas or chaining concepts]

---

## 📸 Screenshots / Evidence

- ![Screenshot](../sentinel-alert-screenshot.png)
- [Attach exported logs, if available]

---

## ✅ Outcome

✅ Incident successfully simulated and detected.  
🛠️ Detection logic verified.  
🕵️ Investigation completed.


---
