# 📍 Detection Rule Settings — T1078.001

## 🔖 Rule Summary

| Field                | Value                                         |
|----------------------|-----------------------------------------------|
| Rule Name            | Default Account Abuse - Guest Enabled         |
| MITRE Technique      | T1078.001 - Valid Accounts: Default Accounts  |
| Tactics              | Initial Access, Persistence, Privilege Escalation |
| Rule Type            | Scheduled Analytics Rule                      |
| Enabled              | ✅ Yes                                         |
| Severity             | Medium                                        |
| Query File           | `detection-rule.kql`                          |
| Frequency            | Every 5 minutes                               |
| Lookup Period        | Past 1 hour                                   |
| Trigger Threshold    | Greater than 0                                |
| Incident Creation    | ✅ Enabled                                     |

---

## 🧠 Entity Mappings

| Sentinel Field    | Mapped Column    |
|-------------------|------------------|
| Account           | `Account`         |
| Host              | `Computer`        |
| Timestamp         | `TimeGenerated`   |

---

## 📦 Grouping Settings

| Setting                 | Value            |
|-------------------------|------------------|
| Grouping Enabled        | ✅ Yes           |
| Group by Entities       | `Account`, `Host` |
| Reopen Closed Incidents | ❌ No             |

---

## 🏷️ Tags (optional)


T1078, AtomicRedTeam, LabTest, Detection Engineering

---

## 🧪 Notes

- Triggered successfully on lab run dated: `YYYY-MM-DD`
- Rule tested using Atomic Red Team simulation in Azure VM
- Can be tuned further with exclusions (e.g. known safe lab VMs)

---
