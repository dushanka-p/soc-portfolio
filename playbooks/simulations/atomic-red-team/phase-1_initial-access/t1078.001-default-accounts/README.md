# T1078.001 — Default Accounts (Guest enable + add to Admins / RDP) 🚨

**Folder:** `t1078.001-default-accounts`
**Atomic Red Team:** [https://www.atomicredteam.io/atomic-red-team/atomics/T1078.001](https://www.atomicredteam.io/atomic-red-team/atomics/T1078.001)
**ART GUID:** `99747561-ed8d-47f2-9c91-1e5fde1ed6e0`
**Platform:** Windows (Windows 11 tested) — MITRE T1078.001

> **⚠️ SAFETY:** Run **only** in an isolated test VM (snapshot/revert). Do **not** run on production or internet-exposed VMs.

---

## Purpose

Validate detection & investigation when the built-in **Guest** account is enabled, added to **Administrators** / **Remote Desktop Users**, and RDP is enabled.

---

## Prereqs

* Isolated test VM (snapshot/revert).
* Azure VM (Windows 11) onboarded to Microsoft Defender for Endpoint (MDE) and ingesting logs to Microsoft Sentinel.
* Windows auditing enabled (Account Management, Security Group Management).
* Keep raw logs/private artifacts offline — **do not** commit IPs, hashes, UPNs.

---

## Atomic steps (run elevated)

```powershell
net user guest /active:yes
net user guest Password123!
net localgroup Administrators guest /add
net localgroup "Remote Desktop Users" guest /add
reg add "HKLM\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections /t REG_DWORD /d 0 /f
reg add "HKLM\SYSTEM\CurrentControlSet\Control\Terminal Server" /v AllowTSConnections /t REG_DWORD /d 0x1 /f
```

**Inputs (defaults above):** `guest_user=guest`, `guest_password=Password123!`

---

## Cleanup (run after test)

```powershell
net user guest /active:no
net localgroup Administrators guest /delete
net localgroup "Remote Desktop Users" guest /delete

# Optional: revert RDP registry keys (uncomment to run if you want to remove RDP changes)
# reg delete "HKLM\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections /f
# reg delete "HKLM\SYSTEM\CurrentControlSet\Control\Terminal Server" /v AllowTSConnections /f
```

---

## Run steps (short)

1. Revert VM to snapshot → note **start time**.
2. Run the Atomic commands (elevated) on the isolated VM.
3. Wait for MDE telemetry to ingest into Sentinel.
4. Collect SecurityEvent / MDE / DeviceProcessEvents / Sysmon telemetry → note **end time**.
5. Record sanitized rows in `test-notes.md`. Revert snapshot.

---

## Quick detection — expected Windows Event IDs 🔎

* **4722** — User account enabled (TargetUserName: `Guest`)
* **4732** — Member added to a security-enabled local group (Administrators / Remote Desktop Users)
* **4672** — Special privileges assigned to new logon (use for correlation)

Also watch process command lines: `net user`, `net localgroup`, `reg add`, PowerShell equivalents; and Defender hunting (`DeviceProcessEvents`) for those command strings.

---

## Files in this folder

* `README.md` (this file)
* `test-notes.md` — sanitized observations (you fill after test)
* `detection.kql` — optional starter KQL (small scheduled rule)
* `incident-summary.md` — short incident template
* `evidence/` — sanitized artifacts (private)

---

## Public vs Private

* **Public:** README, generic KQL, templates.
* **Private:** raw SecurityEvent exports, MDE timelines with IPs/hashes, screenshots containing UPNs/hostnames.

---

## References

* Atomic Red Team — T1078.001 (see page for inputs & cleanup)
* Microsoft event IDs: 4722, 4732, 4672

---
