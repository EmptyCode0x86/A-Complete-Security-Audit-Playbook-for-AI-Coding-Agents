# Reference: Appendix A, Tiered Checklist (ASVS 5.0 and MASVS)

> OffCode Security Audit Playbook, modular edition. Used in [session 01](../sessions/session-01-kickoff.md) (choose the level) and [session 12](../sessions/session-12-final-report.md) (complete the checklist).

<!-- BEGIN ORIGINAL id=appx -->
## Appendix A: Tiered Checklist (ASVS 5.0 and MASVS)

"Secure enough" depends on the project's risk. Select the level before
completing the [section O](../sessions/session-12-final-report.md#o-production-readiness-checklist) checklist and justify the choice.

| Level | When | Minimum requirement |
| --- | --- | --- |
| ASVS L1 | Low risk, no sensitive data | Baseline controls, automated testing, OWASP Top 10 covered |
| ASVS L2 | Most applications, personal data, login | L1 + threat model, authorization tests, MFA for admins, logging and alerts, supply chain controls |
| ASVS L3 | Critical data, payments, health, a high-value target | L2 + deep manual review, external pentest, separate cryptography assessment, strong provenance |

For mobile applications, also use the OWASP MASVS control groups
(STORAGE, CRYPTO, AUTH, NETWORK, PLATFORM, CODE, RESILIENCE, PRIVACY) and
MASTG test cases. The RESILIENCE group is discretionary and only
additional protection; it does not replace other controls.

Cross-check findings and classify them with CWE identifiers. Go through
at least the CWE Top 25 weaknesses that apply to the project's
languages and technologies.

Quick check for all projects (mark PASS / FAIL /
NOT VERIFIED / NOT APPLICABLE):

-   [ ] Threat model (STRIDE) prepared and up to date
-   [ ] Authorization is checked on the server side for every object
    and field
-   [ ] MFA for admin and maintenance accounts
-   [ ] No secrets in code, history, the client, or logs
-   [ ] Dependencies locked, scanned, and an SBOM available
-   [ ] CI/CD permissions minimized and actions pinned
-   [ ] Releases and updates signed
-   [ ] Security headers and CSP (web/webview)
-   [ ] Fail-closed behavior in error conditions
-   [ ] AI agent actions require approval and are run in isolation
-   [ ] Security logs, alerts, and an incident response guide
-   [ ] Backups tested by restoring
-   [ ] Vulnerability reporting channel (SECURITY.md / security.txt)
-   [ ] Privacy processes (DPIA when needed, data-subject rights)

Sources: OWASP ASVS
(https://owasp.org/www-project-application-security-verification-standard/),
OWASP MASVS (https://mas.owasp.org/MASVS/), CWE Top 25
(https://cwe.mitre.org/top25/), OWASP Top 10:2025
(https://owasp.org/Top10/2025/).

---

[Back to top](../SECURITY_AUDIT.md#modules)

<!-- END ORIGINAL id=appx -->
