# AgenticExercise

Your coding agent coaches you while you write the code.

Practice programming with small, practical exercises chosen for your goals. Get feedback on your work and fix mistakes. You can earn XP and badges for verified accomplishments.

Works with Claude Code and Codex. Exercises follow your goals, with no fixed list or streaks to maintain.

[Install](#install) · [How it works](#how-it-works) · [Rewards](#practice-finish-earn) · [Progress](#progress-that-stays-with-you)

## Practice, finish, earn

| Accomplishment | Reward |
| --- | --- |
| Complete an exercise with verified review | **100 XP** |
| Independently verify a skill again after an agreed delay | **25 XP**, once per skill |
| Reach a milestone | **First Finish**, **Independent Builder**, **Retention Check** |

You approve reward rules during setup. Assisted completions can earn XP, with help recorded. XP tracks completed accomplishments; it does not measure mastery.

## Install

Install either your host's plugin or the standalone fallback below. Installing both loads the coaching instructions twice.

### Claude Code

```sh
claude plugin marketplace add 1001api/AgenticExercise
claude plugin install agenticexercise@agenticexercise-marketplace
```

Start a new session and run:

```text
/agenticexercise:agenticexercise
```

### Codex

```sh
codex plugin marketplace add 1001api/AgenticExercise
codex plugin add agenticexercise@agenticexercise-marketplace
```

Start a new session. Use `/skills` or type `$` and select `agenticexercise`. Use `/plugins` to manage the plugin.

<details>
<summary>Alternate installation and troubleshooting</summary>

#### Install inside Claude Code

```text
/plugin install agenticexercise --marketplace 1001api/AgenticExercise
```

#### Standalone skill

If your Codex CLI does not have `plugin` commands, update it or use this fallback. Choose either the plugin or the standalone skill to avoid loading coaching instructions twice.

Paste the matching prompt into your coding agent:

**Claude Code:**

```text
Install AgenticExercise for Claude Code from https://github.com/1001api/AgenticExercise.git.
Fetch into a new empty temporary directory and inspect skills/agenticexercise/,
including all references. Do not execute downloaded scripts, hooks, or build tools.
Ask whether I want installation in my learner project's .claude/skills/agenticexercise/
or in ~/.claude/skills/agenticexercise/ for all projects. Show the resolved path
for approval, then copy only the inspected skill folder. Reject source symlinks
and escaping paths; do not follow destination symlinks. If already installed,
show differences and ask before replacing anything. Leave repository configuration
and learner records unchanged. Verify copied files and relative links, report
checks actually performed, then tell me how to start with /agenticexercise.
```

**Codex:**

```text
Install AgenticExercise for Codex from https://github.com/1001api/AgenticExercise.git.
Fetch into a new empty temporary directory and inspect skills/agenticexercise/,
including all references. Do not execute downloaded scripts, hooks, or build tools.
Ask whether I want installation in my learner project's .agents/skills/agenticexercise/
or in ~/.agents/skills/agenticexercise/ for all projects. Show the resolved path
for approval, then copy only the inspected skill folder. Reject source symlinks
and escaping paths; do not follow destination symlinks. If already installed,
show differences and ask before replacing anything. Leave repository configuration
and learner records unchanged. Verify copied files and relative links, report
checks actually performed, then tell me how to select agenticexercise with /skills
or by typing $.
```

Use one installation per host. Keep learner records outside the installation directory.

#### Skill not showing up?

Restart your session. Check that the plugin is enabled, or that the standalone installation contains `SKILL.md` and `references/`.

In Claude Code, run `/agenticexercise:agenticexercise` for the plugin or `/agenticexercise` for the standalone skill. In Codex, use `/skills` or type `$` and select `agenticexercise`.

As a session-only fallback, ask your agent to read the inspected `SKILL.md` and its linked references. This does not verify native skill discovery; file checks alone do not establish that your host discovered the skill.

</details>

## Start your first exercise

Once the skill is loaded, tell your agent what you want to practice:

```text
I've relied on AI for too long. Work is faster, but I miss writing code
myself and feel my skills slipping. I want to rebuild my Go skills
and enjoy solving problems again.

I'd like practical problems, starting at medium difficulty, without
taking on a full project. I'll look up documentation, but won't copy
solutions or use AI to write my code. Use this folder as my learner workspace.
```

The coach asks questions one at a time. You approve the setup, reward rules, and learner workspace before it creates records or assigns your first exercise.

## How it works

1. Choose a language or topic, set a time budget, and describe where you get stuck.
2. Get a small problem with clear requirements and completion criteria. The coach leaves the solution to you.
3. Write code and tests. Ask for a small hint when stuck.
4. Request a review and fix issues until the required behavior is verified.
5. Earn approved rewards. The coach uses your history to choose future exercises.

For example, a Go log summarizer exercise asks you to build a CLI with Go's standard library. It reads newline-delimited JSON logs, counts valid and invalid records, and reports the three most frequent error messages. Malformed records are counted and skipped; file and read failures stop the command with a useful error.

You write the code and tests, then explain one error-handling decision during review. The brief specifies the required behavior and completion criteria, leaving implementation choices to you. This example comes from an existing learner exercise; it isn't evidence of a completed review or host behavior test.

<details>
<summary>Hints, reviews, and independent work</summary>

Each brief names the skill, expected effort, input/output examples, allowed resources, constraints, and completion criteria. Exercises can cover languages, tooling, algorithms, practical tasks, or a mix. Looking up documentation is normal.

Ask a conceptual question for an explanation, or request a small hint. The coach should not offer starter code, reference solutions, or pseudocode that gives away the implementation.

If you request a solution, tests, dependency setup, or code edits, the coach explains how that help affects your practice and asks for separate confirmation naming the exercise and scope. Confirmed help is recorded; affected work cannot count as an independent demonstration.

Reviews happen when you ask. The coach checks the brief, submission, earlier attempts, and assistance history using evidence it has permission to access. Findings include concrete failing inputs or states and file/line locations where available. You make fixes unless you separately confirm an exception.

Reviews distinguish observed checks, results you reported, and unverified behavior. Outcomes are `revise`, `complete`, or `complete with revisit scheduled`. Missing required verification keeps a review provisional and prevents final completion. Earlier failures remain linked to their resolutions.

</details>

## Progress that stays with you

The coach chooses exercises based on reviewed work, not your XP total. There is no fixed exercise list to exhaust. You can change languages, topics, or pace without losing earlier progress or repeating full onboarding.

Your report records strengths, gaps, assistance, completed work, and earned rewards. The coach refreshes it after reviewed completion or when you ask.

Unfinished work waits until you return. There are no daily quotas, streaks, or daily logs. Keep your learner workspace separate from the installed skill; it holds your saved progress.

<details>
<summary>Rewards, badges, and evidence rules</summary>

### XP rules

During setup, the coach proposes these version-1 rules for approval. Rewards aren't enabled until you agree.

| Event | XP | Requirements |
| --- | --- | --- |
| Complete an exercise | 100 | A requested review verifies all required criteria. Both `complete` and `complete with revisit scheduled` qualify. Assisted completion also qualifies, with assistance labeled. |
| Verify retention of a named skill | 25 | After an independent demonstration and an agreed delay, another exercise verifies independent use in a meaningfully different context. Awarded once per skill. |
| Submit work, receive `revise`, or receive a provisional review | 0 | An attempt alone earns no completion award. Fixing the exercise can earn completion XP once a review verifies the criteria. |

Completion XP is awarded once per exercise; retention XP once per named skill. Same-context fixes, self-reported results, repeated reviews, and report refreshes earn no extra XP.

### Badges

| Badge | Earned when |
| --- | --- |
| `First Finish` | You complete your first reviewed exercise. Any assistance is labeled. |
| `Independent Builder` | You independently demonstrate an exercise's primary skill: your own work meets verified criteria, and you explain a meaningful decision assessed in that work. |
| `Retention Check` | You pass your first independently verified delayed skill revisit. |

Each badge is awarded once, links to supporting evidence, and adds no bonus XP.

### Example: 225 XP across two exercises

This example uses approved default rules. It isn't an actual learner record.

1. Independently complete your first exercise and explain the assessed decision: 100 XP, `First Finish`, and `Independent Builder`.
2. After an agreed delay, independently complete a different exercise that also verifies retention of that skill: 100 XP + 25 XP, and `Retention Check`.

You now have 225 XP. Another review adds nothing. Revisiting the same skill again earns no further retention XP.

Substantial hints or a solution don't prevent a verified completion from earning 100 XP. Affected skills stay labeled as assisted and need fresh independent evidence before counting as demonstrated or qualifying for a later retention award.

### Reward records

`REPORT.md` holds the XP ledger, total, badges, and evidence links. Each award has a stable ID, rule version, amount, date, evidence link, and assistance label. Corrections preserve the original entry and add a dated adjustment; badge corrections preserve history and mark the badge active or retracted.

You can agree to different reward rules during setup or later. Changes get an explicit rule version and apply going forward, without silently recalculating old awards. There are no mastery levels based on XP.

</details>

<details>
<summary>Learner files and skill assessments</summary>

### Learner workspace

| File | Purpose |
| --- | --- |
| `LEARNING.md` | Approved goals, preferences, time budget, and coaching boundaries. |
| `PROGRESS.md` | Active exercise, next action, assistance summary, and per-skill evidence. |
| `exercises/<numeric-id>-<slug>/BRIEF.md` | Exercise goal, criteria, constraints, and finish line. |
| `exercises/<numeric-id>-<slug>/REVIEW.md` | Dated review attempts, actual checks, findings, assistance, and outcomes. |
| `REPORT.md` | Cumulative strengths, gaps, completed work, awards, and revisit evidence. |

The coach creates records only when there's something to put in them. Ordinary conceptual questions don't require record updates. Back up your workspace before moving it or merging existing learning records. Skill updates should leave that history untouched.

### Skill assessments

The coach adjusts one part of an exercise at a time based on recurring mistakes, your explanations, independently verified work, and later revisits. Completing a task provides evidence for the skills assessed in that task. It does not establish proficiency in an entire topic or language.

| State | What it means |
| --- | --- |
| `unassessed` | No relevant evidence observed. Self-reported experience guides setup only. |
| `practicing` | Relevant attempts, but requirements for independent demonstration aren't met. |
| `demonstrated` | Independently authored work meets verified criteria, and you can explain a meaningful decision assessed in that work. |
| `retention checked` | After an agreed delay, independent work verifies the skill again in a meaningfully different context. |

Substantial hints and solutions receive assistance labels. Affected skills need fresh independent work before counting as demonstrated. Delayed revisits are agreed practice targets, not automatic calendar reminders.

</details>

<details>
<summary>Updates</summary>

For the Claude Code plugin, run `claude plugin update agenticexercise@agenticexercise-marketplace`.

For the Codex plugin, run `codex plugin marketplace upgrade`, then use `/plugins` to inspect and manage available updates.

Restart your session after updating. Maintainers must bump both plugin manifest versions for each release.

For the standalone skill, reuse your host's installation prompt and ask to update the existing installation. Have the agent compare fresh source with installed files and show additions, changes, and deletions for approval before replacement. Stop on unexpected symlinks or unrelated content. Preserve the old installation until replacement succeeds, remove obsolete policy files only with approval, and verify copied files and relative links. Leave learner code and records unchanged; report any partial failure.

</details>

## Things you can ask

After loading the skill, you can make requests in ordinary language. These examples aren't additional slash commands:

```text
Give me one small hint, not a solution.
Review my submission against the exercise brief.
Show my XP total, badges, and the evidence behind each award.
Show which skills I have demonstrated independently and which need work.
Continue my unfinished exercise.
Switch future practice to SQL, but keep my Go history.
Let's agree on a delayed revisit for input validation.
```

## Boundaries and privacy

- AgenticExercise provides coaching instructions. It does not provide a sandbox or separate learning platform. Quality depends on your host and model; learning outcomes aren't guaranteed. The first release focuses on programming.
- Keep host permission controls enabled. Review requests to run commands, install dependencies, access the network, or publish files. The skill asks for approval but cannot enforce those boundaries.
- Your provider may process code and learner records even when files live locally. Check provider data handling and host settings before using sensitive material. Keep credentials out of exercises.

[Coaching rules](skills/agenticexercise/SKILL.md) · [Onboarding](skills/agenticexercise/references/onboarding.md) · [Practice and review](skills/agenticexercise/references/practice.md) · [Progress and rewards](skills/agenticexercise/references/progress.md) · [License](LICENSE)
