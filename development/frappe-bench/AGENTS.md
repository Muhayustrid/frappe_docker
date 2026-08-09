# Frappe Bench Rules

This file contains bench-wide rules for `/Users/rotiropi/DockerERPNext/frappe_docker/development/frappe-bench`.

## Scope and Precedence

- This bench contains Frappe, ERPNext, `bakery_manufacturing`, and `roti_ropi_pos`.
- Read the nearest applicable nested `AGENTS.md` before changing an app.
- Repository-specific nested `AGENTS.md` files refine or override these bench-wide instructions within their own scope.
- `apps/bakery_manufacturing/AGENTS.md` governs bakery app work.
- `apps/roti_ropi_pos/AGENTS.md` governs Mobile POS backend work.
- Android is maintained separately under `/Users/rotiropi/DockerERPNext/POSERPNext` and follows its own `AGENTS.md`; it does not inherit this file.

## Core and Ownership Boundaries

- Never directly edit files under `apps/frappe` or `apps/erpnext`.
- Inspect installed Frappe and ERPNext source before relying on a core method, field, hook, permission, controller, cache behavior, or side effect.
- `bakery_manufacturing` owns manufacturing, batch/UOM behavior, Price Group, and existing legacy ERPNext POS customization.
- `roti_ropi_pos` owns the versioned Mobile POS backend.
- Do not move responsibilities between repositories or apps without explicit user approval.

## Communication and Change Control

- Communicate with the user in Indonesian.
- Write repository Markdown, code comments, technical documentation, test names, and commit messages in English.
- Do not commit, push, publish, deploy, reset, clean, stash, migrate production, or begin a later implementation phase without explicit user approval.
- Do not revert or overwrite worktree changes you did not make.
- Do not delete a directory without explicit user approval unless deletion is strictly required for an explicitly requested application objective; inspect it first and state the concrete technical reason before deleting.
- Use the native `EnterWorktree` tool for non-trivial implementation, bug fixes, refactors, and multi-file changes; edit the active checkout directly only for trivial documentation or configuration changes.
- Do not remove a worktree without explicit user approval.

## Frappe Skill and Verification

- Primary Frappe development skill: `/Users/rotiropi/DockerERPNext/ai-skills/frappe/skills/skills/frappe-app-dev/SKILL.md`.
- Reference directory: `/Users/rotiropi/DockerERPNext/ai-skills/frappe/skills/skills/frappe-app-dev/references/`.
- Invoke the installed `frappe-app-dev` skill for Frappe/ERPNext work, then read `existing-app.md` and only the references directly required by the task; do not invoke or load Frappe guidance for unrelated work.
- Before implementing APIs, hooks, DocTypes, permissions, controllers, fixtures, caching, tests, or bench operations, read the relevant reference file. Fixture work commonly requires `hooks.md` and `bench-operations.md`, plus `permissions.md` when applicable.
- Skills are guidance only. They do not override the nearest `AGENTS.md` and do not replace verification against installed Frappe/ERPNext source and executable tests or bench checks.

## Code Navigation

- When a `.codegraph/` index exists, use `codegraph_explore` before grep, find, or manual file reads for code discovery, call paths, and impact analysis.
- Do not use Graphify; verify CodeGraph results against current source and executable tests when correctness matters.
