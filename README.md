# AgenticExercise

Portable programming-practice tutoring skill for Claude Code and Codex. Learner writes code, tests, dependencies, and fixes; agent offers bounded exercises, requested hints, evidence-based review, and progress records. No app, API subscription integration, custom runtime, installer script, or required Superpowers dependency.

**Status: draft, not behaviorally validated.** Structural checks do not prove coaching compliance. Programming is intended first-release scope; neither host discovery nor arbitrary-domain assessment has been smoke-tested. See [test results](tests/RESULTS.md) and [scenarios](tests/scenarios.md).

## Install safely

Exact source folder: `skills/agenticexercise/`, including `SKILL.md` and `references/`. Copy only that folder to one selected destination:

| Host | Project-local destination | Personal destination | Invocation |
| --- | --- | --- | --- |
| Claude Code | `.claude/skills/agenticexercise/` | `~/.claude/skills/agenticexercise/` | `/agenticexercise` |
| Codex | `.agents/skills/agenticexercise/` | `~/.agents/skills/agenticexercise/` | `/skills`, or type `$` and select `agenticexercise` |

Project-local paths are relative to intended learner project, not necessarily this repository. Codex scans `.agents/skills` from current directory up to repository root. Avoid duplicate copies in multiple scopes. Do not put personal learner state inside installation directory. Personal installations affect more than one project; choose that scope deliberately.

Give installer agent this prompt, replacing placeholder with actual repository URL. URL alone is not installation permission:

> Inspect repository at `<REPOSITORY_URL>` for AgenticExercise. Fetch into a new empty temporary directory. Read source before installing. Do not execute downloaded scripts, hooks, or build tools. Exact source is `skills/agenticexercise/`; inspect its whole contents, symlinks, and destination before copying. Ask which host and project-local or personal scope I want, then show resolved destination for approval. Reject source symlinks or paths escaping inspected folder. Do not follow destination symlinks or overwrite an existing installation without showing changes and obtaining separate approval. Copy only inspected skill folder; no repository configuration or learner records. Do not commit, publish, or transfer learner code. Keep learner workspace separate and unchanged. Report copied files and checks actually performed; do not claim host discovery passed unless observed.

No repository owner, hosted URL, or license grant is supplied here. Obtain source URL and usage permission from repository owner.

## Start practice

In Claude Code, invoke `/agenticexercise` and describe goals. In Codex, use `/skills` or `$agenticexercise`. Codex detects newly installed skills automatically; restart if missing. If Claude Code does not show skill, start a new session and check destination and `SKILL.md`.

Skill interviews one question at a time, proposes setup, then waits for approval. Confirm separate learner workspace before state creation. Proposed reward defaults: 100 XP per reviewed completion and 25 XP per independently verified delayed skill revisit, with stable once-only keys. XP never proves mastery.

Learner workspace holds `LEARNING.md`, `PROGRESS.md`, `REPORT.md`, and per-exercise briefs/review history. No personal goals, submissions, or progress belong in distributed package. Conceptual explanations and requested small hints stay within tutoring boundaries. Solutions or code edits require warning plus separate scoped confirmation; exposure stays labeled.

Manual fallback when discovery is unavailable: ask host to read `skills/agenticexercise/SKILL.md` plus its linked references from inspected local source and follow them for this session. This is manual instruction loading, not verified native integration or a guarantee that host honors policy.

## Update

Inspect fresh source in a new empty directory; compare installed folder before touching it. Show additions, changes, deletions, and resolved destination; require approval before replacement. Replace only approved policy files, handling removed files explicitly rather than blindly merging stale references. Preserve old installation until new copy succeeds; report partial failures. Never change separate learner workspace, import someone else's records, or execute downloaded update scripts. Verify links after copy. Stop on unexpected symlinks or unrelated destination content. No real installation is performed by this repository's checks.

## Validate locally

From repository root:

```sh
python3 -I tests/check_skill.py
git diff --check
```

Checker uses Python standard library. Checks required files, simple metadata, relative inline Markdown links, reference routing, core word budget, machine-local paths, and unwanted authoring dependency references. Temporary negative fixtures verify missing reference and wrong metadata rejection. It does **not** test tutoring behavior, assess learner submissions, prove host discovery, or certify safe installs. `git diff --check` excludes untracked files; inspect those separately before committing.

## Documentation checked 2026-11-01

- [Claude Code skills](https://code.claude.com/docs/en/skills): project/personal paths and slash invocation. This package supplies both `name` and `description`, although Claude Code permits their omission.
- [Codex skills entry](https://developers.openai.com/codex/skills/), redirected to [Build skills](https://learn.chatgpt.com/docs/build-skills): `.agents/skills` paths, `/skills` and `$` invocation, required `name`/`description`, automatic detection with restart fallback.

Documentation checks are not host smoke tests. Behavior can vary with host version, higher-priority instructions, and model. Review limitations before relying on draft for independent-practice enforcement.
