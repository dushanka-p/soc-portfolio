# 📋 Final Report – Phishing Investigation

---

## 🆔 Case Details

- **Case Title:**  
- **Case ID / Folder:** `YYYY-MM-DD-case-name`  
- **Detection Source (SIEM/Tool):**  
- **Date/Time Alert Triggered:**  
- **Analyst Name:**  
- **Severity:** Low / Medium / High  
- **Status:** Closed / Escalated / Monitoring  

---

## 🧠 Executive Summary

> 2–3 sentence overview explaining what happened, what was found, and what was done.

Example:  
A phishing email impersonating HR was delivered to a staff member. The email contained a spoofed link to a fake SharePoint login. No user interaction occurred, and the message was removed before damage. Preventive blocks have been applied.

---

## 📅 Timeline of Events (UTC)

| Time (UTC) | Action |
|------------|--------|
| 10:12 | Alert triggered in Microsoft Sentinel |
| 10:15 | Headers reviewed, spoofing confirmed |
| 10:20 | Malicious link analyzed and sandboxed |
| 10:25 | Message removed from user mailbox |
| 10:30 | Domain and IP blocked at perimeter |
| 10:35 | User notified, case closed |

---

## 🧪 Key Findings

- **Phishing Type:** Credential Harvesting / Malware Delivery / Impersonation / Other  
- **Spoofed Brand (if any):**  
- **User Clicked Link?** Yes / No  
- **Attachment Present?** Yes / No  
- **Was Payload Executed?** Yes / No / Not Applicable  
- **Device Compromised?** No (confirmed)  
- **Campaign/Pattern Detected?** If known, describe briefly.  

---

## 🔍 Indicators of Compromise (IOCs)

| Type     | Value |
|----------|-------|
| URL      | `http://spoofed.sharepoint-login-example.com` |
| Sender   | `hr@fakecompany.co` |
| Hash     | `e3b0c44298fc1c149...` |
| IP       | `185.123.45.67` |

_Add full list in evidence log if too long._

---

## 🧯 Actions Taken

- [x] Verified headers and sender
- [x] Submitted URL to sandbox
- [x] Removed message from mailbox
- [x] Blocked domain/IP
- [x] Alerted user and advised no action taken
- [x] Tagged case as resolved

---

## 📁 Linked Files

- [phishing-evidence-log.md](./phishing-evidence-log.md)  
- [playbook.md](./playbook.md)  
- [`evidence/`](./evidence/) – headers, screenshots, logs, hashes

---

## ✅ Closure Notes

- No signs of user interaction or compromise  
- IOC added to blocklist and threat repo  
- Playbook validated  
- Report saved to GitHub for future reference

---

**Template v1.2 – Final Report (Phishing | SOC Sim Edition)**  
_Last updated: 2025-10-19_

