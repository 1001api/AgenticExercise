# AgenticExercise

A long-term programming practice game for Claude Code or Codex. Choose what you want to learn, work through exercises at your own pace, and earn XP and badges for reviewed accomplishments.

You write the code and tests, then fix issues found in review. The coach keeps your history in a separate learner workspace and uses it to choose future exercises. Over weeks and months, your report shows what you've completed, where you've improved, and what still needs practice.

## The long game

The goal is to build or rebuild independent programming skill through practice you enjoy returning to. Following someone else's code and writing a program yourself ask different things of you. The agent coaches while you write, test, and fix your work. Looking up documentation is normal; you don't have to memorize every API.

Your learner workspace is your save. Each exercise ends, and you carry your work, XP, and reviews into the next one. You can practice one language for months or change direction without losing that history.

### A small problem worth finishing

Exercises are focused, practical tasks sized to your available time. You might write a log summarizer or repair an existing component. Each brief specifies behavior you can check and where the task ends. You decide how to build it.

Finish the task, request a review, and make any needed fixes before moving on. Later exercises can reuse an idea without making you maintain or keep expanding every earlier program.

### Infinite replayability

There is no fixed exercise list to exhaust. The coach chooses each new brief from your goals and past reviews. A recurring mistake can become a practice target. A skill you handled well can return later in a different context to check whether it stuck.

Replays give you a different decision to work through. After summarizing valid records, you might handle malformed records under a policy that requires rejecting the input or skipping and reporting bad rows. A later task could revisit aggregation with persistent data or changed ordering requirements. Renaming inputs or adding unrelated features wouldn't provide that practice.

Difficulty follows reviewed evidence of what you can do independently. A new topic can start small even when you've completed many exercises or earned a large XP total.

### Rewards and a report that grows with you

Once you approve reward rules, reviewed completions earn XP. Independently verified delayed revisits can earn retention XP, and badges mark specific milestones.

Your first report may describe one narrow success, with most skills still unassessed. As you complete more reviewed work, it can identify recurring difficulties and show where later attempts resolved them. Delayed revisits add evidence of what you can still do after time away. The report also records help you received, so you can distinguish completed practice from independent work.

Your XP total gives you a record of accomplishments. Linked reviews show what you did and what was verified. XP alone doesn't establish mastery; refreshing the report adds no new evidence or duplicate rewards.

### A habit without streak pressure

You might aim for one exercise a day. If a problem takes longer or you need a break, unfinished work waits for your next session. There are no daily quotas or streaks to protect, and you don't need to keep a daily log. The coach maintains progress records and refreshes your cumulative report after reviewed completion or when you ask.

## Install and start

### Claude Code plugin

Run in your terminal:

```sh
claude plugin marketplace add 1001api/AgenticExercise
claude plugin install agenticexercise@agenticexercise-marketplace
```

Start a new session and run `/agenticexercise:agenticexercise`.

Or install inside Claude Code:

```text
/plugin install agenticexercise --marketplace 1001api/AgenticExercise
```

### Codex plugin

Run in your terminal:

```sh
codex plugin marketplace add 1001api/AgenticExercise
codex plugin add agenticexercise@agenticexercise-marketplace
```

Start a new session, then use `/skills` or type `$` and select `agenticexercise`. Use `/plugins` to manage the plugin interactively. If your CLI does not have `plugin` commands, update it or use the standalone-skill fallback below.

### Standalone-skill fallback

Choose either the plugin or the standalone skill to avoid loading the coaching instructions twice. For the standalone skill, paste the matching prompt into your coding agent and let it handle installation.

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

Use one installation per host. Keep learner records outside the installation directory. File checks alone do not establish that your host discovered the skill.

### Start practicing

In Claude Code, run `/agenticexercise:agenticexercise` for the plugin or `/agenticexercise` for the standalone skill. In Codex, use `/skills` or type `$` and select `agenticexercise`. If missing, restart your session and check that the plugin is enabled, or that the standalone installation contains `SKILL.md` and `references/`. As a session-only fallback, ask your agent to read the inspected `SKILL.md` and its linked references; this does not verify native skill discovery.

Once the skill is loaded, describe what you want to practice:

```text
I want to practice Python input validation. I'd like to aim for one exercise
a day, around 30 minutes each, and keep going over the coming months.
I usually get stuck deciding what should happen with bad input.
```

The coach asks questions one at a time, then proposes a setup, including reward rules, for your approval. You'll confirm the learner workspace before it creates records or assigns your first exercise.

### Updates

For the Claude Code plugin, run `claude plugin update agenticexercise@agenticexercise-marketplace`. For Codex, run `codex plugin marketplace upgrade`, then use `/plugins` to inspect and manage available updates. Restart your session after updating. Maintainers must bump both plugin manifest versions for each release.

