# Recipe Policy

MinSpec recipes are install-time wiring contracts. They are not runtime packages, generators, or starter applications.

## Core rule

A recipe may introduce a package into an application. It must not secretly redesign the application.

## A recipe should be added only when

- the package exists in an official MinSpec source path
- the package has a clear installation contract
- manual installation would otherwise be repetitive or error-prone
- the recipe result can be explained as a small diff
- the recipe can be tested against `minspec/skeleton`

## Recipe boundaries

Recipes may install or update:

- `config/packages/*.yaml`
- `config/routes/*.yaml`
- environment variable templates
- bundle registration through Flex-supported mechanisms
- asset or Stimulus integration when the owning package requires it
- small first-run files needed to make package behavior explicit

Recipes should not contain:

- runtime business logic
- application-specific domain code
- broad UI scaffolds
- hidden generators
- unreviewed scripts
- unrelated package opinions

## Review standard

Each recipe should answer:

1. What package does this introduce?
2. What files does it create or modify?
3. What host assumptions does it make?
4. What is the smallest useful installation behavior?
5. What would surprise a Symfony developer?
6. What would surprise an AI agent reviewing the diff?
7. What validation proves the recipe works?

## Versioning note

Recipe directories and generated recipe files should follow Symfony Flex recipe version conventions. Use major/minor recipe versions such as `1.0`; do not invent patch-level recipe directories unless Symfony Flex policy changes.
