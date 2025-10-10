# Test Notes — {ART_ID} — {Short Test Title}

**Date (manual run):** {YYYY-MM-DD}
**Runed by:** {your-name}
**Environment:** {lab VM name (sanitized) / lab tag}
**Snapshot used:** {snapshot-name}

---

## Timeline
- **Start:** {YYYY-MM-DD HH:MM:SS UTC}
- **End:** {YYYY-MM-DD HH:MM:SS UTC}

---

## Observations (sanitized)
- **Security Events:**
  - EventID {#} — {short description} — `Account: USER_REMOVED`, `Time: TIMESTAMP_REMOVED`

- **Process events / Sysmon:**
  - `ParentProcess -> ChildProcess` — command line: `{cmdline with placeholders}`

- **Files created / paths:**
  - `C:\Temp\payload.docm` (example)

- **Network:**
  - Domain: `example[.]com` — IP: `EXTERNAL_IP_REMOVED`

---

## Artifacts collected (sanitized)
- `SecurityEvent_sample.json` — (sanitized extract) — stored privately in `../private_evidence/`
- `sysmon_sample.json` — (sanitized)

---

## Tuning notes / false positives
- {notes about noise, whitelisting required, etc.}

---

## Next steps
1. Create detection (detection.kql) and test.
2. Tune and validate in Sentinel.
3. Document incident summary and close test.
