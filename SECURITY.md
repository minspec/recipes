# Security Policy

MinSpec Recipes controls install-time wiring for MinSpec-compatible packages. A recipe can alter configuration, routes, assets, environment templates, and bundle registration, so recipe changes are treated as supply-chain-sensitive.

## Reporting security issues

Please report security issues through GitHub's private vulnerability reporting flow when available, or through an official maintainer contact published by the MinSpec organization.

Do not disclose suspected vulnerabilities publicly before maintainers have had a reasonable opportunity to review them.

## Security posture

During incubation:

- pull requests are enabled but restricted to collaborators only; collaborator PR access is not a public contribution path
- unsolicited code and recipe PRs are not part of the trusted source path
- recipe changes must be small and inspectable
- dependency, workflow, and source-authority changes require maintainer review
- AI tools may generate evidence, but they do not approve or merge changes
- AI agents, GitHub Apps, bots, automation, Dependabot, Copilot agents, browser agents, and external tools are not maintainers and do not gain source authority from collaborator-only PR settings
- installation behavior should be deterministic and reviewable

## Sensitive areas

Recipe changes require heightened review when they touch:

- Composer scripts or plugins
- GitHub Actions or release workflows
- remote URLs or package sources
- environment variables and secrets
- authentication or authorization configuration
- routes, controllers, or public assets
- generated files copied into host applications
- any behavior that relaxes existing policy or trust boundaries
