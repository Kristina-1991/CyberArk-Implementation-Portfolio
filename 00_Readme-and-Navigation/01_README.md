# CyberArk PAM Implementation

## Executive Summary

### Context

FinClear is a Brussels-based post-trade organization which operates in a hybrid, multi-cloud environment (HRIS/IGA/Entra/AD/IDP/SIEM). Internal audits and 2024 incidents exposed critical gaps: 
- manual onboarding (~3 days, ~20% errors)
-  shared/forgotten admin accounts
-  lack of approval controls
-  and no session recording leading to outages, fraud, and compliance findings.
  
## Objective 
Implement **CyberArk PAM** under a **Zero Trust** model to secure privileged identities (human & non-human), reduce operational risk, and demonstrate alignment with **ISO 27001, NIS2, GDPR, DORA**.

## Approach (two phases)
**Phase 0 – Data Discovery & Reconciliation (BR-00):** build a reliable privileged-account inventory and data-quality baseline (AD/HR reconciliation, owners, onboarding waves).

**Phase 1 – Controls rollout (BR-01/02/03):**
- Semi-automated onboarding with Discovery & Pending Accounts  
- Just-in-time approvals (policy/SoD, dual approval, time-boxed elevation)  
- Session recording via PSM + export to SIEM

## KPIs (targets):

- (>90%) onboarded (Wave 1)
- (<5%) orphan/shared
- (>90%) sessions recorded & auditable
- De-provisioning (<24h)

## Scope (In/Out):
**In:** privileged accounts (human & non-human), priority critical systems (servers, DB, cloud), integrations (Workday, SailPoint, Entra/AD, IDP, SIEM). 

**Out (Phase 1):** legacy out-of-connector, full IoT fleet (pilot subset).

## Key integrations.
- SCIM/REST/CSV (HRIS→IGA→Dir/PAM)
- LDAP/Graph (directory),
- SAML/OIDC : for PVWA SSO/MFA, Syslog/API (PAM→SIEM), RDP/SSH/JDBC/API to targets.

## Risk & Mitigation (highlights)
- Orphans/shared → AD↔HR reconciliation & owner assignment
- no approvals → PVWA JIT workflow
- no evidence → PSM recordings + SIEM retention.

---

## Table of Contents

- **[1. Introduction & Context](../01_Introduction-and-Context/1.%20Introduction%20and%20context.md)**
- **Phase 0 – Assessment & Preparation**
  - [2.1 Privileged Account Inventory](../02_Assessment-and-Preparation/2.1%20Privileged%20Account%20Inventory.md)
  - [2.2 Data Quality Report](../02_Assessment-and-Preparation/2.2%20Data%20Quality%20Report.md)
  - [2.3 Definition – Privileged & SoD](../02_Assessment-and-Preparation/2.3%20Definition%20–%20Privileged%20&%20SoD.md)
  - [2.4 Onboarding Plan v1](../02_Assessment-and-Preparation/2.4%20Onboarding%20Plan%20v1.md)
- **BRD & Governance**
  - [BRD v1 (Consolidated)](../03_BRD/3.1%20BRD%20v1%20(Consolidated).md)
  - [Mitigation Plan](../03_BRD/3.2%20Mitigation%20Plan.md)
  - [Stakeholders Mapping](../04_Stakeholders-and-Governance/1.4%20Stakeholders%20mapping.md) · [RACI](../04_Stakeholders-and-Governance/4.1%20RACI.md)
- **Analysis & Design**
  - [Gap Analysis](../05_Analysis-and-Design/1.5%20The%20gap%20analysis.md)
  - [Global View – Target Architecture](../05_Analysis-and-Design/5.1%20Global%20View%20–%20Target%20Architecture.md)
  - [Protocols & Integrations Matrix](../05_Analysis-and-Design/5.2%20Protocols%20&%20Integrations%20Matrix.md)
- **Requirements & Use Cases**
  - [Requirement Gathering](../06_Requirements-and-Use-Cases/1.6%20Requirement%20Gathering.md)
  - [Use Cases](../06_Requirements-and-Use-Cases/1.7%20Use%20cases_CyberArk.md)
- **Delivery**
  - [Product Backlog v1](../07_Backlog-and-Quality/7.1%20Product%20Backlog%20v1.md) · [DoR](../07_Backlog-and-Quality/7.2%20Definition%20of%20Ready%20(D oR).md) · [DoD](../07_Backlog-and-Quality/7.3%20Definition%20of%20Done%20(DoD).md)
  - [UAT Plan](../08_Testing-and-Validation/8.1%20UAT%20Plan.md) · [UAT Report](../08_Testing-and-Validation/8.2%20UAT%20Report.md)
  - [Go/No-Go Checklist](../09_Release-and-Operations/9.1%20Go-NoGo%20Checklist.md) · [Deployment & Support Scenario](../09_Release-and-Operations/9.2%20Deployment%20&%20Support%20Scenario.md) · [Hypercare Plan](../09_Release-and-Operations/9.3%20Hypercare%20Plan.md)
- **Measure & Improve**
  - [KPIs & Results](../10_Measure-and-Improve/10.1%20KPIs%20&%20Results.md) · [Lessons Learned](../10_Measure-and-Improve/10.2%20Lessons%20Learned.md)
- **Support**
  - [Change Log](./00_Change-Log.md) · [Evidence & Data Pack](../99_Support-documents/)

