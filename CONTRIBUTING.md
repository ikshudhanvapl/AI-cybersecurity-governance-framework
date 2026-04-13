# Contributing to the AI-Enabled Cybersecurity Governance Framework

Thank you for your interest in contributing to this framework. Given the sensitive and operational nature of this document, contributions are subject to a structured governance process.

---

## Who Can Contribute

Contributions are accepted from:

- **Registered industry partners** operating within the programme scope (e.g., Project Glasswing or equivalent)
- **Governance Committee members** with formal standing
- **Independent security researchers** proposing factual corrections, updated regulatory references, or technical amendments — subject to Governance Committee review

---

## Types of Contributions

### 1. Errata (Factual Corrections)
Corrections to factual errors, broken references, superseded regulatory timelines, or incorrect technical specifications. Use the [Errata issue template](.github/ISSUE_TEMPLATE/errata.md).

**Examples:**
- A regulatory disclosure timeline has changed
- A referenced standard has been superseded
- A technical specification (e.g., cryptographic algorithm) has been deprecated

### 2. Framework Amendments
Substantive proposed changes to policy content, new sections, or removal of existing requirements. Use the [Framework Amendment issue template](.github/ISSUE_TEMPLATE/framework-amendment.md).

**Examples:**
- A new threat category not currently addressed by the framework
- A proposed change to an access control requirement
- A new regulatory jurisdiction requiring coverage

### 3. Drafting Contributions (Pull Requests)
Registered industry partners may submit pull requests containing proposed markdown-formatted amendments. All PRs are reviewed by the Governance Committee before merging.

---

## Contribution Process

```
1. Open an Issue → 2. Governance Review → 3. Draft PR (if approved) → 4. Governance Approval → 5. Version Release
```

### Step 1: Open an Issue
Use the appropriate issue template. Provide as much context as possible, including:
- The specific section(s) affected
- The nature of the proposed change
- The rationale and any supporting references
- Any regulatory or operational urgency

### Step 2: Governance Review
The Governance Committee reviews all issues at its scheduled meetings (minimum quarterly). Urgent matters (e.g., regulatory changes with imminent effective dates) may be reviewed out-of-cycle. You will receive a response within 30 days for standard issues.

### Step 3: Draft PR (if approved in principle)
If the Governance Committee approves the amendment in principle, you may submit a pull request. PRs must:
- Target the `main` branch
- Modify the relevant `framework-v*.md` file(s)
- Follow the existing document structure and formatting
- Include a CHANGELOG.md entry describing the change
- Complete the [PR template](.github/PULL_REQUEST_TEMPLATE.md)

### Step 4: Governance Approval
The Governance Committee reviews the PR. Final approval requires a quorum of the Committee. Approved PRs are merged by a designated maintainer.

### Step 5: Version Release
Approved amendments are incorporated into a new framework version (following the major.minor convention) and announced via the repository's release mechanism.

---

## Style Guide

### Language
- Use **British English spelling** (authorise, defence, organisation, programme, recognised)
- Write in the present tense for requirements ("The VTO produces..." not "The VTO will produce...")
- Use imperative mood for mandates ("must", "shall") and permissive language for options ("may")

### Formatting (Markdown)
- Use `##` for top-level section headings, `###` for subsections
- Tables are preferred over bulleted lists for structured requirement pairs (Domain / Requirement)
- Callout boxes use blockquote syntax (`>`) for important notes and legal notices
- Section numbers must be maintained sequentially

### References
- New references must follow Chicago Manual of Style (17th edition)
- Add new references to both the section's inline citation and `docs/references.md`
- Prefer primary sources: government publications, standards bodies, peer-reviewed research

### New Sections
New sections must include:
- A clear statement of the threat or governance gap being addressed
- Rationale explaining why this is within the framework's scope
- Concrete, implementable requirements (not aspirational principles)
- At least one authoritative reference

---

## Code of Conduct

Contributions to this framework operate under a professional conduct standard consistent with the framework's own ethical principles:

- **Integrity:** Proposed amendments must be made in good faith, with the genuine intent of improving defensive security governance
- **Transparency:** Disclose any conflicts of interest relevant to a proposed amendment
- **Proportionality:** Proposed requirements must be proportionate to the threat they address
- **Respect:** All interactions in issues and PRs must be professional and constructive

Any contribution that appears designed to weaken framework controls, introduce ambiguity that could be exploited, or serve an undisclosed commercial interest will be rejected and may result in removal of access.

---

## Questions

For questions about the contribution process, contact the Governance Committee through the designated secure channel established under your programme access agreement.

For public technical questions, open a GitHub Discussion (if enabled) or an issue tagged `question`.
