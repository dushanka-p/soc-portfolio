Here’s your **cleaned-up, up-to-date version** — rewritten to reflect your current work (Atomic Red Team simulations, Microsoft stack, Azure lab) while keeping the layout professional, recruiter-friendly, and Markdown-ready 👇

---

# 🧩 SOC Portfolio

Central index for my **Security Operations** projects — focused on **threat simulation, detection engineering, and investigation workflows** using the Microsoft Security stack.
Tools used: **Microsoft Sentinel, Defender for Endpoint, Log Analytics, Azure VMs, and GitHub.**

---

## 📂 Project Index

* **Atomic Red Team Simulations**

  * `atomic-red-team/` — MITRE-mapped tests manually executed on Azure lab VMs to generate Defender + Sentinel telemetry for SOC investigations.

* **SOC Playbooks & Detection Rules**

  * `soc-playbooks-portfolio/` — Sentinel KQL detections, incident workflows, and investigation timelines mapped to ATT&CK.

* **(Planned)** Honeypot & Live Investigations

  * `honeypot-investigations/` — Future addition for analyzing attacker telemetry and IoC extraction from live honeypot data.

---

## 🧱 Repository Structure (Wireframe)

```
soc-portfolio/                   <- main index repo
├─ atomic-red-team/              <- simulation tests (MITRE ATT&CK aligned)
│
├─ soc-playbooks-portfolio/      <- detections, playbooks, incident workflows
│
└─ honeypot-investigations/      <- (planned) honeypot telemetry + analysis reports
```

---

## 🔒 Visibility & Artifacts

* **Public:** sanitized playbooks, detection queries, evidence snippets, and demo summaries.
* **Private:** raw PCAPs, memory dumps, tenant data, and logs stored securely offline.
* **Sanitization:** all published artifacts are redacted with custom PowerShell redaction scripts (`collect_artifacts.ps1`).

---

## 📋 For Recruiters & Reviewers

* Each repo includes:

  * A **TL;DR summary** of the attack or detection.
  * **Step-by-step lab instructions** (safe, lab-only).
  * **Detection queries** and **incident timeline** evidence.
* Demonstrates proficiency in **SOC workflows**, **KQL detection logic**, and **Microsoft Defender telemetry analysis.**

---

## 🛡 Ethics & Safety

* All simulations are **benign and lab-safe**, executed in isolated Azure VMs.
* No sensitive or real-world data is exposed.
* Each sub-repo includes a dedicated `SECURITY.md` for responsible disclosure and safe testing guidelines.

---

Would you like me to include a small **“Current Focus”** section at the top (e.g., “Currently expanding Atomic Red Team detections and Sentinel KQL rules”) so it looks active to recruiters viewing your GitHub?
