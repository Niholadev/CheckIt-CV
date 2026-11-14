# RoleFit CV — Product and Engineering Documentation

**Status:** Proposed · **Version:** 1.1 · **Last updated:** 2026-11-11 · **Owner:** Product owner (name to be added)

RoleFit CV is a web application that helps students and early-career professionals prepare focused, evidence-based CVs for specific internship, graduate-trainee, and entry-level opportunities.

Unlike a conventional CV template builder, RoleFit CV separates the user’s master career profile from individual application-ready CV snapshots. A user can maintain one accurate source profile, review requirements identified in a target job description, inspect evidence-based skill alignment, and create a tailored CV without altering the original profile.

## Product principles

1. **User ownership** — Users control their profile, analyses, and CV versions. The system never publishes or shares private information without explicit user action.
2. **Evidence before claims** — A skill is classified as matched only when supported by a profile entry or associated project/experience record.
3. **Transparency** — Matching results include explanations, evidence references, and a clear distinction between confirmed and unconfirmed information.
4. **Truthful assistance** — The product may recommend emphasis and clearer wording, but it must not invent experience, skills, metrics, or qualifications.
5. **Progressive scope** — The initial release focuses on a reliable core workflow. Advanced automation and integrations are deferred until the core product is validated.

## Product boundary

### Included in the initial release

- Account registration, authentication, and account deletion.
- A structured career profile containing education, skills, projects, experience, certifications, and achievements.
- Pasted job-description text for analysis.
- Technical-skill extraction using a versioned, curated dictionary.
- User review of extracted requirements.
- Evidence-based matching between reviewed requirements and profile records.
- Requirement coverage reporting and project-relevance recommendations.
- Creation and storage of tailored CV snapshots.
- One responsive, ATS-conscious CV template.
- PDF export.
- Basic dashboard views for recent analyses and saved CV versions.

> **Delivery note.** These capabilities are delivered incrementally across the milestones in the [Release Roadmap](01-product/RELEASE_ROADMAP.md). The public MVP release requires all of them.

### Explicitly out of scope

- Automated scraping of job boards.
- Automated job-application submission.
- Payments or subscription billing.
- Recruiter-side applicant tracking.
- Fully automated AI rewriting of professional experience.
- Integration with third-party recruitment platforms.
- Guarantees of interview invitations, hiring outcomes, or ATS acceptance.

## Documentation map

| Area | Document | Purpose |
|---|---|---|
| Product | [Product Requirements](01-product/PRODUCT_REQUIREMENTS.md) | Defines users, problems, scope, and functional requirements |
| Product | [User Journeys](01-product/USER_JOURNEYS.md) | Describes primary user workflows |
| Product | [Release Roadmap](01-product/RELEASE_ROADMAP.md) | Defines delivery milestones and release gates |
| Design | [System Architecture](02-design/SYSTEM_ARCHITECTURE.md) | Describes components, boundaries, and data flow |
| Design | [Data Model](02-design/DATA_MODEL.md) | Defines core entities and relationships |
| Design | [API Contract](02-design/API_CONTRACT.md) | Defines the initial REST interface |
| Engineering | [Skill Extraction](03-engineering/SKILL_EXTRACTION.md) | Specifies extraction rules, evidence, and limitations |
| Engineering | [Matching and Coverage](03-engineering/MATCHING_AND_COVERAGE.md) | Specifies match states, scoring, and recommendations |
| Engineering | [Quality Assurance](03-engineering/QUALITY_ASSURANCE.md) | Defines testing and release-quality practices |
| Operations | [Security and Privacy](04-operations/SECURITY_AND_PRIVACY.md) | Defines security, privacy, retention, and operational controls |
| Operations | [Deployment and Runbook](04-operations/DEPLOYMENT_AND_RUNBOOK.md) | Defines deployment, configuration, monitoring, and incident response |
| Governance | [Decision Record](05-governance/DECISION_RECORD.md) | Records significant architectural and product decisions |
| Governance | [Documentation Standards](05-governance/DOCUMENTATION_STANDARDS.md) | Defines how documentation is maintained |
| Governance | [Changelog](05-governance/CHANGELOG.md) | Records revisions to this documentation pack |
| Guides | [Getting Started](06-guides/GETTING_STARTED.md) | Explains how to set up the repository and begin building |
| Repository | [Contributing](CONTRIBUTING.md) | Defines team workflow, review rules, and AI-agent working agreement |

## Document authority

**Current status:** every document in this pack is **Proposed** until the owners record approval in the approval log in the [Decision Record](05-governance/DECISION_RECORD.md). Until then, nothing here is binding for the release.

Requirements marked **Approved** are binding for the current release. Items marked **Proposed**, **Under review**, or **Deferred** require explicit approval before implementation.

When documents conflict, apply this precedence:

1. Approved product requirements.
2. Approved decision records.
3. Technical specifications.
4. Implementation guides.

Conflicts must be recorded and resolved; contributors must not silently select a preferred interpretation.

## Getting started

See [Getting Started](06-guides/GETTING_STARTED.md) for prerequisites, repository layout, local setup, and the recommended build order. Copy `.env.example` to `.env` and replace the placeholders; never commit `.env`.

## Repository conventions

- Use feature branches named `feature/<short-description>`, `fix/<short-description>`, or `docs/<short-description>`.
- Keep commits small, descriptive, and focused on one change.
- Do not commit credentials, real CVs, production data, session tokens, or personal contact information.
- Use synthetic fixtures for development and testing.
- Update affected requirements, API documentation, tests, and decision records when behavior changes.
- A feature is complete only when its acceptance criteria are met and relevant tests pass.
- Follow [CONTRIBUTING.md](CONTRIBUTING.md) for review rules and the use of AI coding agents.
- Add an entry to the [Changelog](05-governance/CHANGELOG.md) when documentation changes.
