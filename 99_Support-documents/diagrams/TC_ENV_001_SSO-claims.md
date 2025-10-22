# TC-ENV-001 - IDP SSO (SAML/OIDC) to PVWA - Claim Mapping

## Purpose
Document the SSO flow and the identity/authorization claims required by PVWA.

## Flow (high level)
1) User accesses PVWA → redirected to IDP (SAML/OIDC)  
2) MFA at IDP → assertion/ID token back to PVWA  
3) PVWA maps **NameID / sub**, **groups/roles**, **email**, **displayName**

## Claim / Attribute Mapping
| Claim (IDP)        | Example Value                       | Used For                     | PVWA Mapping Notes              |
|---                 |---                                  |---                           |---                              |
| `NameID` / `sub`   | `alice.admin@finclear.com`          | User identity                | Primary identifier              |
| `email`            | `alice.admin@finclear.com`          | Contact / audit              | Optional                        |
| `given_name`       | `Alice`                             | UI                           | Optional                        |
| `family_name`      | `Admin`                             | UI                           | Optional                        |
| `groups` / `roles` | `["PAM_Approver","PAM_Operator"]`   | RBAC in PVWA                 | Mapped to PVWA roles            |
| `department`       | `Security`                          | Reporting / policy           | Optional                        |

**Acceptance (demo).** This mapping is agreed and stored here.  
**Production validation.** Screenshot of successful PVWA SSO (home page) + IDP app claim configuration.

