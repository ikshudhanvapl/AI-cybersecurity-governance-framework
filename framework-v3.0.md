# AI-Enabled Cybersecurity Governance Framework

**Red Team / Blue Team Operational Policy for Advanced AI Models**

---

| Field | Detail |
|-------|--------|
| **Classification** | Restricted — Registered Industry Partners Only |
| **Version** | 3.0 — Comprehensive Framework with Full Threat Landscape Coverage |
| **Supersedes** | v2.0 — Enhanced Framework with IAM-as-Primary-Defence Architecture |
| **Date** | April 2026 |
| **Applies To** | AI frontier model deployments in cybersecurity environments |
| **Author** | Ikshudhanva P L |

---

> **V3.0 Additions — Known Threats Are Better Governed Than Unknown Ones**
>
> | Section | Title | Status |
> |---------|-------|--------|
> | 11 | Supply Chain Identity Risk | ★ New v3.0 |
> | 12 | Federated Identity & Cross-Org Collaboration | ★ New v3.0 |
> | 13 | Quantum Cryptography Readiness | ★ New v3.0 |
> | 14 | Insider Threat Detection | ★ New v3.0 |
> | 15 | AI Output Integrity Verification | ★ New v3.0 |
> | 16 | Regulatory & Jurisdictional Framework | ★ New v3.0 |
> | 17 | Digital Forensics & Evidence Preservation | ★ New v3.0 |
> | 18 | Continuous Compliance Monitoring | ★ New v3.0 |
> | 19 | Human Factors & Operational Resilience | ★ New v3.0 |
> | 20 | Agentic AI Controls | ★ New v3.0 |
> | 0–10 | Core Framework (v1.0 + v2.0) | ✓ Retained |

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
11. [Supply Chain Identity Risk](#11-supply-chain-identity-risk)
12. [Federated Identity & Cross-Organisation Collaboration](#12-federated-identity--cross-organisation-collaboration)
13. [Quantum Cryptography Readiness](#13-quantum-cryptography-readiness)
14. [Insider Threat Detection](#14-insider-threat-detection)
15. [AI Output Integrity Verification](#15-ai-output-integrity-verification)
16. [Regulatory & Jurisdictional Framework](#16-regulatory--jurisdictional-framework)
17. [Digital Forensics & Evidence Preservation](#17-digital-forensics--evidence-preservation)
18. [Continuous Compliance Monitoring](#18-continuous-compliance-monitoring)
19. [Human Factors & Operational Resilience](#19-human-factors--operational-resilience)
20. [Agentic AI Controls](#20-agentic-ai-controls)
21. [References](#21-references)

---

## 0. IAM as Primary Defence — The Foundational Thesis

*Established in v2.0 — foundational to all subsequent sections*

Traditional cybersecurity placed the firewall at the perimeter. Zero Trust redrew the map. This framework takes that principle further — treating IAM not as a supporting control but as the **primary security architecture**.

| Domain | Requirement |
|--------|-------------|
| Who can access | RBAC defines roles and structural permissions. No role, no access. |
| Under what conditions | ABAC enforces contextual gates — location, device, time, MFA freshness. |
| For how long | Just-in-Time access limits session duration. Roles expire. Elevation ends. |
| With what verification | FIDO2 hardware keys enforce phishing-resistant MFA. Identity is cryptographically hardware-bound.[^1] |
| With what oversight | PAM session recording captures every keystroke. WORM logs make the audit trail tamper-evident. |
| With what consequence | Separation of Duties, escalation chains, and automated lockdown are all triggered by identity events. |

> **Core Thesis:** IAM is not a module. It is the architecture. Every section of this framework is, at its core, an identity question.

---

## 1. Executive Summary

This framework establishes governance, access controls, operational procedures, and escalation protocols for deploying frontier AI models with advanced vulnerability detection and exploitation capabilities within cybersecurity environments.

Version 3.0 extends the framework to address the full known threat landscape — including supply chain risk, insider threats, quantum cryptography transition, agentic AI, and the human factors that technical controls alone cannot address. The governing philosophy of v3.0: **known threats are better governed than unknown ones.**

- **Help, do not destroy** — AI is a force multiplier for defenders, not a weapon.
- **Human primacy** — No AI action is terminal without human verification and authorisation.
- **Transparency and accountability** — Every action is logged, reviewed, and auditable.
- **Complete threat coverage** — Govern what you know before it becomes what you didn't.

---

## 2. Scope and Applicability

This framework applies to any organisation granted access to a frontier AI model under a restricted cybersecurity deployment programme (e.g., Project Glasswing or equivalent). It governs the separation of Red Team and Blue Team operations, physical and logical access controls, documentation and disclosure obligations, escalation procedures, and in v3.0, the extended threat surface including supply chain, insider threats, and agentic AI operations.

> **SCOPE NOTE:** This framework does **not** authorise offensive use of discovered vulnerabilities. All findings are for defensive hardening only. Any use of AI-identified exploits against systems not under authorised scope constitutes a criminal offence under applicable computer fraud laws.

---

## 3. Rule 1 — Separation of Duties (SoD)

The Red Team and Blue Team must operate as entirely independent units with no shared personnel, systems, communication channels, or findings access.

### 3.1 Rationale

Separation of Duties is a foundational IAM principle serving two purposes: preventing intentional collusion between offensive and defensive functions, and ensuring findings integrity — a Blue Team that knows the exact exploit methodology may patch too narrowly, creating false security.

### 3.2 SoD Implementation

| Domain | Requirement |
|--------|-------------|
| Personnel | No individual may hold both Red Team and Blue Team roles simultaneously or sequentially within a 12-month cooling-off period. |
| Systems | Red and Blue Team environments must be on physically separate networks with no cross-connect. Air-gapped where possible. |
| Communications | Red Team findings transmitted only via sanitised intermediary report — never directly. |
| Management | Red and Blue Team leads must report to separate chains of command up to CISO level. |
| Audit Logs | Log repositories must be write-once and inaccessible to both teams. Accessible only to Governance. |

### 3.3 Vulnerability Translation Officer (VTO)

- Receives full Red Team findings including exploit methodology
- Produces sanitised remediation brief — sufficient to patch, insufficient to reproduce the attack
- Governed by separate confidentiality agreement with dual accountability to CISO and Governance Committee
- Has no operational role on either team

---

## 4. Rule 2 — Virtual Environment Mandate

All AI-assisted vulnerability discovery, exploit simulation, and zero-day analysis must occur exclusively within designated, isolated virtual environments. No findings or payloads may touch production systems at any stage.

### 4.1 Environment Specifications

| Requirement | Specification |
|-------------|---------------|
| Isolation | Network-isolated VM or sandbox. No internet access. No shared storage with host. |
| Replication | Environments must mirror production system architecture as closely as possible. |
| Snapshot Policy | Full environment snapshot before each AI session. Rollback capability mandatory. |
| Data | No real user data, credentials, or PII within the virtual environment. |
| Expiry | Each environment instance destroyed and rebuilt after each documented session. |

### 4.2 Device Vulnerability Exception

- Session immediately suspended and logged
- Designated device quarantined — disconnected from all networks
- Full forensic image taken before any remediation
- Finding escalated directly to Governance Committee as Priority 1
- Replacement device from verified stock used to resume operations

### 4.3 AI Model Identity Management

*Added in v2.0 — Non-human IAM controls for the AI model itself*

| Domain | Requirement |
|--------|-------------|
| Service Account Ownership | Every AI model instance has a designated human owner. Ownerless AI service accounts treated as orphaned and immediately suspended. |
| Credential Rotation | AI model API credentials and service tokens rotated on maximum 90-day cycle. Automated and logged. |
| Session Token Invalidation | On session suspension, all active session tokens invalidated immediately. |
| Orphaned Credential Revocation | All credentials associated with abandoned sessions automatically revoked within 15 minutes. |
| Model Instance Registry | Every AI model instance registered in central IAM system. Unregistered instances blocked at network layer. |
| Least Privilege for AI | AI model service account granted only minimum permissions for its authorised function. No production write access. |

---

## 5. Rule 3 — Test and Document Only

The sole authorised purpose of AI in this framework is to identify vulnerabilities and document findings for human review.

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
| Blue Team Engineer | AI query access within Blue Team environment only. Read: Sanitised briefs. Write: Patch documentation. |
| Vulnerability Translation Officer | Read: Full Red Team reports. Write: Sanitised Blue Team briefs. No AI query access. |
| Governance Committee Member | Read: All logs and reports. No AI query access. Approve: Patch deployment, public disclosure. |
| CISO | Full read access. Authorise: Emergency lockdown, escalation to authorities. |
| System Administrator | Environment management only. No access to AI findings or reports. |

### 6.2 Attribute-Based Enforcement (ABAC)

| Attribute | Required Condition |
|-----------|-------------------|
| Location | Must be on registered, designated premises. GPS + network verification required. |
| Device | Must be the registered, designated device. Hardware fingerprint + TPM attestation. |
| Time Window | Access permitted only within pre-approved session schedule. No ad hoc access. |
| MFA Status | Valid multi-factor authentication within the last 15 minutes. |
| Session Duration | Maximum 4-hour continuous session. Mandatory re-authentication after. |
| Concurrent Sessions | Zero concurrent sessions permitted per user. |

### 6.3 Physical Access Controls

- Designated devices must never leave the registered premises
- Dedicated secured room with access logging (badge + biometric) for all AI sessions
- No personal devices, recording equipment, or wireless peripherals permitted in the session room
- Sessions must have a minimum of two registered personnel present (four-eyes principle)

### 6.4 Identity Compromise Response Protocol

*Added in v2.0*

If an operator identity is suspected compromised during or within 24 hours of an active session:

1. Session suspended immediately — no further AI queries accepted
2. All active tokens revoked within 60 seconds
3. Zero Trust re-verification required before any reinstatement
4. Forensic session review by VTO for potential leakage
5. Governance Committee scope assessment — disclosure timelines accelerated if needed
6. Replacement operator on freshly rebuilt environment after Governance clearance

---

## 7. Rule 5 — Blue Team Remediation Protocol

1. VTO produces sanitised remediation brief from Red Team finding
2. Blue Team AI assists in developing patch within its virtual environment
3. Patch tested against production-mirror environment — not live systems
4. Human verifier (minimum: Blue Team Lead) reviews patch efficacy and scope
5. Governance Committee approves deployment authorisation
6. Designated system administrator deploys to production under change management controls
7. Post-deployment verification: Red Team AI re-tests patched vector to confirm closure

---

## 8. Rule 6 — Critical Escalation Protocol

### 8.1 Red Alert Triggers

| Category | Trigger Examples |
|----------|-----------------|
| Financial System Vulnerability | Banking core systems, payment processing, market infrastructure |
| Human Life Risk | Hospitals, power grid, water treatment, aviation, emergency services |
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

> **SLA COMMITMENT:** Governance Committee must acknowledge Red Alert within 15 minutes. CISO must authorise action plan within 60 minutes. Failure triggers automatic board-level escalation.

---

## 9. Rule 7 — The Common Sense Principle

| Mechanism | Description |
|-----------|-------------|
| A — Ethical System Prompt | The AI model must operate under a system prompt framing its role as a defensive security tool. Reviewed quarterly. Not modifiable by operators. |
| B — Proportionality Test | Operators must document a specific scoped objective before any AI session. Governance Committee may reject disproportionate requests. |
| C — Ethics Audits | Independent ethics panel conducts quarterly reviews of findings, session logs, and escalation events. |
| D — Whistleblower Protection | Registered operators have a protected channel to report misuse directly to Governance Committee and regulatory authorities. |
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

*Added in v2.0*

| Domain | Requirement |
|--------|-------------|
| Version Registration | Every AI model version separately registered with Governance Committee including capability summary and risk delta. |
| Upgrade Approval | No version upgrade without explicit Governance Committee approval and capability assessment. |
| Retrospective Log Association | All logs permanently associated with specific model version that generated them. |
| Capability Regression Testing | Structured regression test confirms updated model operates within framework boundaries before deployment. |
| Emergency Version Rollback | Governance Committee may order immediate rollback. Executable within 30 minutes. |
| Version Sunset | Model versions over 24 months old reviewed for fitness. Known security issues trigger mandatory retirement. |

---

## 11. Supply Chain Identity Risk

*★ New in v3.0*

The SolarWinds compromise demonstrated that the most sophisticated internal controls can be rendered irrelevant by a compromised upstream vendor.[^4] An AI governance framework that governs internal operators but ignores the supply chain has a fundamental blind spot.

### 11.1 Supply Chain Threat Vectors

| Vector | Risk |
|--------|------|
| AI Model Vendor | The organisation that trains and delivers the frontier AI model. If model weights are tampered with at source, all downstream controls are compromised. |
| Cloud Infrastructure Provider | The platform hosting the virtual environments. A compromised cloud provider has access below the governance layer. |
| Security Tool Vendors | PAM, SIEM, and audit logging vendors. A compromised logging vendor could silently suppress audit evidence. |
| Managed Service Providers | Third parties with privileged access to maintain or monitor components of the framework environment. |
| Software Dependencies | Libraries, packages, and tools used within the virtual environment. Open-source dependency compromise (e.g., XZ Utils[^5]) can create covert access. |

### 11.2 Supply Chain IAM Controls

| Domain | Requirement |
|--------|-------------|
| Vendor Identity Verification | Every vendor with system access governed by the same RBAC/ABAC framework as internal operators. No vendor receives implicit trust. |
| Vendor Session Recording | All vendor remote access sessions recorded via PAM. No unrecorded vendor access permitted under any circumstance. |
| AI Model Provenance Verification | Cryptographic signature of AI model weights verified before each deployment. Signature chain traced to the AI vendor's root certificate. |
| Supply Chain SoD | No vendor may have access to both the AI model and the audit logs. Vendor access is siloed to its specific function. |
| Third Party Security Assessment | Vendors undergo security posture assessment before partnership and annually thereafter. |
| Vendor Offboarding Protocol | When a vendor relationship ends, all vendor identities are revoked immediately — treated as departing employee credentials under the JML leaver workflow. |
| Software Bill of Materials (SBOM) | A complete inventory of all software dependencies within the virtual environment is maintained and assessed for known vulnerabilities before each session. |

### 11.3 Model Weight Integrity Protocol

- Model weights delivered via authenticated, encrypted channel from vendor
- Cryptographic hash of weights computed and registered with Governance Committee on delivery
- Hash verified against vendor-signed manifest before every deployment
- Any hash mismatch triggers immediate quarantine and vendor notification
- Independent third party verifies model behaviour against baseline after each deployment

---

## 12. Federated Identity & Cross-Organisation Collaboration

*★ New in v3.0*

Cybersecurity rarely happens in isolation. Vulnerability findings may require coordination with national CERTs, sector-specific ISACs, international partners, or the affected vendor. Each of these interactions creates an identity federation challenge.

### 12.1 Federation Standards

| Standard | Use Case |
|----------|----------|
| SAML 2.0 | Enterprise-to-enterprise identity federation for structured, long-term partner relationships. |
| OpenID Connect (OIDC) | Modern token-based federation for API-level integration with external partner systems. |
| FIDO2 Cross-Domain | Hardware key authentication that works across organisational boundaries without password sharing. |
| PKI Cross-Certification | Certificate authority cross-certification for high-assurance partner identity verification. |

### 12.2 External Identity Controls

| Domain | Requirement |
|--------|-------------|
| Guest Operator Access | External parties receive time-limited, scope-restricted access only. Guest identities expire automatically at session end. No persistent external accounts. |
| External SoD | No external party may hold the VTO role. Translation of findings for external sharing performed exclusively by internal VTO. |
| Federated ABAC | External operator access subject to the same ABAC attribute checks as internal operators. |
| External Audit Trail | All external access logged separately with clear attribution to the external organisation and specific individual. |
| Data Minimisation for Sharing | Findings shared externally are further sanitised beyond the VTO Blue Team brief. Minimum information principle: share only what the external party needs to act. |

### 12.3 Cross-Organisation Disclosure Protocol

1. Governance Committee approves external disclosure — no operator may share findings externally without approval
2. VTO produces external-grade sanitised brief — additional layer of sanitisation beyond Blue Team brief
3. Secure communication channel established — encrypted, authenticated channel to receiving organisation
4. Receiving organisation identity verified before sharing proceeds
5. Sharing logged with content hash — what was shared, to whom, when, and by whom
6. Follow-up verification — receiving organisation confirms receipt and confirms finding is under remediation

---

## 13. Quantum Cryptography Readiness

*★ New in v3.0*

This framework currently relies on classical cryptographic algorithms theoretically vulnerable to sufficiently powerful quantum computers. NIST finalised its first post-quantum cryptography standards in 2024 (FIPS 203, 204, 205).[^6]

The threat of **harvest now, decrypt later** attacks means adversaries may be collecting encrypted session data today with the intention of decrypting it when quantum capability matures.[^7] For a framework with 7-year audit log retention, this is a present risk to historical records.

### 13.1 Cryptographic Inventory

| Component | Current State & Migration Target |
|-----------|----------------------------------|
| PKI Certificates | Currently RSA-2048 or ECDSA P-256. Quantum-vulnerable. Migration target: CRYSTALS-Dilithium (ML-DSA, FIPS 204). |
| Key Exchange | Currently ECDH. Quantum-vulnerable to Shor's algorithm. Migration target: CRYSTALS-Kyber (ML-KEM, FIPS 203). |
| Hash Functions | SHA-256/SHA-384. Grover's algorithm reduces effective security. Migration target: SHA-3/SHAKE (FIPS 205). |
| HSM-Signed Audit Logs | Signatures using classical algorithms. Priority migration target given 7-year retention window. |
| FIDO2/WebAuthn | Underlying cryptography quantum-vulnerable. Hardware key vendors publishing PQC roadmaps — monitor and upgrade on vendor timeline. |

### 13.2 Migration Roadmap

| Priority & Component | Target Timeline |
|----------------------|-----------------|
| Critical: Audit log signing | Migrate to ML-DSA within 12 months |
| High: PKI certificate infrastructure | Hybrid classical + PQC within 18 months. Full PQC within 36 months. |
| High: Key exchange for session encryption | ML-KEM hybrid mode within 18 months |
| Medium: FIDO2 hardware keys | Monitor vendor PQC roadmap. Upgrade on availability. |
| Medium: TLS inter-component communication | TLS 1.3 with PQC cipher suites within 24 months |
| Lower: Internal hash functions | SHA-3 migration within 36 months |

### 13.3 Hybrid Cryptography Period

During the transition period, **hybrid cryptography** — running classical and post-quantum algorithms simultaneously — is mandatory. This ensures communications are protected against both classical and quantum attacks during the migration window.

> **Governance Note:** The Governance Committee must receive a quarterly quantum readiness update from the System Administrator until full PQC migration is complete.

---

## 14. Insider Threat Detection

*★ New in v3.0*

Section 6.4 addresses externally compromised operator identities. This section addresses the distinct and arguably more dangerous scenario: the authorised insider who is actively working against the framework. Separation of Duties prevents collusion between teams but does not detect a solo insider who is authenticated, authorised, and deliberately misusing their access.

### 14.1 Behavioural Baseline & Anomaly Detection

| Domain | Requirement |
|--------|-------------|
| Behavioural Baseline | Normal operator activity patterns established during onboarding and refined over first 30 days. Baseline covers: typical query types, session duration, finding volumes, and access patterns. |
| Query Anomaly Detection | Queries that significantly deviate from operator's role scope or historical patterns trigger automated review flag. |
| Access Pattern Monitoring | Unusual finding access patterns — accessing findings outside own session, accessing VTO outputs without authorisation — trigger alert. |
| Volume Anomalies | Significant deviation from typical output volumes flagged for review. |
| After-Hours Access Attempts | Any access attempt outside approved session schedule automatically logged as anomaly and reviewed by Governance. |
| UEBA Integration | User and Entity Behaviour Analytics platform correlates behavioural signals across all monitored dimensions with machine learning baseline.[^8] |

### 14.2 Canary Finding Protocol

Canary findings are deliberately fabricated vulnerability reports embedded within the legitimate findings pool, indistinguishable from real findings to any operator who should not have access to them. If a canary finding appears in an external context, it provides definitive proof of insider leakage and identifies the access point.

- Canary findings created by Governance Committee — never by Red or Blue Team operators
- Canary content is sufficiently realistic to be actionable if leaked but references non-existent components
- Canary access logged with the same granularity as real findings — any canary access outside authorised scope is an immediate alert
- Canary seeding frequency and placement is known only to Governance Committee and CISO

### 14.3 Deterrence Controls

| Domain | Requirement |
|--------|-------------|
| Formal Acknowledgement | Operators formally acknowledge monitoring at every session start. Psychological deterrence is a meaningful control — people behave differently when they know they are observed. |
| Personnel Security Re-Vetting | All operators undergo personnel security re-vetting every 12 months. |
| Rotation Policy | Operators rotated between projects on a maximum 18-month cycle. |
| Reporting Culture | Operators actively encouraged to report colleague behaviour inconsistent with the framework, protected under the whistleblower framework. |

---

## 15. AI Output Integrity Verification

*★ New in v3.0*

This section addresses whether the AI's outputs can be trusted. Three distinct integrity risks exist: **hallucination** (the AI generates plausible but false findings), **adversarial prompting** (a malicious operator manipulates the AI), and **tampering** (AI outputs are modified after generation and before review).

### 15.1 Cryptographic Output Integrity

| Domain | Requirement |
|--------|-------------|
| Generation-Time Signing | Every AI output is cryptographically signed at the moment of generation using the AI model service account's private key. Any post-generation modification is detectable. |
| Hash Chain Logging | Outputs are linked in a hash chain — each output's hash includes the previous output's hash. Retroactive modification breaks the chain. |
| Tamper-Evident Transmission | Outputs transmitted from AI to human reviewer via authenticated, integrity-verified channel. |
| Immutable Finding Registry | All signed outputs registered in the WORM audit log immediately. Original signed version is the authoritative record. |

### 15.2 Hallucination Detection Protocol

- Every finding must reference a verifiable, identifiable component — system name, software version, configuration identifier. Findings without specific component attribution are automatically flagged for mandatory human review before any action
- Critical and High severity findings require independent human expert verification before entering the VTO pipeline
- Cross-model verification for Critical findings — a second independent AI instance reviews the finding without knowledge of the first model's output; significant divergence triggers escalated human review
- Historical finding pattern analysis — findings that significantly deviate from the AI model's historical patterns for similar system types are flagged as potential anomalies

### 15.3 Adversarial Prompt Detection

- All operator queries logged in full — the complete query, not a summary, is recorded with the session log
- Query content analysis — automated screening for patterns associated with prompt injection, jailbreaking, or scope manipulation
- Scope deviation alerts — queries referencing systems, topics, or objectives outside the operator's approved session scope trigger immediate alert
- AI refusal logging — instances where the AI declines to respond are logged as potential indicators of adversarial interaction

---

## 16. Regulatory & Jurisdictional Framework

*★ New in v3.0*

A vulnerability found in a system in Country A, by an organisation in Country B, using an AI model from Company C, affecting users in Country D — which law applies? This section provides a structured regulatory map.

### 16.1 Regulatory Disclosure Timeline Map

| Jurisdiction / Framework | Reporting Timeline |
|--------------------------|-------------------|
| India — CERT-In[^9] | 6 hours for initial report. 30 days for detailed report. |
| India — DPDP Act 2023[^10] | As soon as practicable. Specific timeline pending subordinate legislation. |
| India — RBI Cyber Security Framework | 2–6 hours depending on severity. Immediate for critical infrastructure. |
| EU — NIS2 Directive[^11] | 24 hours initial notification. 72 hours detailed report. |
| EU — GDPR[^12] | 72 hours to supervisory authority. Without undue delay to affected individuals. |
| US — SEC Cybersecurity Rules | 4 business days after determining incident is material. |
| Global — Responsible Disclosure | 90 days standard (Google Project Zero benchmark[^3]). Accelerated for active exploitation or life-safety risk. |

### 16.2 Jurisdictional Conflict Resolution

- **Most restrictive timeline applies** — if CERT-In requires 6 hours and NIS2 requires 24 hours, the 6-hour obligation governs for the overlapping scope
- **Parallel notification** — where multiple regulators have jurisdiction, notifications are prepared and transmitted in parallel, not sequentially
- **Legal counsel engaged at discovery** — for any finding with multi-jurisdictional implications, legal counsel is engaged at the point of discovery, not at the point of disclosure
- **Safe harbour documentation** — good faith compliance efforts documented from the moment of discovery

### 16.3 Authorised Computer Access Verification

All AI-assisted vulnerability testing must operate within explicitly authorised scope.

> **Legal Boundary:** Testing systems beyond explicitly authorised scope — regardless of defensive intent — constitutes unauthorised computer access under India's IT Act Section 43[^13], UK Computer Misuse Act, US CFAA, and equivalent legislation globally. Ignorance of scope boundaries is not a legal defence.

---

## 17. Digital Forensics & Evidence Preservation

*★ New in v3.0*

This framework produces extensive audit logs, session recordings, and findings documentation. These records may ultimately be required as evidence in criminal prosecutions, civil litigation, or regulatory investigations. A log that is technically intact but lacks forensic chain of custody is potentially inadmissible.

### 17.1 Chain of Custody

| Domain | Requirement |
|--------|-------------|
| Custody Initiation | Chain of custody documentation begins at session start — not at the point an incident is identified. Every session is treated as potentially evidentiary from its inception. |
| Custodian Designation | Each log and finding has a designated custodian responsible for its integrity. Custodian changes are logged with timestamp and reason. |
| Access Logging | Every access to an evidentiary record — including read access — is logged. |
| Integrity Verification | Hash of each evidentiary record computed at creation and verified at each access. Hash mismatch terminates access and triggers immediate Governance alert. |
| Transfer Protocol | Transfer of evidentiary records between custodians requires written acknowledgement, hash verification, and Governance Committee notification. |

### 17.2 Forensic Standards Compliance[^14]

- ISO/IEC 27037 — Guidelines for identification, collection, acquisition, and preservation of digital evidence
- ISO/IEC 27041 — Guidance on assuring suitability and adequacy of incident investigative methods
- NIST SP 800-86 — Guide to integrating forensic techniques into incident response
- All forensic imaging uses write-blocking to prevent modification of original media
- Forensic images verified by MD5 and SHA-256 hash comparison against source

### 17.3 Evidence Lifecycle

| Domain | Requirement |
|--------|-------------|
| Retention Period | Standard retention: 7 years. Extended to indefinite for records associated with ongoing litigation, regulatory investigation, or criminal proceeding. |
| Preservation Hold | When litigation is reasonably anticipated, a legal hold is placed on all potentially relevant records. Scheduled deletion is suspended for held records. |
| Secure Destruction | At end of retention period, records destroyed using NIST SP 800-88 compliant methods. Destruction is logged and the destruction log itself retained for 3 years. |

---

## 18. Continuous Compliance Monitoring

*★ New in v3.0*

A governance framework reviewed quarterly is a framework that may be non-compliant for up to three months before anyone notices. Continuous compliance monitoring creates a real-time view of framework health.

### 18.1 Automated Control Testing

| Domain | Requirement |
|--------|-------------|
| RBAC Assignment Verification | Daily automated check confirms all active operator role assignments are current, approved, and consistent with the role definitions in Section 6.1. Unauthorised assignments trigger immediate alert. |
| ABAC Attribute Freshness | Real-time monitoring of ABAC attribute validity. Expired location verification, lapsed MFA, or unregistered device triggers immediate access denial and alert. |
| Certificate Validity Monitoring | Automated alerting when any certificate approaches expiry — 30 days, 14 days, and 7 days before expiry. |
| Session Recording Confirmation | At session start, automated check confirms session recording is active before any AI query is accepted. Recording failure is a hard block — session cannot proceed without active recording. |
| WORM Log Integrity Check | Daily automated hash verification of all audit log entries. Any integrity failure triggers immediate Governance alert and forensic preservation of affected logs. |
| Access Review Currency | Automated check that periodic access reviews have been completed within required timeframes. |

### 18.2 Key Risk Indicators (KRIs)

| KRI | Alert Threshold |
|-----|-----------------|
| Session Log Completeness | Below 100% — any incomplete session is an immediate alert |
| MFA Failure Rate | More than 3 failures per operator per 7 days — review required |
| Access Request Turnaround | More than 4 hours — escalate to Governance |
| Finding-to-Patch Cycle Time | More than 30 days for Critical findings — mandatory escalation |
| Canary Access Events | Any single event — immediate insider threat investigation |
| Vendor Session Coverage | Below 100% PAM recording — any unrecorded vendor session is an immediate alert |

### 18.3 Benchmarking Standards

Framework controls are benchmarked annually against:[^15]

- NIST Cybersecurity Framework (CSF) 2.0 — Identify, Protect, Detect, Respond, Recover
- ISO/IEC 27001:2022 — Information Security Management System
- CIS Controls v8 — Prioritised cybersecurity best practices[^16]
- NIST AI Risk Management Framework (AI RMF) — AI-specific governance[^17]
- India CERT-In Guidelines — Regulatory compliance baseline

---

## 19. Human Factors & Operational Resilience

*★ New in v3.0*

Every technical control in this framework is ultimately operated by humans. Cognitive overload, decision fatigue, stress, and psychological pressure all degrade the quality of human judgement — and human judgement is the ultimate safeguard in this framework at every critical decision point.

### 19.1 Operator Certification Requirements

| Domain | Requirement |
|--------|-------------|
| Technical Qualification | Operators must demonstrate technical competency in IAM, cybersecurity fundamentals, and the specific AI tool deployed. Competency assessed before first session and annually. |
| Psychological Fitness Assessment | Initial psychological fitness assessment by qualified occupational psychologist. Re-assessment triggered by significant life events. |
| Framework Induction | Mandatory structured induction covering all framework rules, escalation procedures, and ethical principles. Induction assessment required before any operational access. |
| Ongoing Training | Mandatory training updates when framework is materially updated (v3.0 triggers updated induction). Quarterly security awareness refresher for all operators. |

### 19.2 Fatigue & Cognitive Load Management

| Domain | Requirement |
|--------|-------------|
| Session Duration Limit | Maximum 4-hour continuous session. No operator may conduct more than 2 sessions in a 24-hour period, or more than 8 sessions in a 7-day period. |
| Mandatory Break Protocol | Sessions exceeding 2 hours require a documented 15-minute break. Operator must step away from the session room. Break is logged. |
| Complex Finding Protocol | Findings assessed as Critical severity trigger a mandatory 30-minute review period before any operator action. Prevents rushed decision-making on highest-stakes findings. |
| Cognitive Load Monitoring | Session complexity is tracked. If a single session produces an unusually high volume of findings, the session is paused for human review before continuing. |

### 19.3 Psychological Safety & Error Management

- **Near-miss reporting** — operators explicitly encouraged to report situations where the framework was nearly violated. Near-misses treated as valuable intelligence, not disciplinary triggers.
- **Error response protocol** — when an operator makes an error within the framework, the default response is a structured review to understand root cause, not punitive action. Punitive responses to honest errors create concealment incentives.
- **Mandatory post-incident debrief** — after any Red Alert event, all involved operators participate in a structured debrief focused on learning, not blame. An independent facilitator conducts the debrief.
- **Stress reporting channel** — operators experiencing significant personal stress have a confidential channel to self-report and request temporary suspension of operational duties without career consequence.

### 19.4 Succession & Single Point of Failure Prevention

- Every designated role — VTO, Red Team Lead, Blue Team Lead, Governance Chair — must have a trained, currently authorised backup
- Backup operators exercised at least quarterly — they execute real session responsibilities under supervision
- Key person risk register maintained by Governance Committee — identifies roles where single-person dependency exists and tracks mitigation progress
- Critical process knowledge must be documented, not held only in individuals' heads. Documentation reviewed for accuracy every 6 months

---

## 20. Agentic AI Controls

*★ New in v3.0 — The Most Forward-Looking Section*

This framework was originally designed for a query-response AI interaction model. The emergence of agentic AI fundamentally changes this dynamic. Agentic AI can plan multi-step tasks, execute sequences of actions autonomously, and adapt its approach based on intermediate results — all without a human query at each step.

In a cybersecurity context, an agentic AI could autonomously chain vulnerability discovery steps and produce exploit chains of a sophistication that exceeds what any query-response interaction could achieve. The governance controls for query-response AI are necessary but not sufficient for agentic AI.

### 20.1 Agentic Action Taxonomy

| Action Class | Description | Authorised? |
|--------------|-------------|-------------|
| Permitted Autonomous | Single-step analysis within predefined scope. Information gathering. Vulnerability classification. | Yes — logged |
| Conditionally Permitted | Multi-step analysis chains up to 5 steps. Intermediate findings review. Scope-bounded exploration. | Yes — with mandatory human checkpoint at step 3 |
| Requires Approval | Action chains exceeding 5 steps. Novel methodology not in session brief. Findings suggesting critical severity. | Human approval required before continuation |
| Prohibited | Any action with external network reach. System modification of any kind. Credential access or manipulation. Actions outside approved virtual environment. | Never — hard technical block |

### 20.2 Action Chain Controls

| Domain | Requirement |
|--------|-------------|
| Maximum Autonomous Steps | No agentic action chain may exceed 5 steps without a mandatory human checkpoint. At checkpoint, operator reviews intermediate findings and explicitly approves continuation. |
| Reversibility Requirement | Agentic AI may only take actions that are reversible within the virtual environment. Any action that cannot be undone by environment rollback is prohibited. |
| Scope Boundary Enforcement | Technical controls prevent agentic AI from accessing systems, files, or network segments outside its approved session scope. Attempted boundary violations trigger session suspension. |
| Action Velocity Limiting | Rate limiting on agentic action sequences. Unusually rapid action chains trigger automatic session suspension pending human review. |
| Goal Alignment Verification | Before initiating an agentic task, the AI model must articulate its planned approach and objective. Divergence between stated plan and actual actions is an alert trigger. |

### 20.3 Agentic Identity

| Domain | Requirement |
|--------|-------------|
| Agentic Service Identity | A separate service account identity is provisioned for agentic AI operations, with more restricted permissions than the query-response identity. |
| Agentic Session Logging | Every autonomous action is logged under the agentic service identity with full action detail, preceding context, and outcome. |
| Agentic Identity Suspension | The agentic service identity can be independently suspended without affecting query-response capabilities. |
| Human Override Priority | At any point during an agentic session, any authorised operator can issue a halt command that immediately terminates all autonomous action. The halt is logged with operator identity and reason. |

### 20.4 Kill Switch Protocol

The existence of an effective, reliably triggerable kill switch is non-negotiable for any agentic AI deployment. The kill switch must be:

- Immediately accessible to any authorised operator in the session room — physical and software-based mechanisms
- Effective within 5 seconds of activation — technical architecture must guarantee this
- Independently tested monthly — kill switch effectiveness is a continuous compliance check (Section 18)
- Non-bypassable by the AI — the kill switch operates at the infrastructure layer, not the application layer. The AI cannot disable its own kill switch
- Logged on every activation — kill switch use is always recorded regardless of reason

> **Agentic AI Principle:** An AI that can act autonomously requires governance that assumes it will. Design controls for the worst credible autonomous behaviour, not the expected behaviour. The kill switch is not a last resort — it is a primary control that should be used without hesitation whenever autonomous behaviour diverges from intent.

---

## 21. References

Citations follow the Chicago Manual of Style (17th edition). Full bibliography: [../../docs/references.md](../../docs/references.md)

[^1]: National Institute of Standards and Technology. "Zero Trust Architecture." NIST Special Publication 800-207, August 2020. https://doi.org/10.6028/NIST.SP.800-207.

[^2]: FIRST.org. "Common Vulnerability Scoring System v4.0: Specification Document." FIRST, November 2023. https://www.first.org/cvss/v4.0/specification-document.

[^3]: Google Project Zero. "Vulnerability Disclosure FAQ." Google, 2021. https://googleprojectzero.blogspot.com/p/vulnerability-disclosure-faq.html.

[^4]: Cybersecurity and Infrastructure Security Agency (CISA). "Alert (AA20-352A): Advanced Persistent Threat Compromise of Government Agencies, Critical Infrastructure, and Private Sector Organizations." CISA, December 17, 2020. https://www.cisa.gov/news-events/cybersecurity-advisories/aa20-352a.

[^5]: Freund, Andres. "Backdoor in Upstream xz/liblzma Leading to SSH Server Compromise." OpenWall, March 29, 2024. https://www.openwall.com/lists/oss-security/2024/03/29/4.

[^6]: National Institute of Standards and Technology. "Post-Quantum Cryptography: FIPS 203, 204, 205." NIST, August 2024. https://www.nist.gov/pqcrypto.

[^7]: National Security Agency. "Quantum Computing and Post-Quantum Cryptography FAQs." NSA Cybersecurity, August 2021. https://media.defense.gov/2021/Aug/04/2002821837/-1/-1/1/Quantum_FAQs.PDF.

[^8]: Gartner. "Market Guide for User and Entity Behavior Analytics." Gartner Research, December 2023.

[^9]: Indian Computer Emergency Response Team (CERT-In). "Directions under sub-section (6) of Section 70B of the Information Technology Act, 2000." Ministry of Electronics and Information Technology, Government of India, April 2022. https://www.cert-in.org.in/Directions70B.jsp.

[^10]: Ministry of Law and Justice, Government of India. "The Digital Personal Data Protection Act, 2023." Gazette of India Extraordinary Part II Section 1, August 2023. https://www.meity.gov.in/content/digital-personal-data-protection-act-2023.

[^11]: European Parliament and Council of the European Union. "Directive (EU) 2022/2555 (NIS2 Directive)." Official Journal of the European Union L 333, December 2022.

[^12]: European Parliament and Council of the European Union. "General Data Protection Regulation (EU) 2016/679." Official Journal of the European Union L 119, May 2016. https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32016R0679.

[^13]: Ministry of Law and Justice, Government of India. "The Information Technology Act, 2000 (Act 21 of 2000)." Gazette of India, June 2000, as amended by the Information Technology (Amendment) Act 2008.

[^14]: International Organization for Standardization. "ISO/IEC 27037:2012 — Guidelines for Identification, Collection, Acquisition and Preservation of Digital Evidence." ISO, 2012.

[^15]: National Institute of Standards and Technology. "Cybersecurity Framework 2.0." NIST, February 2024. https://www.nist.gov/cyberframework.

[^16]: Center for Internet Security. "CIS Controls Version 8." CIS, May 2021. https://www.cisecurity.org/controls/v8.

[^17]: National Institute of Standards and Technology. "Artificial Intelligence Risk Management Framework (AI RMF 1.0)." NIST AI 100-1, January 2023. https://doi.org/10.6028/NIST.AI.100-1.

---

*END OF DOCUMENT — Framework v3.0 — April 2026*  
*Author: Ikshudhanva P L*  
*AI should be something the world finds awe-inspiring, not something it fears.*
