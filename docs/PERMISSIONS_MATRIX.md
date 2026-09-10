# Permissions Matrix

ATLAS uses RBAC plus resource-scoped ABAC. Roles are defaults; organizations may configure narrower custom roles later.

| Capability | Founder/Org Owner | Org Admin | Fundraising Member | Viewer | Investor Member | Investor Admin | ATLAS Trust Admin |
|---|---:|---:|---:|---:|---:|---:|---:|
| Edit own company truth | ✓ | ✓ | scoped | — | — | — | support-only audited |
| Configure raise | ✓ | ✓ | scoped | — | — | — | — |
| View investor matches | ✓ | ✓ | ✓ | ✓ | — | — | support-only |
| Draft outreach | ✓ | ✓ | ✓ | — | — | — | — |
| Send approved outreach | ✓ | configurable | configurable | — | — | — | — |
| Create data room | ✓ | ✓ | scoped | — | — | — | — |
| Grant/revoke data-room access | ✓ | ✓ | configurable | — | — | — | — |
| View granted founder documents | — | — | — | — | grant only | grant only | exceptional audited support |
| Edit own investor mandate | — | — | — | — | scoped | ✓ | verified correction workflow |
| View investor deal flow | — | — | — | — | ✓ | ✓ | support-only |
| Submit interest/offer | — | — | — | — | configurable | ✓ | — |
| Modify organic scoring config | — | — | — | — | — | — | restricted dual-control |
| Override ranking result manually | — | — | — | — | — | — | prohibited; correction requires evidence event |
| View tenant audit logs | ✓ | ✓ | scoped | — | scoped | ✓ | support scope only |
| Manage billing | ✓ | configurable | — | — | — | ✓ | billing support |

## Rules

- Tenant membership alone never grants access to another tenant's resources.
- Data-room grants are resource-specific and may expire/revoke.
- Support/admin impersonation or exceptional access must be explicit, time-bounded, reason-coded, and audited.
- High-risk administrative scoring/rules changes require strong authentication and dual control where implemented.
- AI agents inherit the permissions of the invoking workflow/service account and may not elevate themselves.
- Investor verification does not grant access to confidential founder information.
