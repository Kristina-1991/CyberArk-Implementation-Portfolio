# TC-ENV-004 — Backup & Retention Policy (Vault/PVWA)

**Scope.** CyberArk Vault and PVWA configuration artifacts.

**Schedule.**
- Full backup: daily at 02:00 (UTC)
- Incremental (if applicable): every 6 hours
- Test restore: monthly (pre-prod)

**Retention.**
- Backups retained for **≥ 1 year** (compliance baseline)
- Offsite copy encrypted (KMS/HSM-managed keys)

**Validation (demo).**
- This document states policy and cadence.
- Evidence in production: last backup log (success) + restore test report.
