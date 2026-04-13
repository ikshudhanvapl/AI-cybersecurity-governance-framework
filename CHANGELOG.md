# Changelog

All notable changes to the AI-Enabled Cybersecurity Governance Framework are documented here.

This file follows the [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) format, adapted for policy framework versioning. Framework versions do not follow semantic versioning — each major version represents a substantive governance expansion.

---

## [v3.0] — April 2026

**Version Title:** Comprehensive Framework with Full Threat Landscape Coverage  
**Governing Philosophy:** Known threats are better governed than unknown ones.  
**Supersedes:** v2.0

### Added — Ten New Sections

#### Section 11 — Supply Chain Identity Risk
- Formal identification of AI model vendor, cloud infrastructure provider, security tool vendors, MSPs, and software dependencies as distinct threat vectors
- Supply chain IAM controls including vendor session recording, model weight provenance verification, supply chain SoD, third-party security posture assessments, and vendor offboarding protocol
- Software Bill of Materials (SBOM) requirement for all virtual environment dependencies
- Model Weight Integrity Protocol: cryptographic hash verification, vendor-signed manifest, and independent third-party behaviour verification

#### Section 12 — Federated Identity & Cross-Organisation Collaboration
- Formal federation standards: SAML 2.0, OIDC, FIDO2 cross-domain, and PKI cross-certification
- External identity controls: time-limited guest access, external SoD enforcement, federated ABAC, and external audit trail
- Cross-organisation disclosure protocol: six-step procedure governing Governance Committee approval, VTO external-grade sanitisation, secure channel establishment, and follow-up verification

#### Section 13 — Quantum Cryptography Readiness
- Cryptographic inventory: current classical algorithms mapped to quantum vulnerability and NIST post-quantum migration targets (ML-DSA, ML-KEM, SHA-3)
- Migration roadmap with prioritised timeline: audit log signing (12 months), PKI infrastructure (18–36 months), key exchange (18 months), TLS (24 months), hash functions (36 months)
- Mandatory hybrid cryptography period during transition
- Quarterly quantum readiness reporting requirement

#### Section 14 — Insider Threat Detection
- Behavioural baseline and anomaly detection system: query anomaly detection, access pattern monitoring, volume anomalies, after-hours access, UEBA integration
- Canary Finding Protocol: fabricated findings embedded in legitimate pool, created exclusively by Governance Committee, for definitive insider leakage detection
- Deterrence controls: formal monitoring acknowledgement at session start, annual personnel security re-vetting, 18-month operator rotation policy, and protected reporting culture

#### Section 15 — AI Output Integrity Verification
- Cryptographic output integrity: generation-time signing, hash chain logging, tamper-evident transmission, and immutable finding registry
- Hallucination Detection Protocol: component attribution requirement, Critical/High finding expert verification, cross-model verification for Critical findings, and historical pattern analysis
- Adversarial Prompt Detection: full query logging, automated content analysis, scope deviation alerts, and AI refusal logging

#### Section 16 — Regulatory & Jurisdictional Framework
- Regulatory disclosure timeline map: CERT-In (6hr/30d), DPDP Act 2023, RBI (2–6hr), EU NIS2 (24hr/72hr), GDPR (72hr), SEC (4 business days), and global responsible disclosure (90 days)
- Jurisdictional conflict resolution principles: most restrictive timeline governs, parallel notification, legal counsel at discovery, safe harbour documentation
- Authorised computer access verification requirements with legal boundary notice

#### Section 17 — Digital Forensics & Evidence Preservation
- Chain of custody framework: custody initiation at session start (not incident identification), custodian designation, access logging, integrity verification, and transfer protocol
- Forensic standards compliance: ISO/IEC 27037, ISO/IEC 27041, NIST SP 800-86
- Evidence lifecycle: 7-year standard retention, indefinite hold for active proceedings, legal hold on reasonably anticipated litigation, NIST SP 800-88 compliant secure destruction

#### Section 18 — Continuous Compliance Monitoring
- Automated control testing: daily RBAC verification, real-time ABAC attribute monitoring, certificate expiry alerting (30/14/7 days), session recording hard block, daily WORM log integrity check, and access review currency tracking
- Governance Committee real-time compliance dashboard specification
- Six Key Risk Indicators (KRIs) with defined alert thresholds
- Annual benchmarking against NIST CSF 2.0, ISO/IEC 27001:2022, CIS Controls v8, NIST AI RMF, and CERT-In Guidelines

#### Section 19 — Human Factors & Operational Resilience
- Operator certification requirements: technical qualification, psychological fitness assessment, framework induction, and ongoing training
- Fatigue and cognitive load management: 4-hour session limit, 2-session-per-24-hour cap, 8-session-per-7-day cap, mandatory 2-hour break protocol, 30-minute Critical finding review period, cognitive load monitoring
- Psychological safety and error management: near-miss reporting, non-punitive error response protocol, mandatory post-incident debrief, and confidential stress reporting channel
- Succession and single point of failure prevention: trained backups for every designated role, quarterly backup operator exercises, key person risk register, knowledge documentation requirement