For a standalone skill, reuse your host's installation prompt and ask to update the existing installation. Have the agent compare fresh source with installed files and show additions, changes, and deletions for approval before replacement. Stop on unexpected symlinks or unrelated content. Preserve the old installation until replacement succeeds, remove obsolete policy files only with approval, and verify copied files and relative links. Leave learner code and records unchanged; report any partial failure.

Host discovery and coaching behavior have not been smoke-tested. File and link checks do not validate coaching behavior or certify safe installation.

## What practice looks like

For example, suppose you want to practice Python input validation in 30-minute sessions. This is a sample session, not a recorded test result.

1. The coach asks about your goals, experience, sticking points, time, and preferences, one question at a time. You approve the proposed setup and confirm where learner files should live.
2. You get an exercise: read an expense CSV and summarize totals by category. The brief spells out expected behavior, how to handle malformed input, constraints, and what counts as finished. It leaves the implementation to you.
3. You write code and tests. If you ask for a hint, the coach gives one small pointer or diagnostic question, then waits for your attempt.
4. You request a review. The coach checks your submission against the brief using evidence it has permission to access. It might point out a row that crashes the parser and where the failure occurs. You write the fix.
5. If required behavior hasn't been verified, the review stays provisional. Once the required criteria are verified, the exercise can be marked complete, with any assistance recorded. Those findings inform later exercises. You can also agree on a delayed revisit to check whether you can apply the skill independently in another context.

After completion, the coach updates your report with the exercise and any earned rewards. Your next exercise draws on that history. If you stop partway through, the coach resumes unfinished work next session unless you choose to pause it or change direction.

## How coaching works

### Exercises with a finish line

Each exercise names the skill you'll practice, how much effort to expect, and what you need to show to finish. The brief includes relevant input/output examples, allowed resources, and work outside its scope. Your reported experience and available time guide the first exercises; reviewed work guides later ones.

Practice can cover languages, tooling, algorithms, practical tasks, or a mix. You can change goals, pace, or topic without going through the full onboarding again. Earlier attempts and progress stay in your records.

### Help when you ask

Ask a conceptual question for an explanation, or request a small hint when you're stuck. The coach should not offer starter code, reference solutions, or pseudocode that gives away the implementation.

If you ask for a solution, tests, dependency setup, or edits to your code, the coach explains how that help affects your practice. It then asks for separate confirmation that names the exercise and scope. Confirmed help goes in your records, and the affected work cannot count as an independent demonstration.

### Review you can act on

Reviews happen when you ask. The coach reads the brief, your submission, earlier attempts, and assistance history. It reports defects with concrete failing inputs or states and file/line locations where available. You make the fixes unless you separately confirm an exception.

The review distinguishes checks the coach observed, results you reported, and behavior that remains unverified. Outcomes are `revise`, `complete`, or `complete with revisit scheduled`. Missing required verification prevents final completion. Earlier failures stay in the history, linked to their resolutions.

## How practice follows your progress

The coach adjusts one part of an exercise at a time based on mistakes that recur, your explanations, work you've completed independently and verified, and later revisits. Completing a task provides evidence for the skills assessed in it, not an entire topic or language.

Each skill has its own state:

| State | What it means |
| --- | --- |
| `unassessed` | No relevant evidence has been observed yet. Self-reported experience guides setup only. |
| `practicing` | You've made relevant attempts but haven't met the requirements for independent demonstration. |
| `demonstrated` | Work you authored independently meets verified criteria, and you can explain a meaningful decision assessed in that work. |
| `retention checked` | After an agreed delay, independent work verifies the skill again in a meaningfully different context. |

Substantial hints and solutions receive assistance labels. You'll need fresh independent work before an affected skill can count as demonstrated. Delayed revisits are practice targets you agree to, not automatic calendar reminders.

## Progress across sessions

Your learner workspace holds approved goals, the current exercise, your next action, review history, strengths, gaps, and revisit targets. Ask for a progress report to see the evidence and assistance labels behind the assessments.

| File | Purpose |
| --- | --- |
| `LEARNING.md` | Approved goals, preferences, time budget, and coaching boundaries. |
| `PROGRESS.md` | Active exercise, next action, assistance summary, and per-skill evidence. |
| `exercises/<numeric-id>-<slug>/BRIEF.md` | Exercise goal, criteria, constraints, and finish line. |
| `exercises/<numeric-id>-<slug>/REVIEW.md` | Dated review attempts, actual checks, findings, assistance, and outcomes. |
| `REPORT.md` | Cumulative strengths, gaps, completed work, awards, and revisit evidence. |

