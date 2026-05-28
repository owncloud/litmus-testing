# agents.md -- Litmus Testing

## Repository Overview

CI configuration for running Litmus WebDAV compliance tests nightly against ownCloud builds. Licensed under MIT. Contains no application code -- only CI pipeline definitions.

- **Product family:** Infrastructure / Tooling
- **Primary language(s):** YAML (CI pipeline definitions)

## Architecture & Key Paths

- Root directory contains CI configuration files (Drone CI)
- `.drone.yml` -- Main pipeline definition

## Development Conventions

- Drone CI pipeline configuration
- Nightly test execution schedule
- Tests run against ownCloud server Docker images

## Build & Test Commands

Tests are executed automatically via CI. No local build commands are needed.

## Important Constraints

- Licensed under MIT. The OSPO is driving Apache 2.0 migration across repositories.
- Do not introduce new **copyleft-licensed dependencies** (GPL, AGPL, LGPL, MPL) without explicit discussion in an issue first. This is especially important for repos that are migrating to or already under Apache 2.0, as copyleft dependencies would block or complicate that migration.
- All contributions require a DCO sign-off.


## OSPO Policy Constraints

### GitHub Actions
- **Only** use actions owned by `owncloud`, created by GitHub (`actions/*`), verified on the GitHub Marketplace, or verified by the ownCloud Maintainers.
- Pin all actions to their full commit SHA (not tags): `uses: actions/checkout@<SHA> # vX.Y.Z`
- Never introduce actions from unverified third parties.

### Dependency Management
- Dependabot is configured for automated dependency updates.
- Review and merge Dependabot PRs as part of regular maintenance.
- Do not introduce new dependencies without discussion in an issue first.

### Git Workflow
- **Rebase policy**: Always rebase; never create merge commits. Use `git pull --rebase` and `git rebase` before pushing.
- **Signed commits**: All commits **must** be PGP/GPG signed (`git commit -S -s`).
- **DCO sign-off**: Every commit needs a `Signed-off-by` line (`git commit -s`).
- **Conventional Commits & Squash Merge**: Use the [Conventional Commits](https://www.conventionalcommits.org/) format where the repository enforces it. Many repos use squash merge, where the PR title becomes the commit message on the default branch — apply Conventional Commits format to PR titles as well. A reusable GitHub Actions workflow enforces this.

## Context for AI Agents

This is a CI-only repository with no application code. Changes typically involve modifying the CI pipeline to test against new ownCloud versions or adjust test parameters.
