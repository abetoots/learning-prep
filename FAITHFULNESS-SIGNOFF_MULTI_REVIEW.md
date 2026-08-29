# Faithfulness sign-off — `interview-prep/` against `LEARNING-SYSTEM.md`

**Date:** 2026-08-29 · **Panel:** Claude Fable 5 (lead) · GPT-5.2/Codex (fresh session) · Gemini 3.1 Pro High (Antigravity) · **Rounds:** one independent round each; no debate round needed.

**Question put to the panel:** after the simplicity pass and the extraction of the readiness rubric into `competency-list.md`, is the package still a faithful Track A instantiation of the framework? Specifically: (1) competency list as its own file with week 1 / week 6 score columns; (2) the §3.2 prerequisite sketch deliberately omitted; (3) did the simplification lose anything the framework requires?

## Executive summary

**Signed off, with one fix applied.** Both external legs signed off on both design decisions and found nothing lost in the simplification — Antigravity added that reducing the five-axis tag to one cold mark *increased* §10 faithfulness. All three reviewers independently found the same pre-existing gap, and it is a real one: framework §8 says to count each AI request *as you make it* because "a log fires when something goes wrong, and asking immediately means nothing does." The package's AI column lived in an error log whose only triggers were a miss or a >10-minute stall, so the over-reliance it exists to catch could never produce a row. Fixed with a third trigger — the same fix `web-engineer-prep/error-log.md` already had.

## Consensus findings

| # | Finding | Lead | Codex | Antigravity | Action |
|---|---|---|---|---|---|
| 1 | `competency-list.md` as a file with score columns satisfies §3.1 better than the embedded rubric did | ✔ | sign off | sign off | — |
| 2 | Omitting the §3.2 sketch is correct for Track A; the recorded fallback trigger ("repeatedly blocked by fundamentals → build it") is the check | ✔ | sign off, conditional on the cold-gate actually being run | sign off | — |
| 3 | Simplification lost nothing the framework requires (moved rationale, five-axis → one mark, rubric extraction all checked) | ✔ | nothing found | nothing found | — |
| 4 | **§8 one-metric violation:** AI use only logged when a row fires on a miss/stall; the request that leaves no trace is never counted | medium, pre-existing | falsifier | falsifier — "NOT faithful" | **Fixed:** `error-log.md` now has three triggers; #3 is "you used AI at all, even if nothing went wrong" |
| 5 | §5 Track A (start at retrieve), §5 Track B pockets (worked example → completion → blank), §6 spacing, §9 calibration, §10 mixed-track row, §11 guardrail — all located in the package | ✔ | ✔ | ✔ | — |

## Debated items

| Claim | Codex | Antigravity | Lead | Resolution |
|---|---|---|---|---|
| §8's monthly AI-disabled self-test is not named as such — the AI-disabled mocks exist but the "if performance collapses, cut back to critique-only" rule isn't stated | missing as a named cadence | satisfied | satisfied | **Codex's reading adopted** — one clause added: the mocks are the self-test, and a collapsed mock means critique-only until it recovers. Both readings are now true. |
| Week 4's gap topics (consistent hashing, sharding, cache invalidation, consensus) are the only material the learner never built — §3.2's "skipping" failure can bite there | not raised | not raised | low, lead-unique | **Applied on the casting vote:** one sentence in Week 4 — name what each topic assumes you already have; a missing assumption is the first 20 of the 70 minutes. It's §3.2 applied per item, same shape as the cold-gate, and changes what the learner does that day. Recorded as lead-only. |

No item stayed divergent; nothing escalated.

## Falsifiers offered

- **Antigravity:** the §8 metric as implemented — a column in a log that only fires on failure — silently drops the exact behaviour it was built to catch. *(Accepted; fixed.)*
- **Codex:** same gap; plus, the §3.2 omission is wrong the moment repeated `never-encoded` fundamentals show up across categories — restore the sketch for those items. *(Accepted; matches the recorded trigger.)*
- **Lead:** the §3.2 omission is wrong if Week 4 gap-topic rows pile up with "I didn't have the foundation" as the why. *(Pre-empted by the Week 4 line.)*

## Provenance

| Leg | Read in full | From general knowledge |
|---|---|---|
| Claude (lead) | All 8 package files; framework §2, §3, §5, §8, §10, §11 (§0–§1 and TOC earlier in session). Analysis written to scratchpad before reading either leg. | — |
| Codex | All 8 package files (listed via `rg`); framework §0–§3, §5, §6, §8–§11, §13 | "No general-knowledge basis" |
| Antigravity | All 8 package files; framework §0–§3, §5, §6, §8, §9, §10, §11, §13 | "Answered purely from the provided text" |

No bare approvals in any round. No `bare-GO` or `stale-context` logged.

## Actionable recommendations

All applied:

1. `interview-prep/error-log.md` — three row triggers (wrong / stuck >10 min / used AI at all); the mocks named as the §8 self-test with the cut-back rule.
2. `interview-prep/study-plan.md` — Week 4 prerequisite line on the gap topics.
3. `interview-prep/CHANGELOG.md` — sign-off outcome recorded under the 2026-08-29 follow-up.

Readability guards re-run after the fixes: study-plan path FK 7.7 / p90 28 (unchanged), error-log 7.0 / 25 (was 6.0 / 28 — the new numbered triggers add three short sentences), competency-list 5.4 / 21.

Not applied, by design: the prerequisite sketch stays out as a standing artifact; the framework's literal "starting set of three" is met in substance by the cold-gate's per-item re-encoding for Track B pockets and the Week 4 line, and the package records the trigger that would bring the sketch back.
