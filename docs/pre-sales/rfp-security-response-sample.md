# Sample RFP Security Responses

**Context:** responses for the fictional RJS A/C Quote Calculator **as documented in the public showcase**. I write answers that are accurate first: state what is in place, what is not, and what is planned, with no overstated claims. Customers (and their security reviewers) trust a vendor who is precise about limits.

Status key: **Implemented** · **Partial** · **Planned** · **Not applicable**

| # | Question | Status | Response |
|---|---|---|---|
| 1 | Describe how customer data is stored. | Partial | The prototype stores records in the user's browser, scoped to that browser profile and site origin. There is no central database yet. PostgreSQL persistence is planned for shared records. |
| 2 | Is data encrypted in transit? | Planned | Production deployment will serve all traffic over TLS. The current prototype runs locally and is not a hosted service. |
| 3 | Is data encrypted at rest? | Planned | Planned with the database and cloud deployment: managed encryption at rest with customer-isolated access controls. Browser-local storage relies on the user's device protections. |
| 4 | How is user authentication handled? | Planned | The prototype has no user sign-in. Authenticated access to shared records is a planned milestone, with role-based access (operator vs administrator). |
| 5 | Is there role-based access control? | Planned | Illustrative roles include operators (intake, approval, quoting) and administrators (settings, pricing rules). Final permissions and enforcement are planned. |
| 6 | Is there an audit trail of approvals and price changes? | Planned | Approval is an explicit, separate step in the workflow today. Persistent audit logging (who, what, when) is planned with the database. |
| 7 | Does the application contain personal information? | Partial | Intake records hold contact details and service addresses. The demo uses fictional data only. Production use would require a data-retention and deletion policy before launch. |
| 8 | How are vulnerabilities managed? | Partial | Dependencies are tracked with the package manager, and the showcase readiness report recorded TypeScript checks, automated tests, and production builds. A formal scanning and patching schedule is planned before production. |
| 9 | Where will the solution be hosted? | Planned | AWS deployment is planned. Intended controls include least-privilege IAM, encrypted storage, centralized logging, and network isolation. |
| 10 | Do you have security certifications (SOC 2, ISO 27001)? | Not applicable | None at this stage. As a prototype, it has not been independently audited. |
| 11 | Backup and disaster recovery? | Planned | Will be defined with the production database: automated backups, tested restores, and stated recovery objectives. |
| 12 | Incident response? | Planned | A documented process and customer notification commitments will be in place before any production use. |

## How I use this
- Sales gets a fast, truthful answer sheet; security reviewers get no surprises.
- Anything marked Planned becomes a roadmap item with an owner, not a promise.
- Unknowns go back to engineering or security for confirmation before submission.

## Note
This sample reflects a prototype. Real RFP answers for a production product must be verified with engineering and security before submission.
