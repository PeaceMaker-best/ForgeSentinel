---
name: reposteward-maintainer
description: Maintain ForgeSentinel or operate its reviewed Issue-to-PR workflow, including Issue proposals, focused implementation, CI and reviewer follow-up, and cross-harness handoff. Use for ForgeSentinel repository maintenance and ForgeSentinel-managed contributions; do not use it to bypass code-enforced publication, credential, or verification gates.
---

# ForgeSentinel Maintainer

Use this skill for maintenance judgment and handoff. Let ForgeSentinel code own the
state machine, credentials, digests, storage, verification, and GitHub writes.

## Invariants

- Start every code change from a reviewed open Issue. Keep security reports private.
- Work on a dedicated branch or worktree. Never commit or push directly to `main`.
- Keep one PR focused on one Issue and link it with `Closes #<number>`.
- Read the latest remote Issue, PR, review, and CI state before any public write.
- Use the explicit ForgeSentinel review and publication gates; never infer approval.
- Export a Context Pack and Checkpoint before changing account, machine, or harness.
- Never place credentials, local state, harness caches, or target repositories in Git.

For the end-to-end procedure, read [references/lifecycle.md](references/lifecycle.md).
After a managed PR reaches a terminal state, use the `reposteward-branch-cleanup`
skill to plan remote branch cleanup. Its native state machine preserves the
authoritative merge result while recording cleanup intent, reconciliation, and outcome
in a separate append-only audit.