The coach creates records only when there's something to put in them. Reports refresh after reviewed completion or when you ask. Ordinary conceptual questions don't require updates to your records.

## XP and rewards

You earn XP for completed practice and verified retention, and badges for specific milestones. The coach chooses harder exercises based on evidence of what you can do independently. A high XP total alone doesn't establish mastery.

During setup, the coach proposes the following version-1 rules for your approval. Rewards aren't enabled until you agree to them.

### How you earn XP

| Event | XP | Requirements |
| --- | --- | --- |
| Complete an exercise | 100 | A requested review verifies all required criteria. Both `complete` and `complete with revisit scheduled` qualify. Assisted completion also qualifies, with assistance labeled. |
| Verify retention of a named skill | 25 | After an independent demonstration and an agreed delay, another exercise verifies independent use in a meaningfully different context. Awarded once per skill. |
| Submit work, receive `revise`, or receive a provisional review | 0 | An attempt alone earns no completion award. Fixing the same exercise can earn its completion XP once a review verifies the criteria. |

You earn completion XP once per exercise and retention XP once per named skill. Same-context fixes, self-reported results, and repeated reviews earn no extra XP.

### Badges and their requirements

| Badge | Earned when |
| --- | --- |
| `First Finish` | You complete your first reviewed exercise. Any assistance is labeled. |
| `Independent Builder` | You independently demonstrate an exercise's primary skill: your own work meets verified criteria, and you explain a meaningful decision assessed in that work. |
| `Retention Check` | You pass your first independently verified delayed skill revisit. |

Each badge is awarded once and links to supporting evidence. Badges don't add bonus XP.

### Example: 225 XP across two exercises

This example uses approved default rules. It isn't an actual learner record.

1. You independently complete your first exercise and explain the assessed decision. You earn 100 XP, `First Finish`, and `Independent Builder`.
2. After an agreed delay, you independently complete a different exercise that also verifies retention of that previously demonstrated skill. You earn 100 XP for completion, 25 XP for the skill revisit, and `Retention Check`.
3. Your total is 225 XP. Another review of either exercise adds nothing. Revisiting the same skill again earns no further retention XP.

If you need substantial hints or a solution, a verified completion can still earn 100 XP. Affected skills remain labeled as assisted. They need fresh independent evidence before they can count as demonstrated or qualify for a later retention award.

### Where rewards live

`REPORT.md` holds your XP ledger, total, badges, and evidence links. The coach refreshes it after reviewed completion or when you explicitly request a report. For example:

```text
Show my XP total, badges, and the evidence behind each award.
```

Each XP award has a stable ID, rule version, amount, date, evidence link, and assistance label. Repeated reviews and report refreshes cannot duplicate awards. Corrections keep the original entry and add a dated adjustment. Badge corrections also preserve history and mark the badge as active or retracted.

You can agree to different reward rules during setup or later. Changes get an explicit rule version and apply going forward; they don't silently recalculate old awards. There are no streaks, daily quotas, or mastery levels based on XP.

## Things you can ask

Use ordinary language after loading the skill. These are example requests, not additional slash commands:

```text
Give me one small hint, not a solution.
Explain what makes a test case a boundary case.
Review my submission against the exercise brief.
Show which skills I have demonstrated independently and which need work.
Continue my unfinished exercise.
Switch future practice to SQL, but keep my Python history.
Let's agree on a delayed revisit for input validation.
```

## Limits and privacy

- AgenticExercise is a set of coaching instructions for your coding agent. It provides no sandbox or separate learning platform. Coaching quality depends on your host and model, and learning outcomes aren't guaranteed. The first release focuses on programming.
- Before installing, review the skill files and [license](LICENSE). Choose either the plugin or the standalone skill for your host to avoid loading duplicate instructions. Installation and coaching behavior haven't been smoke-tested on either host.
- Keep exercises and progress in a learner workspace outside the installed skill folder. Back it up before moving it or merging existing learning records. Skill updates should leave that history untouched.
- Keep your host's permission controls enabled. Review requests to run commands, install dependencies, access the network, or publish files. The skill asks the agent to seek approval but cannot enforce those boundaries.
- Your provider may process code and learner records even when the files live locally. Check the provider's data handling and your host settings before using sensitive code or personal information. Keep credentials out of practice material.
- Source repository: [1001api/AgenticExercise](https://github.com/1001api/AgenticExercise).

## Read the coaching rules

See [`SKILL.md`](skills/agenticexercise/SKILL.md) for the coaching instructions and links to [onboarding](skills/agenticexercise/references/onboarding.md), [practice and review](skills/agenticexercise/references/practice.md), and [progress and rewards](skills/agenticexercise/references/progress.md). These rules describe how the coach should behave. The examples above are not evidence that either host has passed behavioral tests.
