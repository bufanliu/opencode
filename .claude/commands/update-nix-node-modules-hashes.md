---
name: update-nix-node-modules-hashes
description: Workflow command scaffold for update-nix-node-modules-hashes in opencode.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /update-nix-node-modules-hashes

Use this workflow when working on **update-nix-node-modules-hashes** in `opencode`.

## Goal

Keeps the Nix node_modules hashes up to date for reproducible builds.

## Common Files

- `nix/hashes.json`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update or regenerate nix/hashes.json
- Commit the updated hashes file

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.