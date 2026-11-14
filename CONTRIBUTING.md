# Contributing

**Status:** Aproved · **Version:** 1.1 · **Last updated:** 2026-14-11 · **Owner:** Product owner (Eniola & Chioma)

This guide applies to everyone who changes this repository: team members and any AI coding agent working on their behalf.

## Workflow

1. Pick a backlog item and confirm its acceptance criteria in the Product Requirements.
2. Create a branch: `feature/<short-description>`, `fix/<short-description>`, or `docs/<short-description>`.
3. Write failing tests first, then the smallest implementation that passes them.
4. Open a pull request. **The author does not merge their own pull request**; another team member reviews and merges.
5. Update the affected requirements, API documentation, tests, Decision Record, and [Changelog](05-governance/CHANGELOG.md).

Keep commits small and focused on one change. Aim for pull requests that touch about five files or fewer.

## Pull request checklist

Use the review checklist in [Documentation Standards](05-governance/DOCUMENTATION_STANDARDS.md#7-review-checklist), plus:

- [ ] The author can explain the change in two sentences without looking at it.
- [ ] Every new route has tests for unauthenticated access and cross-user access.
- [ ] No credentials, real CVs, session tokens, or personal data are included.

## Working with an AI coding agent

An AI agent is a tool used by a team member. It has no authority over scope, requirements, or approvals.

1. Give it one task at a time, tied to a backlog item.
2. Provide the relevant document section, the acceptance criteria, and the files it may change.
3. Ask for failing tests first, then the implementation.
4. The agent must not edit requirements, API contracts, or approved decisions. It may propose changes in a pull request for a human to approve.
5. A human runs the tests and reads every line of the diff before it is merged.
6. Never paste real CVs, secrets, `.env` files, or production data into an agent session. Use synthetic fixtures.

Suggested prompt shape:

```text
Task: <backlog ID and title>
Context: <document section and acceptance criteria>
Files you may change: <list>
Do not change: docs/ approved content, committed migrations
Deliver: failing tests first, then the minimal implementation, then a note on any assumptions.
```

## Data and secrets

- Use synthetic data for development, tests, and demos.
- Keep secrets in environment variables; commit only `.env.example`.
- Report a suspected leak immediately and rotate the affected secret.
