# SOC Portfolio — Blue Team Labs

Welcome to my SOC Portfolio!  
This repo is where I run, analyze, and document **realistic adversary simulations, blue team playbooks, detection rules, and incident workflows** — all mapped to [MITRE ATT&CK](https://attack.mitre.org/).

---

> ⚠️ **Work in Progress:**  
> This lab is always evolving as I build, test, and refine new simulations and detections. Some folders may be incomplete as I focus on depth and quality. Check back for regular updates!

---

## 📂 Browse the Folders

- [**atomic-red-team/**](./atomic-red-team)  
  MITRE technique simulations, test evidence, detection rules, and documentation.

- [**soc-playbooks/**](./soc-playbooks)  
  Production-style SOC playbooks mapped to real-world attacks and MITRE techniques.

- [**incidents/**](./incidents)  
  Executive summaries and full reports for all incident investigations — mapped to MITRE, with timeline, evidence, and outcome.


---

## 🚀 What’s in This Repo?

- **Atomic Red Team Simulations:**  
  Benign, repeatable tests mapped to real-world MITRE techniques. Each test generates telemetry for detection and analysis.
- **SOC Playbooks:**  
  Step-by-step response guides for specific adversary behaviors — production-style, not just theory.
- **Investigation Reports:**  
  Timeline-based documentation of simulated incidents, including artifacts and analysis.
- **Detection Rules:**  
  KQL queries and detection logic for Microsoft Sentinel, Defender, and more — always tied to specific techniques and tests.

---

## 🗂️ Structure

```markdown
soc-portfolio/
│
├── atomic-red-team/           # MITRE technique folders: tests, evidence, detection KQL
│
├── soc-playbooks/             # SOC playbooks (MITRE-aligned)
│
├── incidents/                 # Investigation reports (timelines, artifacts)
│
└── README.md                  # This file
````

**Production-ready detection rules** live in my separate [`detection-engineering`](https://github.com/dushanka-p/detection-engineering) repo.

---

## ⚡ Why Atomic Red Team?

Atomic Red Team lets me run adversary behaviors with just a few PowerShell commands —
so I can focus on detection engineering, investigation, and building real blue team muscle.
It’s repeatable, safe, and perfectly mapped to MITRE — making my learning efficient and practical.

---

## 🧭 MITRE ATT&CK Mapping

Everything here — from simulations to playbooks to detections — is mapped directly to MITRE technique IDs.
This ensures my learning, workflow, and documentation are always relevant to real-world threats and modern SOCs.

---

## 🔄 My Approach

* **Pick a MITRE technique or threat scenario.**
* **Run an Atomic Red Team test to generate evidence.**
* **Investigate, triage, and document every step as if it were a real incident.**
* **Write or improve detection rules (KQL, Sigma, etc.) based on telemetry.**
* **Repeat for new techniques and keep refining old ones as my skills grow.**

---

## 🛠️ Tooling

* **Microsoft Sentinel & Defender**
* **Atomic Red Team (PowerShell)**
* **Azure VMs & isolated lab environments**
* **PowerShell scripting (growing), with Python/C on the roadmap**
* **Full MITRE ATT&CK mapping for everything**

---

## 📈 What’s Next

* Expand detection content and playbooks for more MITRE techniques
* Keep improving incident reports with new artifacts and analysis styles
* Level up my scripting (PowerShell → Python → C → Assembly) for even deeper analysis and automation
* Continue building the skills to one day rival (and outthink) the best adversaries

---

## 📫 Connect & Collaborate

* [GitHub](https://github.com/dushanka-p)
* [LinkedIn](https://www.linkedin.com/in/dushanka-p/)

---