#### Section 20 — Agentic AI Controls
- Agentic action taxonomy: four classes (Permitted Autonomous, Conditionally Permitted, Requires Approval, Prohibited) with clear scope definitions
- Action chain controls: 5-step maximum before human checkpoint, reversibility requirement, scope boundary technical enforcement, action velocity limiting, goal alignment verification
- Agentic identity management: separate service account for agentic operations, granular agentic session logging, independent suspension capability, human override priority
- Kill Switch Protocol: 5-second maximum activation time, monthly independent testing, infrastructure-layer implementation (non-bypassable by AI), mandatory activation logging

### Changed
- Fourth governing principle added: **Complete threat coverage** — Govern what you know before it becomes what you didn't.
- References expanded from 10 to 19 Chicago-style citations

---

## [v2.0] — April 2026

**Version Title:** Enhanced Framework with IAM-as-Primary-Defence Architecture  
**Supersedes:** v1.0

### Added

#### Section 0 — IAM as Primary Defence (New Foundational Section)
- Formal articulation of IAM as the primary security architecture, not a supporting control
- IAM-First Argument table: maps all framework controls to their identity foundation
- Explanation of why IAM-first governance is specifically necessary for AI capability classes

#### Section 4.3 — AI Model Identity Management
- Non-human IAM discipline applied to the AI model itself
- Service account ownership requirement: designated human owner, orphaned account suspension
- 90-day credential rotation cycle, automated and logged
- Session token invalidation on any session suspension event
- Orphaned credential revocation within 15 minutes
- Model Instance Registry in central IAM system
- Least Privilege principle applied to AI service account

#### Section 6.4 — Identity Compromise Response Protocol
- Distinct from Red Alert (findings-triggered); addresses identity compromise during or proximate to active sessions
- Six-step response: session suspension, token revocation within 60 seconds, Zero Trust re-verification, forensic VTO review, Governance Committee scope assessment, replacement operator on fresh environment
- Identity Integrity Principle formally stated

#### Section 10.1 — Model Version Control
- Version registration requirement for every deployed model version
- Governance Committee upgrade approval with capability assessment
- Retrospective log association: logs permanently tied to the model version that generated them
- Capability regression testing before any new version deployment
- Emergency rollback capability: 30-minute execution requirement
- Version sunset: 24-month fitness review, mandatory retirement for known security issues

### Fixed
- **Responsible disclosure window corrected to 90 days** (per Google Project Zero industry standard). v1.0 incorrectly referenced 135 days, which is non-standard.

---

## [v1.0] — April 2026

**Version Title:** Initial Framework Specification

### Added — Seven Core Rules

**Rule 1 — Separation of Duties (SoD)**
- Personnel, systems, communications, management, and audit log separation requirements
- 12-month cooling-off period between Red Team and Blue Team roles
- Vulnerability Translation Officer (VTO) role established

**Rule 2 — Virtual Environment Mandate**
- Network-isolated VM/sandbox specifications
- Snapshot policy and rollback requirement
- Device vulnerability exception and emergency procedure

**Rule 3 — Test and Document Only**
- Defined authorised AI actions: scan, simulate, document, suggest, score
- Vulnerability Report documentation standard: 8 required fields per CVSS 4.0

**Rule 4 — Access Controls (RBAC + ABAC)**
- Six-role RBAC definition: Red Team Operator, Blue Team Engineer, VTO, Governance Committee Member, CISO, System Administrator
- Six-attribute ABAC enforcement: location, device, time window, MFA status, session duration, concurrent sessions
- Physical access controls: premises restriction, biometric room access, four-eyes principle

**Rule 5 — Blue Team Remediation Protocol**
- Seven-step remediation workflow from VTO sanitised brief to post-deployment verification
- Governance Committee deployment authorisation gate

**Rule 6 — Critical Escalation Protocol**
- Three red alert trigger categories: financial, human life, national security
- Automated response (T+0 to T+5): session suspension, environment freeze, device network suspension, auto-report, CISO notification
- Human escalation chain (T+5 to T+60): Governance Committee, CISO, legal counsel, law enforcement, disclosure
- 15-minute Governance Committee acknowledgement SLA; 60-minute CISO action plan SLA

**Rule 7 — The Common Sense Principle**
- Five operationalising mechanisms: ethical system prompt, proportionality test, ethics audits, whistleblower protection, sunset review

**IAM Architecture**
- Identity Provider, FIDO2/WebAuthn MFA, PAM, Just-In-Time Access, Zero Trust Network, Certificate Lifecycle, WORM Audit Logging, Privileged Session Management (7-year retention)

---

*For proposed amendments or corrections, see [CONTRIBUTING.md](CONTRIBUTING.md) and use the issue templates in [.github/ISSUE_TEMPLATE/](.github/ISSUE_TEMPLATE/).*
