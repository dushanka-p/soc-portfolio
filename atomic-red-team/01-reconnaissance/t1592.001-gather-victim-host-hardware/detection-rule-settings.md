# 📍 Detection Rule Settings — T1592.001 Gather Victim Host Information: Hardware

## 🔖 Rule Summary

| Field             | Value                                                |
| ----------------- | ---------------------------------------------------- |
| Rule Name         | Host Hardware Recon via PowerShell (MITRE T1592.001) |
| MITRE Technique   | T1592.001 – Gather Victim Host Information: Hardware |
| Tactics           | Reconnaissance                                       |
| Rule Type         | Scheduled Query Rule                                 |
| Enabled           | ✅ Yes                                                |
| Severity          | Medium                                               |
| Query File        | `detection-rule.kql`                                 |
| Frequency         | Every 5 minutes                                      |
| Lookup Period     | Last 1 hour                                          |
| Trigger Threshold | 1                                                    |
| Incident Creation | ✅ Enabled                                            |

---

## 🧠 Entity Mappings

| Sentinel Field | Mapped Column |
| -------------- | ------------- |
| Account        | AccountName   |
| Host           | DeviceName    |
| Timestamp      | Timestamp     |

---

## 📦 Grouping Settings

| Setting                 | Value         |
| ----------------------- | ------------- |
| Grouping Enabled        | ✅ Yes         |
| Group by Entities       | Account, Host |
| Reopen Closed Incidents | ✅ Yes         |

---

## 🏷️ Tags (optional)

T1592, T1592.001, Reconnaissance, AtomicRedTeam, LabTest, DetectionEngineering

---

## 🧪 Notes

* Triggered successfully on lab run dated: `2025-10-19`
* Rule tested using Atomic Red Team simulation in Azure VM (`dp--art-sim--dp`)
* Can be tuned further with additional exclusions or environment-specific context

---

