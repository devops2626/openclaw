---
name: api-or-schema-evolution
description: Workflow command scaffold for api-or-schema-evolution in openclaw.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /api-or-schema-evolution

Use this workflow when working on **api-or-schema-evolution** in `openclaw`.

## Goal

Updates or extends protocol schemas, validators, and related registry/types for new or changed API contracts.

## Common Files

- `packages/gateway-protocol/src/schema*.ts`
- `packages/gateway-protocol/src/validator-registry.ts`
- `packages/gateway-protocol/src/schema-export-registry.ts`
- `packages/gateway-protocol/src/schema-modules.ts`
- `packages/gateway-protocol/src/schema-types.ts`
- `packages/gateway-protocol/src/*.test.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Modify or add files under packages/gateway-protocol/src/schema* or similar schema/type files.
- Update validator or registry files to match schema changes.
- Update or add related test files for schema validation.
- Update documentation if public contract changed.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.