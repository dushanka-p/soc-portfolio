# SOC Investigation Playbook: Phishing Email Analysis

---

## 1. Alert Summary

- **Alert Name:**  
- **Date Detected:**  
- **Source (SIEM/Tool):**  
- **Alert Severity:**  
- **Triage Analyst:**  
- **MITRE ATT&CK Mapping:**  
- **Related Ticket/Case #:**  

---

## 2. Trigger/Detection Logic

*In most SOC lab simulations, only the detection source (SIEM/tool) is visible. Rule name and logic are usually not available.*

1. **Detection Rule Name:**  
   - Not visible in simulation
2. **Rule Logic / KQL / SPL:**  
   - Not available in lab environment
3. **Detection Source:**  
   - (e.g., Microsoft Sentinel, Splunk, Elastic)

---

## 3. Initial Triage

1. **Alert context:**  
   - What triggered the alert? (suspicious link, attachment, sender, etc.)
2. **Immediate checks:**  
   - False positive indicators?  
   - User/system involved?
3. **Relevant timeline:**  
   - When was the email received, opened, links clicked, etc.

---

## 4. Investigation Steps (Phishing Analysis)

1. **Review email content:**  
   - Check sender display name and email address  
   - Compare envelope vs. header sender  
2. **Analyze email headers:**  
   - Look for spoofing, unusual return-path, mismatched domains
3. **Extract and analyze links:**  
   - Hover over/check all URLs  
   - Use safe tools (URLscan, VirusTotal, etc.)
4. **Inspect attachments:**  
   - Quarantine and scan in a sandbox  
   - Check file type and extension
5. **Correlate user activity:**  
   - Did the recipient click any links/open attachments?
   - Any related endpoint/network alerts?
6. **Document findings:**  
   - Add screenshots, headers, IOC checks to evidence

---

## 5. Containment & Response Actions

1. **Containment:**  
   - Quarantine the email  
   - Block sender/domain if confirmed malicious  
   - Isolate affected endpoint if needed
2. **Response:**  
   - Notify user and IT/security team  
   - Force password reset if credentials involved  
   - Advise on potential impact/users to watch
3. **Recovery:**  
   - Restore systems if compromised  
   - Monitor for follow-up phishing/malware

---

## 6. Remediation & Lessons Learned

1. **Root cause identified:**  
   - (e.g., user clicked a link, gateway failed, new phishing technique)
2. **Remediation steps:**  
   - Update spam/phish filters  
   - User education/awareness  
   - Refine detection rules
3. **Preventive actions:**  
   - Improve playbooks, add detection logic, enable DMARC/SPF/DKIM

---

## 7. Documentation & Reporting

- **Evidence:** `/evidence/` (screens, logs, email headers, URLs)
- **Investigation notes:** `investigation-notes.md`
- **Final report:** `final-report.md`

---

## 8. References

- **Playbooks:** (links to phishing/IR playbooks, checklists)
- **Detection rule:** (if available, paste or link)
- **MITRE ATT&CK:**  
  - [Phishing: T1566](https://attack.mitre.org/techniques/T1566/)
  - [Credential Phishing: T1566.001](https://attack.mitre.org/techniques/T1566/001/)
- **Cheat Sheets:**  
  - [Email header analysis](https://www.cisa.gov/news-events/news/analyzing-email-headers)
  - [IOC lookup (VirusTotal)](https://www.virustotal.com/)

---

> _Template last updated: 2025-10-19_
