# phish-to-exfil

**Goal:** repeatable, benign simulation covering phishing → stager → beacon → mock exfil on a single Azure VM. Designed for SOC detection, hunting, and IR practice (Defender + Sentinel telemetry).

**Contents**
- `01-phish-playbook.md` — scenario steps, architecture, timeline, telemetry to collect.
- `runbook-analyst.md` — analyst triage & containment runbook.
- `.env.example` — placeholders for safe config values.
- `.gitignore` — exclude secrets and large artifacts.

**Safety**
- All scripts are **benign** and read-only by default. Never include credentials or production secrets. Use `.env` locally (not pushed).

**How to use**
1. Clone repo.
2. Review `01-phish-playbook.md` and `.env.example`.
3. Deploy single Azure Windows VM (victim) per instructions in your lab docs.
4. Run the benign stager from the victim (download from `scripts/` or GitHub raw link).
5. Follow `runbook-analyst.md` to practice detection, triage and mock exfil validation.

**License & notes**
- MIT (or your preferred license). Document any third-party scripts used.

