# Atomic Red Team — MITRE ATT&CK Simulations

This directory contains **Atomic Red Team simulations** for a wide range of [MITRE ATT&CK](https://attack.mitre.org/) techniques.  
Each subfolder maps to a MITRE ATT&CK tactic and technique, containing benign tests, evidence, and detection rules for hands-on SOC learning.

---

## 📁 Folder Structure

```markdown
atomic-red-team/
│
├── 01-reconnaissance/         # MITRE Reconnaissance techniques
├── 02-resource-development/   # Resource Development techniques
├── 03-initial-access/         # Initial Access techniques (e.g., phishing, valid accounts)
├── docs/                      # Setup guides and extra docs
└── README.md                  # This file
```
---

## 🧩 How to Use

- Each numbered folder = MITRE tactic (aligned to ATT&CK categories).
- Inside each tactic, you'll find folders for individual techniques (e.g., `T1078.001-Default-Accounts/`).
- Each technique folder typically contains:
  - `README.md` — Simulation overview and instructions
  - `detection-rule.kql` — KQL detection logic (Microsoft Sentinel, Defender, etc.)
  - Test artifacts, logs, and notes

---

## ⚡ Why Atomic Red Team?

Atomic Red Team lets me safely simulate real-world adversary techniques in my own lab.  
This approach means I can generate telemetry, validate detection rules, and practice investigation workflows without the risk or complexity of live malware.

---

## 🧭 MITRE ATT&CK Mapping

Every simulation and folder here is mapped directly to a MITRE ATT&CK technique ID,  
making it easy to align my blue team skills with industry frameworks.

---

## 🛠️ Notes

- All tests are benign and run in a controlled, isolated lab environment.
- For setup or troubleshooting help, see the [`docs/`](./docs) folder.

---

> This repo is a work in progress — new techniques and detection rules added regularly!

---

