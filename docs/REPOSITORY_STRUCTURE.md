# Repository Structure

This repository starts with policy and an empty endpoint stub. Real recipe files should be added only when real MinSpec packages need install-time wiring.

## Current files

```text
.
├── .github/
│   └── CODEOWNERS
├── docs/
│   ├── AGENT_GUARDRAILS.md
│   ├── RECIPE_POLICY.md
│   └── REPOSITORY_STRUCTURE.md
├── .gitignore
├── CONTRIBUTING.md
├── LICENSE
├── README.md
├── SECURITY.md
└── index.json
```

## Future recipe layout

Symfony Flex private/custom recipes commonly use a source layout like:

```text
vendor/
└── package-name/
    └── 1.0/
        ├── manifest.json
        ├── config/
        └── post-install.txt
```

Compiled endpoint files are expected at the repository root, including:

```text
index.json
vendor.package-name.1.0.json
```

For MinSpec packages, future source recipes should normally follow:

```text
minspec/
└── package-name/
    └── 1.0/
        └── manifest.json
```

Do not add empty package directories as placeholders.
