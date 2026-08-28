# Interview Prep Package — derived from websand-v4

Built 2026-07-08 through multi-model review (Codex, Gemini, Claude) and revised three times since — see [CHANGELOG.md](CHANGELOG.md). External question-bank contents were verified against live pages.

## Files

| File | What it is | Use it for |
|---|---|---|
| [study-plan.md](study-plan.md) | The 6-week plan: budget, week-by-week, weekly review, Anki, where to use external tools instead, readiness rubric | The schedule. Start with "Tonight" at the top |
| [question-bank.md](question-bank.md) | 65 conceptual questions in 8 categories, each with a grounding artifact and answer-key pointers | The core drill: answer aloud, 2–4 min each, per the weekly schedule. First attempt cold |
| [role-and-evidence.md](role-and-evidence.md) | Target role (Senior Backend / Product Platform), the evidence table, the AI-collaboration table, and what's missing for Staff | Positioning, resume framing, the "why not Staff?" answer |
| [external-comparison.md](external-comparison.md) | Repo themes vs 8 verified public banks: covered / missing / better drilled elsewhere | Which tool to use for which topic; the reading list |
| [error-log.md](error-log.md) | Append-only log of every miss, with why, route, and confidence-before | **Write the row before looking up the answer.** Read weekly for patterns |
| [CHANGELOG.md](CHANGELOG.md) | Dated review rounds, what each changed and why, rejected alternatives | History. Not needed to run the plan |

A parked design for a spaced-repetition CLI lives in [`../parked/`](../parked/learn-cli-README-draft.md). It is deferred until the six conditions at the top of that file hold, and it is not part of this package.

## The thesis

The repo's differentiator is correctness engineering — idempotent dispatch, optimistic CAS, recovery philosophy, tenancy invariants, ops discipline — which public banks barely cover. Lead with it in project deep-dives and design discussions. The banks own what the repo can't teach: canonical system-design problems, distributed-systems vocabulary you never needed at single-node scale, and timed algorithms. Those are routed to NeetCode, Anki, Primer and Hello Interview in the study plan, with cadence and pass bars. Aim at Senior Backend / Product Platform roles; the Staff gap list is real and named.

Two later findings shape the package. The target role held up against 2026 market data — don't repackage as "AI Engineer." And the repo was built partly with agentic coding, so every "I designed this" claim is checked cold before it's made. Details in the changelog.

## Maintenance

Re-verify external URLs before a real interview cycle (NeetCode redesigned recently; Hello Interview paths moved). Re-run the readiness rubric after any 2-week break.
