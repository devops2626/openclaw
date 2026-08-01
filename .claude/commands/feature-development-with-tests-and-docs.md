---
name: feature-development-with-tests-and-docs
description: Workflow command scaffold for feature-development-with-tests-and-docs in openclaw.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-development-with-tests-and-docs

Use this workflow when working on **feature-development-with-tests-and-docs** in `openclaw`.

## Goal

Implements a new feature or enhancement, accompanied by relevant tests and documentation updates.

## Common Files

- `src/**/*.ts`
- `extensions/**/*.ts`
- `apps/**/*.swift`
- `apps/**/*.kt`
- `docs/**/*.md`
- `src/**/*.test.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Implement or modify feature logic in main source files.
- Add or update corresponding test files (often *.test.ts or *.test.swift).
- Update or add relevant documentation files (docs/*.md).

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.