# 📁 Phishing Evidence Log

> This file logs all key evidence collected during the phishing investigation.  
> All filenames should match those saved under the `evidence/` directory.

---

## 1. Email Header

- **File saved as:** `evidence/logs/email-headers.txt`  
- **SPF:** Pass / Fail  
- **DKIM:** Pass / Fail / Missing  
- **DMARC:** Pass / Fail / None  
- **Return-Path:**  
- **Reply-To:**  
- **From (Display Name):**  
- **From (Email Address):**  
- **First Public IP in Received Chain:**  

---

## 2. Suspicious Links

| URL / Domain | Final Redirect | Status | Notes |
|--------------|----------------|--------|-------|
| `http://example.com` | `http://fake-login.com/` | Malicious | Redirects to phishing login |
| `http://short.link/xzy` | `http://cdn-fakepage.site` | Unknown | Shortened URL resolved |

- **Screenshot(s) saved in:** `evidence/screenshots/links/`

---

## 3. Attachments (if applicable)

| Filename | Extension | Hash (SHA256) | Verdict | Notes |
|----------|-----------|---------------|---------|-------|
| `invoice.docm` | .docm | `e3b0c44298fc1c149...` | Malicious | Macro-enabled payload |

- **Quarantined in:** `evidence/attachments/` (read-only)  
- **Sandbox report:** [Link or file path]  
- **Submitted to VirusTotal?** Yes / No

---

## 4. IOCs Collected

| Type      | Value                         | Source (Header / Body / Sandbox / VT) |
|-----------|-------------------------------|----------------------------------------|
| Domain    | `spoofed-login.com`           | Email body                             |
| IP        | `185.123.45.67`               | Header (Received:)                     |
| Hash      | `e3b0c44298fc1c149...`        | File attachment                        |
| URL       | `http://fake-login.com/login` | Sandbox redirect                       |

---

## 5. User & Host Info

- **Target User:** `j.doe@example.com`  
- **Device Name / Hostname:** `WIN10-FINANCE-01`  
- **Signs of Interaction:**  
  - [ ] Link clicked  
  - [ ] Attachment opened  
  - [x] Email viewed only  
- **Login Anomalies:** None / Unusual IP / MFA bypass

---

## 6. Screenshots Collected

| Description | Filename |
|-------------|----------|
| Phishing landing page | `evidence/screenshots/phish-page.png` |
| Email headers (annotated) | `evidence/screenshots/headers-review.png` |
| VirusTotal verdict | `evidence/screenshots/vt-result.png` |

---

## 7. Logs Collected

| Log Type | Path |
|----------|------|
| Email headers | `evidence/logs/email-headers.txt` |
| Sandbox report (raw) | `evidence/logs/sandbox-output.json` |
| Mail delivery trace (if visible) | `evidence/logs/mta-delivery.txt` |

---

## Notes

- All sensitive values have been sanitized before uploading to GitHub.  
- Files follow naming convention: `evidence/{type}/{artifact_or_desc}`

---

**Template v1.2 – Phishing Evidence Log (SOC Sim Edition)**  
_Last updated: 2025-10-19_

