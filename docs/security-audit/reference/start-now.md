# Reference: Start Now (section 19, original audit order)

> OffCode Security Audit Playbook, modular edition. This is the original order of work. In the modular edition the [session plan](../SECURITY_AUDIT.md#session-plan) implements this order; agents do not need to read this file.

<!-- BEGIN ORIGINAL id=start -->
## 19. Start Now

Begin in the following order:

1.  Mapping of the repository and available files.
2.  Identification of technologies, versions, and dependencies.
3.  Mapping of architecture, data flow, and trust boundaries.
4.  Formation of the threat model and attack surface.
5.  Analysis of authentication and authorization.
6.  Listing and auditing of all external interfaces.
7.  Review of databases, files, and other storage.
8.  Review of client applications and the local environment.
9.  Review of privacy and sensitive data.
10. Review of cryptography and key management, if applicable.
11. Review of the server, infrastructure, and deployment, if
    applicable.
12. Review of dependencies and the supply chain.
13. Preparation of the vulnerability report.
14. Implementation of fixes, if permitted.
15. Execution of regression tests and other verifications.
16. Final assessment of production readiness.

Include the additional stages in the items above at their natural
place: Rule 7 right at the beginning, STRIDE (1b) at item 4, API risks (2b)
at item 6, MFA (3b) at item 5, desktop and AI (6b, 6c) at item 8,
headers (7b) and cryptographic agility (8b) before item 11, cloud
and CI/CD (10b, 10c) at item 11, SBOM/SLSA and failure conditions (11b, 11c)
at item 12, automated testing (12b) before item 13, and stages
14-17 before the final assessment. Select the ASVS level according to [appendix A](appendix-a-checklist.md#appendix-a-tiered-checklist-asvs-50-and-masvs)
before item 16.

Do not skip applicable stages. However, do not mechanically apply mobile,
backend, web, or cloud controls to a project that does not have
them. Mark inapplicable areas **NOT APPLICABLE** and
justify briefly. Continue until the project has been audited as
comprehensively as possible within the available source code, configurations,
tools, and authorized testing environments.

---

<!-- END ORIGINAL id=start -->
