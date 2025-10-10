# T{ART_ID} — {Short Test Title}

**Folder name (recommended):** `t{art_id_lower}-{short-slug}`
**MITRE ATT&CK mapping:** `{ART_ID} — {Full MITRE Title}`
**Atomic Red Team reference:** {Atomic_URL}

---

## Purpose — one line
{One-liner: why this test exists and MITRE mapping.}

---

## Description
{Paste/shorten the description you want to keep public.}

---

## Pre-reqs ✅
1. Isolated test VM (snapshot / revert point).
2. Defender / EDR onboarded and logging to Sentinel (or equivalent).
3. Local auditing enabled (Windows Audit Policy, Sysmon, etc.).
4. Atomic Red Team test guidance available: {Atomic_URL}
5. Private storage for raw logs — **do not** push raw hashes/IPs/passwords to public repo.

---

## Run steps (manual)
1. Revert VM to snapshot.
2. Read ART instructions at the link above.
3. Manually perform the selected Atomic step inside the isolated lab.
4. Note the exact time range you ran the test.
5. Collect telemetry and logs (SecurityEvent, Sysmon, EDR/MDE, network flows).
6. Document key artifacts and observations in `test-notes.md`.
7. Revert the VM when finished.

---

## What to look for / Key artifacts 🔎
- Example list: Security Event IDs, process names, files created, registry changes, network connections, group membership changes.
- Record fields: `Timestamp`, `AccountName`, `EventID`, `InitiatingProcess`, `SourceIP`, `DeviceName`.

---

## Files in this folder
- `README.md` (this file)
- `test-notes.md` — observations (sanitized)
- `detection.kql` — starter detection(s)
- `incident-summary.md` — investigation timeline + remediation
- `evidence/` — sanitized samples (.gitkeep if empty)

---

## Public vs Private guidance
- Public: README, generic KQL examples, high-level notes.
- Private: raw SecurityEvent logs, IPs, real hashes, passwords, private keys — keep offline/private.

---

## References
- Atomic Red Team: {Atomic_URL}
- Vendor & Microsoft docs (link to relevant guidance)
