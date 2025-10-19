# Evidence Index (Environment Readiness)

This folder contains **tool-agnostic evidence** used in lieu of proprietary screenshots.

- [TC-ENV-001_SSO-claims.md](./TC-ENV-001_SSO-claims.md) — IDP claims and PVWA mapping
- [TC-ENV-002_Port-Matrix.csv](./TC-ENV-002_Port-Matrix.csv) — required ports/protocols
- [TC-ENV-003_PAM-log-sample.log](./TC-ENV-003_PAM-log-sample.log) — sample PAM log lines  
  [TC-ENV-003_parsing-notes.txt](./TC-ENV-003_parsing-notes.txt) — parsing & dashboard notes
- [TC-ENV-004_Backup-Policy.md](./TC-ENV-004_Backup-Policy.md) — backup/retention policy
- [TC-ENV-005_Time-Check.csv](./TC-ENV-005_Time-Check.csv) — NTP skew check
- [TC-ENV-006_Delta-Example.json](./TC-ENV-006_Delta-Example.json) — IGA→PAM delta payload
- [TC-ENV-007_Connector-Matrix.csv](./TC-ENV-007_Connector-Matrix.csv) — target connectors matrix

**How this would be validated in production**
- SSO: PVWA SSO screenshot + IDP app claim config
- Ports: firewall rules change (CR) + port test results
- Logs: SIEM saved search + sample event view
- Backup: job log + restore test report
- Time: NTP status on components (skew ≤ policy)
- Delta: IGA job run log / API response
- Connectors: PVWA connector screen + test connection
