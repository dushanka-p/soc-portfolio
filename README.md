# soc-portfolio

One-page index for my Security Operations work: simulations, detections, and honeypot investigations.  
Tools used: **Azure VMs, Microsoft Defender, Microsoft Sentinel, GitHub**.

---

## 📂 Projects (short index)
- **Simulations**
  - `soc-phish-sim` — Phish → PowerShell stager → persistence → beacon → mock exfil (Azure VM victim).  
- **Honeypot & Investigations**
  - `honeypot-investigations` — Honeypot telemetry, triage guides, IoC extraction, timeline reports.  

---

## 📂 Repository Structure (Wireframe)

```
soc-portfolio/                <- umbrella (index repo)
├─ simulations/               <- all benign SOC simulations
│  └─ soc-phish-sim/          <- phishing → stager → beacon → mock exfil (Azure VM + Defender + Sentinel)
│
└─ honeypot-investigations/   <- honeypot logs, IoC extraction, triage + investigation reports
```
---

## 🔒 Visibility & where to find artifacts
- **Public:** playbooks, detection rules, sanitized evidence, demo videos.  
- **Private:** raw PCAPs, full memory dumps, unredacted logs, tenant secrets (stored in private repos or private folder).  
- **Sanitization:** use `scripts/collect_artifacts.*` to redact hostnames, IPs, and usernames before publishing.

---

## 📋 For recruiters / reviewers (what to expect)
- Demo-ready repos with: short TL;DR, one-click run instructions (lab-only), detection queries, and sanitized timelines.  
- Live honeypot repo: real telemetry + repeatable triage steps demonstrating detection → investigation → remediation.

---

## 🛡 Safety & ethics (must-read)
- All simulations use **benign scripts only** and are to be run in isolated lab VMs.  
- Raw sensitive artifacts are never public. See each repo's `SECURITY.md` for details.

---
