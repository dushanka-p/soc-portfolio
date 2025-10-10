# Detection Rule Settings — DP_IR_Default_Accounts_Creation

| Setting | Value |
|----------|-------|
| **Severity** | High |
| **Tactic** | Privilege Escalation / Persistence |
| **Technique** | T1078.001 - Valid Accounts: Default Accounts |
| **Rule Type** | Scheduled |
| **Query Frequency** | 5 minutes |
| **Query Lookback** | 15 minutes |
| **Entity Mapping** | Host → HostName → WorkstationName<br>Account → Name → AccountUpn<br>Process → CommandLine → ProcessCommandLine |
| **Suppression Period** | 1 hour |
| **Playbook / Response** | Manual isolation & user investigation |
| **Version** | v1.0 |
| **Last Updated** | 2025-10-10 |
