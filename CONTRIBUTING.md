# Contributing

MinSpec Recipes is founder-controlled during incubation.

Public visibility does not imply public write access, public governance, or acceptance of unsolicited code mutation.

## Accepted during incubation

- questions
- reproducible bug reports
- documentation questions
- security reports
- design feedback about recipe boundaries
- evidence that a recipe causes surprising or unsafe installation behavior

## Not accepted during incubation

- unsolicited code PRs
- unsolicited recipe PRs
- generated code drops
- copied snippets from unapproved sources
- dependency or workflow changes without maintainer approval
- broad refactors that bypass MinSpec doctrine

## Trusted source path

Only official MinSpec repositories and approved source paths may provide code or recipe content.

AI tools may help inspect, explain, test, or draft proposals. They do not approve, merge, or establish source authority.

## Recipe review expectations

Any future recipe change should explain:

- which package it wires
- why the recipe belongs here rather than in package runtime code
- which files it creates or modifies
- what happens on a clean `minspec/skeleton` application
- whether the behavior is reversible or easy to audit
- whether it adds environment variables, routes, bundles, assets, commands, or scripts
- what validation was run
