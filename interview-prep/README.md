# Interview Prep Package — derived from websand-v4

Built 2026-07-08 via a multi-model workflow: Codex defined acceptance criteria against the repo before drafting; external question-bank contents were verified against live pages; the final package was iterated with Codex until sign-off.

## Files

| File | What it is | Use it for |
|---|---|---|
| [role-and-evidence.md](role-and-evidence.md) | Target role (Senior Backend / Product Platform), the evidence table proving it, and the honest what's-missing-for-Staff list | Positioning, resume/profile framing, the "why not Staff?" answer |
| [question-bank.md](question-bank.md) | ~66 conceptual questions in 8 interview categories, tagged (defend-your-design / what-breaks-if / alternatives), each with grounding artifact + answer-key pointers | The core drill: answer aloud, 2–4 min each, per the weekly schedule |
| [external-comparison.md](external-comparison.md) | Repo themes vs 8 verified public banks (Primer, Hello Interview, ByteByteGo, Tech Interview Handbook, NeetCode, HackerRank, interviewing.io, StaffEng): covered / missing / better-drilled-elsewhere | Deciding *which tool* to use for each topic; the reading list |
| [study-plan.md](study-plan.md) | 6-week plan (~11 hrs/wk, ≈67h; a reduced ~9 hrs/wk variant is included): repo-conceptual + standardized-drill + simulation streams, weekly checkpoints, Anki protocol, honest LeetCode/Anki routing, readiness rubric | The actual schedule; read the rubric in week 0, score it in weeks 1 and 6 before booking real loops |
| [error-log.md](error-log.md) | Append-only log of every miss, with a mandatory *why* column and a confidence-before rating | **Write the row before looking up the answer.** Read it weekly for *patterns*, not entries — that's where next week's syllabus comes from |
| [learn-cli-README-draft.md](learn-cli-README-draft.md) | Design doc for a spaced-repetition CLI over your own codebase docs. **Status: DEFERRED** | Parked, not active. Six-condition build trigger is at the top of the file — don't start it until all six hold |

## The one-paragraph thesis

The repo's differentiator is correctness engineering — idempotent dispatch, optimistic CAS, recovery philosophy, tenancy invariants, ops discipline — which public banks barely cover; lead with it in project deep-dives and design discussions. The banks own what the repo can't teach: canonical system-design problems, distributed-vocabulary you never needed at single-node scale, and timed algorithms — those are routed to NeetCode/Anki/Primer/Hello Interview in the study plan, with cadence and pass bars. Aim at Senior Backend/Product Platform roles; the Staff gap list is real and named.

## 2026-07-22 — AI-era second pass

A multi-model panel re-examined the target role against live 2026 market data ([`../ROLES-AND-DELIVERABLES_MULTI_REVIEW.md`](../ROLES-AND-DELIVERABLES_MULTI_REVIEW.md)). **The role held** — software engineering is resilient at the category level, seniority is the strongest protective factor in the data, and backend complexity is valued while frontend commoditizes. The market moved toward this package's differentiator, not away from it. Do **not** repackage as "AI Engineer": ML postings are genuinely up ~40%, but there are no evidence rows here for modeling work.

One real gap was found and closed: **AI-collaboration fluency**, which 2026 senior loops probe directly and this package trained nothing for. It now has an evidence table in `role-and-evidence.md`, a review round in week 4, two STAR skeletons in week 5, and a rubric row.

## 2026-08-01 — agentic-coding ownership gap

The package assumed websand-v4 was entirely hand-written; agentic coding broke that for an unknown slice of it. Two-stage multi-model fix: [`../PLAN-SIGNOFF_MULTI_REVIEW.md`](../PLAN-SIGNOFF_MULTI_REVIEW.md) (plan sign-off) then [`../AI-OWNERSHIP-GAP_MULTI_REVIEW.md`](../AI-OWNERSHIP-GAP_MULTI_REVIEW.md) (mechanism design + Stage 3 re-review). Adds a Week 1 ownership cold-gate (present-tense blank-page check, never a memory judgment) that routes each item to Track A or a time-boxed Track B re-encoding loop, a four-axis self-tag on `role-and-evidence.md` rows and every `question-bank.md` item, and a `Route` column in `error-log.md` distinguishing decayed retrieval from material that was never actually encoded. The user's "only the timeline changes" hypothesis was tested and rejected: the interview-claim wording changes too (`[DYD]` downgrades to `[EVAL]`/`[ADOPT]` when the design wasn't actually the user's own), and the fix generalizes upstream into `~/learning-system/LEARNING-SYSTEM.md` (§2, §10) as a "mixed-track" concept, not just this plan.

## Maintenance

Re-verify external URLs before a real interview cycle (NeetCode redesigned recently; Hello Interview paths moved). Re-run the readiness rubric after any 2-week break.
