# 🛡️ Incident Reports

This directory contains **SOC incident reports** from my lab simulations, mapped to [MITRE ATT&CK](https://attack.mitre.org/) techniques and tactics.

Each file is a single incident investigation—covering Atomic Red Team simulations, chained attack scenarios, or any blue team event I analyze.

---

## 📅 Incident Index

| Date       | Techniques / MITRE IDs         | Description                            | Summary                                    | Full Log Link                                                                 |
|------------|-------------------------------|----------------------------------------|--------------------------------------------|-------------------------------------------------------------------------------|
| 2025-10-11 | T1078.001 (Default Accounts)  | Guest enabled, added to admin/RDP      | [Summary](2025-10-11-default-accounts.md)  | [Full Log](../atomic-red-team/03-initial-access/t1078.001-Default Accounts/soc-investigation-log.md) |
| ...        | ...                           | ...                                    | ...                                        | ...                                                                           |

*Add a new row for each incident report you create. “Full Log Link” can point to detailed investigation in the related test folder or wherever your full evidence/artifacts live.*

---

## 📄 Incident Report Template

See [`incident-report-template.md`](./incident-report-template.md) for a blank template to use when writing new reports.
