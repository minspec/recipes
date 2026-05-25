# MinSpec Recipes

Symfony Flex recipes and install-time wiring policy for MinSpec-compatible packages.

MinSpec Recipes is the installation automation layer for MinSpec's Symfony reference stack. It defines small, deterministic, reviewable recipes that introduce MinSpec packages into a host application without turning installation into hidden scaffolding or freeform generation.

> Packages provide capability. Recipes introduce capability safely.

---

## Status

**Incubation / no public recipe catalog yet.**

This repository starts as a source-of-truth surface for recipe policy, endpoint shape, and future MinSpec package wiring. Do not add placeholder recipes. A recipe should exist only when there is a real MinSpec package with a real installation contract.

---

## Purpose

A MinSpec-compatible package should focus on what it provides at runtime.

A MinSpec recipe should focus on how that package is introduced into an application.

This separation keeps responsibilities clear:

- package repositories hold runtime code
- this repository holds install-time wiring
- `minspec/skeleton` defines the starting baseline
- applications compose only the capabilities they choose

Recipes are not marketing demos, starter applications, or hidden generators. They are small, inspectable installation actions.

---

## Current Endpoint Stub

This repository includes an empty `index.json` so the endpoint contract can be reviewed before recipes exist.

Future MinSpec applications may opt into this endpoint with Composer/Symfony Flex configuration similar to:

```json
{
  "extra": {
    "symfony": {
      "endpoint": [
        "https://api.github.com/repos/minspec/recipes/contents/index.json",
        "flex://defaults"
      ]
    }
  }
}
```

Do not add this to `minspec/skeleton` until there is a real reason to use the endpoint.

---

## Design Principles

### 1. Deterministic installation

Installing the same package into the same baseline should produce the same recipe result every time.

### 2. Minimal host assumptions

Recipes should assume only the canonical MinSpec skeleton and explicit Composer dependencies.

### 3. Explicit composition

Recipes may wire required integration points, but they must not silently reshape the host application.

### 4. Symfony-native behavior

Recipes should follow Symfony Flex conventions and remain understandable to Symfony developers.

### 5. Reviewable diffs

Every recipe must be small enough for a maintainer to inspect and explain.

### 6. Agent-safe boundaries

AI tools may inspect, explain, draft, and test recipes, but they must not become authority for package introduction or source policy.

---

## What Belongs Here

- Symfony Flex recipe manifests
- recipe endpoint index data
- install-time configuration files copied by recipes
- recipe policy and review standards
- recipe validation notes and release checklists

## What Does Not Belong Here

- runtime package code
- full starter applications
- business logic
- generated application scaffolds
- unreviewed AI-generated code
- third-party code snippets
- hidden mutation scripts

---

## First Real Recipe Candidate

The first real recipe should probably be for a small, low-risk MinSpec package whose installation contract is obvious. Do not start with a broad UI/dashboard/auth recipe unless the corresponding package boundaries are already settled.

A good first recipe should prove:

- the endpoint works
- the package-to-recipe boundary is clear
- the recipe is reversible or at least easy to audit
- the generated application diff is understandable
- the workflow can be tested against `minspec/skeleton`

---

## Governance

MinSpec is founder-controlled during incubation. Public visibility does not imply public governance, public write access, or an open contribution process.

Pull requests are enabled but restricted to collaborators only. Only users with repository write, maintain, or admin access may open pull requests.

Collaborator PR access is an operational mechanism for trusted maintainers and approved collaborators. It is not a public contribution path.

Outside questions, issues, reproducible bug reports, documentation clarity suggestions, design feedback, and security reports may be useful where intentionally enabled. Opening an issue or providing feedback does not grant contribution authority, source authority, maintainer status, or approval to submit code changes.

Unsolicited external PRs are not part of the trusted source path during incubation.

AI agents, GitHub Apps, bots, automation, Dependabot, Copilot agents, browser agents, and external tools are not maintainers and do not gain source authority from collaborator-only PR settings.

See `CONTRIBUTING.md`, `SECURITY.md`, and `docs/AGENT_GUARDRAILS.md`.

---

## License

Apache-2.0. See `LICENSE`.
