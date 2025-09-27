# phish-to-exfil — Public playbook (sanitized)

---

## 1. Purpose / Why we created this
- Provide a clear, shareable playbook for defenders and learners showing a realistic phishing → execution → exfiltration scenario.  
- Demonstrate telemetry patterns and investigative steps without publishing any runnable simulation code.  
- Help SOC engineers, detection authors, and interview candidates practice detection, triage and incident-response workflows using sanitized data and screenshots.

---

## 2. Safety note (important)
- The actual benign simulation scripts used to generate telemetry are stored in a **private** repository for safety.  
- This public playbook contains only: descriptions, sanitized screenshots, sample timelines, and conceptual detection guidance.  
- If you need the scripts for an isolated lab, request access to the private repo from the owner — do not run any code from public sources.

---

## 3. What this playbook contains (public)
- High-level scenario overview and attacker-emulation goals.  
- Timeline of simulated stages (sanitized timestamps).  
- Example telemetry snippets (redacted) and screenshots from Defender / Sentinel dashboards.  
- Suggested investigative questions and analyst tasks for each stage.  
-Notes on how to safely reproduce the scenario in an isolated lab (conceptual only — no code).

---

## 4. What we simulated (summary)
- Phishing delivery  
  - A convincing email sample that links to a web-hosted document or attachment (simulated, not published).  
- Execution  
  - A user-opening document action that triggers benign process activity (document app + helper script).  
- Optional persistence (lab-only)  
  - A non-destructive startup artifact to simulate post-reboot re-execution (enabled only in private lab).  
- C2 / Beaconing  
  - DNS lookup attempts to a fake domain and harmless HTTP GETs to public, benign sites to produce network telemetry.  
- Exfiltration staging  
  - Creation of a dummy “sensitive” file, archival (zip) and local staging to simulate file staging prior to exfiltration.

---

## 5. Why this is useful for defenders
- Produces representative telemetry across endpoint, DNS and network sources so detection logic can be validated.  
- Enables analysts to practice timeline-building, alert triage, and containment steps without risk.  
- Helps detection engineers tune rules, reduce false positives, and verify coverage for common phishing-to-exfil patterns.

---

## 6. How to use this playbook (public guidance)
- Read the scenario and timeline to understand expected telemetry.  
- Use the sanitized screenshots and redacted samples to craft queries and hunting rules in your environment.  
- Do **not** attempt to recreate the scenario from this public doc; request private access for the scripts and run only in an isolated lab.

---

## 7. Requesting access
- To obtain the benign simulation scripts for an isolated lab, contact the repo owner and request access to the private `simulations/phish-sim-01` repository.  
- Access will be granted only for verified lab environments and with the expectation that the scripts remain private.

---

## 8. Credits & license
- Created by: [Your Name / Team] (replace as needed).  
- License: CC BY-NC-SA (or choose an appropriate license) — public materials are for learning and non-commercial use only.

---
