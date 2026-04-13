# Git Setup Instructions

## Initialising the Repository

```bash
cd ai-cybersecurity-governance-framework
git init
git add .
git commit -m "feat: initial release of AI-Enabled Cybersecurity Governance Framework

- v1.0: Initial Framework Specification (7 core rules)
- v2.0: IAM-as-Primary-Defence Architecture (AI model identity, identity compromise response, model version control)
- v3.0: Comprehensive Framework — full threat landscape coverage (supply chain, quantum readiness, insider threat, agentic AI controls, and 6 further sections)

Author: Ikshudhanva P L
Date: April 2026"
```

## Tagging Versions

```bash
git tag -a v1.0 HEAD~2 -m "Framework v1.0 — Initial Framework Specification"
git tag -a v2.0 HEAD~1 -m "Framework v2.0 — IAM-as-Primary-Defence Architecture"
git tag -a v3.0 HEAD    -m "Framework v3.0 — Comprehensive Framework"
```

## Pushing to GitHub

```bash
git remote add origin https://github.com/<your-username>/ai-cybersecurity-governance-framework.git
git branch -M main
git push -u origin main
git push origin --tags
```

## Recommended Repository Settings (GitHub)

After pushing, configure the following in your GitHub repository settings:

- **Description:** Red Team / Blue Team Operational Policy for Advanced AI Models — Governance framework for frontier AI deployments in cybersecurity environments
- **Topics:** `cybersecurity`, `ai-governance`, `iam`, `zero-trust`, `red-team`, `blue-team`, `vulnerability-management`
- **Branch protection on `main`:** Require pull request reviews before merging (minimum 1 reviewer)
- **Issues:** Enable and use the provided templates
- **Discussions:** Optional — for community engagement on future versions

## Branch Strategy (Recommended)

```
main          ← current stable version (v3.0)
├── develop   ← ongoing amendments under Governance review
└── vX.Y-draft ← draft of next version (e.g., v3.1-draft)
```
