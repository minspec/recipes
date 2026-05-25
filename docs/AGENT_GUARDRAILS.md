# Agent Guardrails

This repository is supply-chain-sensitive because recipes affect host applications at install time.

## Allowed agent roles

AI and automation tools may:

- inspect repository state
- summarize recipe behavior
- compare diffs
- draft proposed changes for human review
- generate validation reports
- identify policy conflicts

## Disallowed agent roles

AI and automation tools must not:

- create trusted source authority
- merge changes
- approve changes
- accept unsolicited code
- add dependencies or workflows without explicit maintainer intent
- introduce remote code sources
- silently rewrite recipe policy

Pull requests are enabled but restricted to collaborators only. That setting does not make AI agents, GitHub Apps, bots, automation, Dependabot, Copilot agents, browser agents, or external tools into maintainers or trusted source authorities.

## Required evidence for recipe changes

Any agent-produced recipe proposal should include:

- exact changed files
- expected host application diff
- source package being wired
- reason the recipe belongs here
- validation command output or manual validation notes
- security/trust-boundary concerns

## Bias toward no-op

When uncertain, agents should prefer no mutation and report the uncertainty.

Recipe automation is useful only when it preserves developer understanding and MinSpec source-of-truth control.
