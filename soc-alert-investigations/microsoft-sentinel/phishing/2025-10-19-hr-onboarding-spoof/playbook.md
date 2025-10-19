# Phishing Investigation Playbook  
> For SOC simulations (TryHackMe, LetsDefend)  
> Starts from alert — no detection rule access  
> Use with: `phishing-evidence-log-template.md`, `phishing-final-report-template.md`, and `investigation-notes.md`

---

## 1. Alert Summary

1. Alert name / ID: 8818 – Inbound Email Containing Suspicious External Link
2. Date detected (YYYY-MM-DD HH:MM UTC+0): 2025-10-19 12:33 UTC+0  
3. SIEM / tool: Microsoft Sentinel  
4. Severity / priority: Medium  
5. Triage analyst: Dushanka P.  
6. Related case / ticket ID: Phishing  
7. Short summary of alert:
Inbound email with suspicious external link received by user “j[.]garcia[@]thetrydaily[.]thm”. The email, titled “Action Required: Finalize Your Onboarding Profile,” was sent from “onboarding[@]hrconnex[.]thm”. No attachments. Email encourages recipient to click a link for profile setup (hxxps://hrconnex[.]thm/onboarding/15400654060/j[.]garcia). Investigation required to determine if the link is malicious and whether endpoints accessed it.

---

## 2. Trigger Context (Alert-Only)

- **Alert trigger type:**  
  Inbound email flagged due to the presence of a suspicious external link.

- **Observable shown:**  
  - External URL: `hxxps://hrconnex[.]thm/onboarding/15400654060/j[.]garcia`  
  - No attachment  
  - Sender: `onboarding[@]hrconnex[.]thm`

- **SIEM/tool that generated alert:**  
  TryHackMe SOC Simulator (email alert system)

- **Data included in alert:**  
  - **Subject:** Action Required: Finalize Your Onboarding Profile  
  - **Sender:** `onboarding[@]hrconnex[.]thm`  
  - **Recipient:** `j[.]garcia[@]thetrydaily[.]thm`  
  - **Timestamp:** 2025-10-19 12:33:25.051 UTC  
  - **Direction:** Inbound  
  - **Attachment:** None

- **Visible telemetry:**  
  No email header snippet, click trace, or file hash provided in the alert at this stage.


---

## 3. Initial Triage

1. Check for duplicates / false positives: Screenshot: [email-search-same-subject-alertid-8818.png](evidence/screenshots/email-search-same-subject-alertid-8818.png)  
Shows both emails with the same subject line found during duplicate check.  
2. Identify target recipient(s) and role sensitivity  
3. Quick verdict: benign / suspicious / malicious — with reason  
4. Decision: escalate or continue analysis  

---

## 4. Email Header Analysis

1. Extract full headers (if visible)  
2. Check `From`, `Reply-To`, `Return-Path`  
3. Review SPF / DKIM / DMARC results  
4. Analyze `Received:` hops  
5. Identify anomalies (e.g., mismatched domain, spoofed relay)  

---

## 5. Sender & Domain Checks

1. Run WHOIS lookup — domain age, registrar  
2. Check domain reputation (VirusTotal, AbuseIPDB)  
3. Look for typosquatting or impersonation attempts  
4. Capture brand mimicry (logos, naming)  

---

## 6. URL / Link Analysis

1. Extract all links from the email (including hidden/HTML links)  
2. Expand shortened URLs  
3. Analyze in VirusTotal, URLScan  
4. If allowed, visit safely in sandbox and screenshot  
5. Record final redirect path and domain  

---

## 7. Attachment Analysis

1. Note filename and file extension  
2. Calculate and record hashes (MD5, SHA1, SHA256)  
3. Submit to VirusTotal / sandbox (if allowed)  
4. Quarantine file in `evidence/attachments/`  
5. Record sandbox verdicts or behavior  

---

## 8. Endpoint / Mailbox Triage

1. Identify device (hostname) and user  
2. Check for interaction (opened, clicked, replied)  
3. Look for suspicious processes (Office → PowerShell etc.)  
4. Review login history (unusual access, MFA prompts)  
5. Isolation or other containment actions  

---

## 9. Threat Intel & MITRE Mapping

1. Cross-reference IOCs (URLs, domains, hashes)  
2. Check for known campaigns or phishing kits  
3. Map to MITRE technique (if clear)  
4. Add summary to final report  

---

## 10. Containment & Remediation

1. Block sender, domain, or URL  
2. Remove message from mailboxes  
3. Reset credentials / enforce MFA  
4. Scan or reimage endpoint  
5. Assess additional user exposure  

---

## 11. Communication & Escalation

1. Notify affected user(s)  
2. Escalate to L2, IR, or team lead if needed  
3. Update internal ticket or case  
4. Record timeline of key actions  

---

## 12. Linked Artifacts

- [phishing-evidence-log-template.md](./phishing-evidence-log-template.md)  
- [investigation-notes.md](./investigation-notes.md)  
- [phishing-final-report-template.md](./phishing-final-report-template.md)  
- Evidence folder: `./evidence/` (headers, attachments, screenshots, logs)

---

## 13. Wrap-Up

1. Add final notes or observations  
2. Package report & evidence if needed  
3. Mark status: Closed / Monitoring / Escalated  
4. Archive case folder if completed  

---

## ✅ Forensic Artifact Summary

| What You Can Find       | Why It Matters                                                                |
|-------------------------|-------------------------------------------------------------------------------|
| Raw email (.eml/.msg)   | Full headers and content for in-depth analysis                               |
| Attachment hashes        | Used to verify malware presence via sandbox or threat intel                 |
| Link screenshots         | Captures phishing landing page or fake login prompt                         |
| Header anomalies         | Shows spoofing, mismatches, or bad relay origins                            |
| User behavior logs       | Helps confirm if user interacted with threat or was compromised             |

---

**Template v1.2 – SOC Simulation Edition**  
_Last updated: 2025-10-19_
