# AI-Enabled Cybersecurity Governance Framework

**Red Team / Blue Team Operational Policy for Advanced AI Models**

---

| Field | Detail |
|-------|--------|
| **Classification** | Restricted — Registered Industry Partners Only |
| **Version** | 2.0 — Enhanced Framework with IAM-as-Primary-Defence Architecture |
| **Supersedes** | v1.0 — Initial Framework Specification |
| **Date** | April 2026 |
| **Applies To** | AI frontier model deployments in cybersecurity environments |
| **Author** | Ikshudhanva P L |

---

> **V2.0 Key Additions:**
> - **Section 0** — IAM as Primary Defence: The foundational thesis now formally stated
> - **Section 4.3** — AI Model Identity Management: Non-human IAM for the AI itself
> - **Section 6.4** — Identity Compromise Response: Response when an operator identity is breached mid-session
> - **Section 10.1** — Model Version Control: Governance for AI model updates and versioning
> - **Correction:** Responsible disclosure window standardised to 90 days per Google Project Zero

---

## Table of Contents

0. [IAM as Primary Defence — The Foundational Thesis](#0-iam-as-primary-defence--the-foundational-thesis)
1. [Executive Summary](#1-executive-summary)
2. [Scope and Applicability](#2-scope-and-applicability)
3. [Rule 1 — Separation of Duties (SoD)](#3-rule-1--separation-of-duties-sod)
4. [Rule 2 — Virtual Environment Mandate](#4-rule-2--virtual-environment-mandate)
5. [Rule 3 — Test and Document Only](#5-rule-3--test-and-document-only)
6. [Rule 4 — Access Controls (RBAC + ABAC)](#6-rule-4--access-controls-rbac--abac)
7. [Rule 5 — Blue Team Remediation Protocol](#7-rule-5--blue-team-remediation-protocol)
8. [Rule 6 — Critical Escalation Protocol](#8-rule-6--critical-escalation-protocol)
9. [Rule 7 — The Common Sense Principle](#9-rule-7--the-common-sense-principle)
10. [IAM Architecture Summary & Model Version Control](#10-iam-architecture-summary--model-version-control)
11. [References](#11-references)

---

## 0. IAM as Primary Defence — The Foundational Thesis

*★ New Section in v2.0*

Traditional cybersecurity placed the firewall at the perimeter and the endpoint at the boundary. When networks were closed and users were inside, this was sufficient. It is no longer sufficient.

Zero Trust redrew the map. When the network edge dissolved — through cloud, remote work, and SaaS — the only reliable perimeter left was identity. NIST and every major security framework now agree: identity is the new perimeter.[^1]

This framework takes that principle further. It does not treat IAM as a supporting control in a broader security architecture. It treats IAM as the **primary security architecture** — the foundational layer on which every other control depends.

### 0.1 The IAM-First Argument

Every meaningful security control in this framework is, at its core, an IAM control:

| Domain | Requirement |
|--------|-------------|
| Who can access | RBAC defines roles and structural permissions. No role, no access. |
| Under what conditions | ABAC enforces contextual gates — location, device, time, MFA freshness. Condition fails, access denied. |
| For how long | Just-in-Time access limits session duration. Roles expire. Elevation ends. |
| With what verification | FIDO2 hardware keys enforce phishing-resistant MFA. Identity is cryptographically bound to hardware. |
| With what oversight | PAM session recording captures every keystroke. WORM logs make the audit trail tamper-evident. |
| With what consequence | Separation of Duties, escalation chains, and automated lockdown are all triggered by identity events — not network events. |

The AI model itself is governed by IAM. The humans governing the AI are governed by IAM. The findings produced by the AI are access-controlled by IAM. There is no layer of this framework that is not, fundamentally, an identity question.

> **Core Thesis:** In an AI-enabled cybersecurity environment, IAM is not a module. It is the architecture.

### 0.2 Why This Matters for AI Governance

AI models capable of autonomous vulnerability discovery represent a qualitatively new risk class. They are not passive tools — they generate findings that, in the wrong hands, become weapons. The question of who has access to those findings, under what conditions, for how long, and with what auditability is not a secondary question. It is the primary question.

---

## 1. Executive Summary

This framework establishes the governance, access controls, operational procedures, and escalation protocols for deploying frontier AI models — specifically those with advanced vulnerability detection and exploitation capabilities — within cybersecurity environments. Version 2.0 formally establishes IAM as the primary architectural layer.

**Three governing principles:**

- **Help, do not destroy** — AI is a force multiplier for defenders, not a weapon.
- **Human primacy** — No AI action is terminal without human verification and authorisation.
- **Transparency and accountability** — Every action is logged, reviewed, and auditable.

---

## 2. Scope and Applicability

This framework applies to any organisation granted access to a frontier AI model under a restricted cybersecurity deployment programme (e.g., Project Glasswing or equivalent). It governs the separation of Red Team and Blue Team operations, physical and logical access controls, documentation and disclosure obligations, and escalation procedures.

> **SCOPE NOTE:** This framework does **not** authorise offensive use of discovered vulnerabilities. All findings are for defensive hardening only. Any use of AI-identified exploits against systems not under authorised scope constitutes a criminal offence under applicable computer fraud laws.

---

## 3. Rule 1 — Separation of Duties (SoD)

The Red Team and Blue Team must operate as entirely independent units with no shared personnel, systems, communication channels, or findings access.

### 3.1 Rationale

Separation of Duties is a foundational IAM principle serving two purposes: preventing intentional collusion between offensive and defensive functions, and ensuring findings integrity.

### 3.2 SoD Implementation

| Domain | Requirement |
|--------|-------------|
| Personnel | No individual may hold both Red Team and Blue Team roles simultaneously or sequentially within a 12-month cooling-off period. |
| Systems | Red and Blue Team environments must be on physically separate networks with no cross-connect. Air-gapped where possible. |
| Communications | Red Team findings transmitted only via a sanitised intermediary report — never directly. |
| Management | Red and Blue Team leads must report to separate chains of command up to the CISO level. |
| Audit Logs | Log repositories must be write-once and inaccessible to both teams. Accessible only to Governance. |

### 3.3 Vulnerability Translation Officer (VTO)

- Receives full Red Team findings including exploit methodology
- Produces a sanitised remediation brief — sufficient technical detail to patch, insufficient to reproduce the attack
- Is governed by a separate confidentiality agreement with dual accountability to CISO and Governance Committee
- Has no operational role on either team

---

## 4. Rule 2 — Virtual Environment Mandate

All AI-assisted vulnerability discovery, exploit simulation, and zero-day analysis must occur exclusively within designated, isolated virtual environments.

### 4.1 Environment Specifications

| Requirement | Specification |
|-------------|---------------|
| Isolation | Network-isolated VM or sandbox. No internet access. No shared storage with host. |
| Replication | Environments must mirror production system architecture as closely as possible. |
| Snapshot Policy | Full environment snapshot taken before each AI session. Rollback capability mandatory. |
| Data | No real user data, credentials, or PII within the virtual environment. |
| Expiry | Each environment instance is destroyed and rebuilt after each documented session. |

### 4.2 Device Vulnerability Exception

- Session immediately suspended and logged
- Designated device quarantined — disconnected from all networks
- Full forensic image taken before any remediation
- Finding escalated directly to Governance Committee as Priority 1
- Replacement device from verified stock used to resume operations

### 4.3 AI Model Identity Management

*★ New in v2.0 — Non-human IAM controls for the AI model itself*

The AI model deployed under this framework is itself a non-human identity. Like any non-human identity — service accounts, API keys, automated processes — it carries security risk if not subject to full IAM lifecycle controls.

| Domain | Requirement |
|--------|-------------|
| Service Account Ownership | Every AI model instance must have a designated human owner. Ownerless AI service accounts are treated as orphaned and immediately suspended. |
| Credential Rotation | AI model API credentials and service tokens are rotated on a maximum 90-day cycle. Rotation is automated and logged. |
| Session Token Invalidation | On session suspension — whether manual, scheduled, or triggered by Red Alert — all active session tokens are immediately invalidated. |
| Orphaned Credential Revocation | All credentials associated with abandoned or interrupted sessions are automatically revoked within 15 minutes. |
| Model Instance Registry | Every AI model instance is registered in the central IAM system. Unregistered instances are blocked at the network layer. |
| Least Privilege for AI | The AI model service account is granted only the minimum permissions required for its authorised function. No write access to production systems. |

---

## 5. Rule 3 — Test and Document Only

The sole authorised purpose of AI in this framework is to identify vulnerabilities and document findings for human review. The AI has no authority to modify systems, deploy patches, or take any action outside the virtual environment.

### 5.1 Authorised AI Actions

- Scan code and system configurations for vulnerabilities
- Simulate exploit chains within the virtual environment
- Generate technical documentation of findings
- Suggest remediation approaches for Blue Team review
- Generate risk severity scoring for findings per CVSS 4.0[^2]

### 5.2 Documentation Standard

| Field | Description |
|-------|-------------|
| Finding ID | Unique identifier with timestamp and session hash |
| Severity | Critical / High / Medium / Low per CVSS 4.0 scoring |
| Affected Component | System, software version, configuration detail |
| Exploit Conditions | Prerequisites required for exploitation (Red Team report only) |
| Remediation Summary | Plain-language fix guidance (Blue Team report — no exploit detail) |
| AI Confidence | Model-assigned confidence score with reasoning |
| Human Verifier | Name, role, and timestamp of human reviewer |
| Disclosure Timeline | Target date for vendor notification and public disclosure |

---

## 6. Rule 4 — Access Controls (RBAC + ABAC)

### 6.1 Role Definitions (RBAC)

| Role | Permissions |
|------|-------------|
| Red Team Operator | AI query access within Red Team environment only. Read: Red Team findings. Write: Vulnerability Reports. |
| Blue Team Engineer | AI query access within Blue Team environment only. Read: Sanitised remediation briefs. Write: Patch documentation. |
| Vulnerability Translation Officer | Read: Full Red Team reports. Write: Sanitised Blue Team briefs. No AI query access. |
| Governance Committee Member | Read: All logs, all reports. No AI query access. Approve: Patch deployment, public disclosure. |
| CISO | Full read access. Authorise: Emergency lockdown, escalation to authorities. |
| System Administrator | Environment management only. No access to AI findings or reports. |

### 6.2 Attribute-Based Enforcement (ABAC)

| Attribute | Required Condition |
|-----------|-------------------|
| Location | Must be on registered, designated premises. GPS + network verification required. |
| Device | Must be the registered, designated device. Hardware fingerprint + TPM attestation. |
| Time Window | Access permitted only within pre-approved session schedule. No ad hoc access. |
| MFA Status | Valid FIDO2/WebAuthn multi-factor authentication within the last 15 minutes. |
| Session Duration | Maximum 4-hour continuous session. Mandatory re-authentication after. |
| Concurrent Sessions | Zero concurrent sessions permitted per user. |

### 6.3 Physical Access Controls

- Designated devices must never leave the registered premises
- Dedicated secured room with access logging (badge + biometric) for all AI sessions
- No personal devices, recording equipment, or wireless peripherals permitted in the session room
- Sessions must have a minimum of two registered personnel present (four-eyes principle)

### 6.4 Identity Compromise Response Protocol

*★ New in v2.0 — Response procedure when an operator identity is suspected compromised mid-session*

If an operator identity is suspected compromised during or within 24 hours of an active session:

1. Session suspended immediately — no further AI queries accepted regardless of session state
2. All active tokens revoked — session tokens, API keys, and temporary role elevations invalidated within 60 seconds
3. Zero Trust re-verification required — the identity cannot be reinstated until full re-verification including hardware MFA and Governance Committee approval
4. Forensic session review — the VTO reviews all AI outputs from the compromised session window for potential leakage
5. Scope assessment — Governance Committee determines whether findings from the compromised session must be treated as potentially exposed; disclosure timelines accelerated accordingly
6. Replacement operator — a different, verified operator resumes the session on a freshly rebuilt environment instance after Governance Committee clearance

> **Identity Integrity Principle:** An IAM framework that governs AI access but fails to govern the identities of the humans operating that AI is incomplete. The human operator is as much an attack surface as the AI itself. This protocol closes that gap.

---

## 7. Rule 5 — Blue Team Remediation Protocol

The Blue Team's function is exclusively remediation. They receive sanitised findings from the VTO and develop patches and hardening recommendations. All remediation is subject to human verification before deployment.

1. VTO produces sanitised remediation brief from Red Team finding
2. Blue Team AI assists in developing patch within its virtual environment
3. Patch tested against production-mirror environment — not live systems
4. Human verifier (minimum: Blue Team Lead) reviews patch efficacy and scope
5. Governance Committee approves deployment authorisation
6. Designated system administrator deploys to production under change management controls
7. Post-deployment verification: Red Team AI re-tests patched vector to confirm closure

---

## 8. Rule 6 — Critical Escalation Protocol

If any AI finding reveals a pathway to financial loss, critical infrastructure compromise, or risk to human life, an immediate red alert is triggered.

### 8.1 Red Alert Triggers

| Category | Trigger Examples |
|----------|-----------------|
| Financial System Vulnerability | Banking core systems, payment processing, financial market infrastructure |
| Human Life Risk | Hospital systems, power grid, water treatment, aviation, emergency services |
| National Security | Defence infrastructure, intelligence systems, election infrastructure |

### 8.2 Automated Response (T+0 to T+5 minutes)

- AI session immediately suspended and locked
- Virtual environment snapshot frozen and cryptographically sealed
- All network access to designated devices suspended automatically
- Incident report auto-generated and transmitted to Governance Committee
- CISO notified via out-of-band channel

### 8.3 Human Escalation Chain (T+5 to T+60 minutes)

- Governance Committee convenes — target: within 15 minutes
- CISO assesses scope and authorises notification to affected organisations
- Legal counsel engaged for regulatory notification obligations
- Law enforcement notification if criminal exploitation confirmed
- Responsible disclosure timeline accelerated — 90-day standard window suspended for life/safety risks[^3]

> **Note (v2.0 Correction):** Responsible disclosure window standardised to 90 days per Google Project Zero industry standard. Previous v1.0 referenced 135 days, which is non-standard.

> **SLA COMMITMENT:** Governance Committee must formally acknowledge Red Alert within 15 minutes. CISO must authorise an action plan within 60 minutes. Failure triggers automatic escalation to board level.

---

## 9. Rule 7 — The Common Sense Principle

Underpinning all technical controls is a foundational ethical principle: this system exists to help, not to destroy.

| Mechanism | Description |
|-----------|-------------|
| A — Ethical System Prompt | The AI model must operate under a system prompt framing its role as a defensive security tool. Reviewed quarterly. Not modifiable by operators. |
| B — Proportionality Test | Operators must document a specific, scoped objective before any AI session. Governance Committee may reject disproportionate requests. |
| C — Regular Ethics Audits | Independent ethics panel conducts quarterly reviews of findings, session logs, and escalation events. |
| D — Whistleblower Protection | Registered operators have a protected channel to report misuse to Governance Committee and regulatory authorities. |
| E — Sunset Review | Framework subject to mandatory review every 6 months as AI capabilities evolve. |

---

## 10. IAM Architecture Summary & Model Version Control

| IAM Component | Implementation |
|---------------|---------------|
| Identity Provider (IdP) | Federated, hardware-backed identity with PKI certificate per user. No shared accounts. |
| MFA | Hardware security key (FIDO2/WebAuthn) mandatory. No SMS or app-based OTP. |
| PAM | All AI sessions conducted via PAM solution with session recording and keystroke logging. |
| Just-In-Time Access | Role elevation time-limited to approved session window. Roles expire automatically. |
| Zero Trust Network | No implicit trust. Every access request verified against RBAC + ABAC policy in real time. |
| Certificate Lifecycle | Device certificates rotated every 90 days. OCSP revocation checked at session start. |
| Audit Logging | WORM logging. Logs signed with HSM key. Tamper-evident. 7-year retention minimum. |
| Privileged Session Management | Video and keystroke capture of all AI interactions. |

### 10.1 Model Version Control

*★ New in v2.0 — Governance for AI model updates and capability changes*

AI models are not static. Updates, retraining, fine-tuning, and capability expansions represent a material change in the risk profile of the deployed system. A governance framework designed for model version N may be insufficient for version N+1.

| Domain | Requirement |
|--------|-------------|
| Version Registration | Every AI model version deployed must be separately registered with the Governance Committee, including version identifier, capability summary, known limitations, and risk delta from previous version. |
| Upgrade Approval | No model version upgrade may be deployed without explicit Governance Committee approval and capability assessment comparing new version to previous against the framework's threat model. |
| Retrospective Log Association | All session logs, vulnerability reports, and findings remain permanently associated with the specific model version that generated them. |
| Capability Regression Testing | Before deploying a new model version, a structured regression test must confirm the updated model continues to operate within framework boundaries. |
| Emergency Version Rollback | Governance Committee may order immediate rollback to the previous approved version. Rollback must be executable within 30 minutes. |
| Version Sunset | Model versions more than 24 months old must be reviewed for continued fitness. Versions with known security issues must be retired on a documented timeline regardless of age. |

---

## 11. References

Citations follow the Chicago Manual of Style (17th edition).

[^1]: National Institute of Standards and Technology. "Zero Trust Architecture." NIST Special Publication 800-207, August 2020. https://doi.org/10.6028/NIST.SP.800-207.

[^2]: FIRST.org. "Common Vulnerability Scoring System v4.0: Specification Document." FIRST, November 2023. https://www.first.org/cvss/v4.0/specification-document.

[^3]: Google Project Zero. "Vulnerability Disclosure FAQ." Google, 2021. https://googleprojectzero.blogspot.com/p/vulnerability-disclosure-faq.html.

[^4]: FIDO Alliance. "FIDO2: WebAuthn & CTAP." FIDO Alliance, 2023. https://fidoalliance.org/fido2/.

[^5]: International Organization for Standardization. "ISO/IEC 27001:2022 — Information Security, Cybersecurity and Privacy Protection." ISO, 2022. https://www.iso.org/standard/27001.

[^6]: National Institute of Standards and Technology. "Cybersecurity Framework 2.0." NIST, February 2024. https://www.nist.gov/cyberframework.

[^7]: Ministry of Law and Justice, Government of India. "The Information Technology Act, 2000 (Act 21 of 2000)." Gazette of India, June 2000, as amended by the Information Technology (Amendment) Act 2008.

[^8]: Indian Computer Emergency Response Team (CERT-In). "Directions under sub-section (6) of Section 70B of the Information Technology Act, 2000." Ministry of Electronics and Information Technology, Government of India, April 2022. https://www.cert-in.org.in/Directions70B.jsp.

[^9]: European Parliament and Council of the European Union. "General Data Protection Regulation (EU) 2016/679." Official Journal of the European Union L 119, May 2016. https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32016R0679.

[^10]: European Parliament and Council of the European Union. "Directive (EU) 2022/2555 (NIS2 Directive)." Official Journal of the European Union L 333, December 2022.

---

*END OF DOCUMENT — Framework v2.0 — April 2026*  
*Author: Ikshudhanva P L*  
*AI should be something the world finds awe-inspiring, not something it fears.*
