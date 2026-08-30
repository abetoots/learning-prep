# Track-routing retrospective — `interview-prep/` vs `web-engineer-prep/`

**Date:** 2026-08-30 · **Panel:** Claude Fable 5 (lead) · GPT-5.2/Codex (fresh session) · Gemini 3.1 Pro High (Antigravity) · **Rounds:** independent analysis, then one consensus round. All parts conceded by both legs in round 2.

**Owner's hypothesis, as put to the panel:** (a) `interview-prep/` assumes prior knowledge of `LEARNING-SYSTEM.md`, where `web-engineer-prep/` is self-contained on what / why / how / when; (b) the framework prescribes different handling per track and per-item routing for mixed-track material, and `interview-prep/` detects Track B pockets (the cold-gate's `blank` / `recognizes`) but doesn't route the learner into the Track B system the way the beginner package embodies it.

## Executive summary

**(a) is overstated; (b) is half right, and the half that's right is a real defect.**

The framework does not propose different *systems* per track — §2: "The system is the same for everyone. What differs is where to push first." `web-engineer-prep/` isn't a different system; it's the same three artifacts and the same §5 loop with Track B weight on steps 1–3 and a mentor. And `interview-prep/` *does* route a `blank` item into the Track B method: the cold-gate (added 2026-08-01 for exactly this) sends it to worked example → completion problem → blank attempt → compare, which is §5 Track B steps 3–5. "Doesn't account for that" is wrong.

What all three reviewers found independently is that the routing is **defective in the same three ways**: the blank-page retry happens in the same session as the reread, which §6 says "counts as never" — so the loop never verifies retention; there is no "if still blank" branch; and the completion step is unexecutable for a text ADR unless you're told the §5 trick (ask an AI to hand the ADR back with pieces blanked out). The fix is ~6 lines in Week 1 plus a dated mark in the question bank. No new artifact — the panel rejected the lead's own proposal for a per-item `I can | Proof | Date` table as §11 bureaucracy, and the lead conceded.

On (a): after the readability pass, no framework term on the plan's path is undefined (measured). What remains is that the plan explains the *why* once ("The premise") where the beginner package restates it at every point of use. For a Track A reader that is correct design — §2 says the Track A learner is already competent and the risk is retrieval under pressure, not not-knowing-what-to-do. The one place point-of-use *why* is genuinely missing is the `blank` branch itself, because that is the one moment the reader is a beginner for that item.

## Consensus findings

| # | Finding | Severity | Lead | Codex | Antigravity |
|---|---|---|---|---|---|
| 1 | Hypothesis (a) overstated: operating path is self-contained; explicitness gap is mostly correct Track A design | — | ✔ | ✔ ("partly correct Track A design") | ✔ ("correct: omitting the pedagogical rationale") |
| 2 | Hypothesis (b) half right: the cold-gate routes to the Track B *method*, but the routing is defective | — | ✔ | ✔ ("detected, then remediated with a terse recipe") | ✔ ("its failure isn't that it ignores Track B; it executes it defectively") |
| 3 | **§6 violation:** the `blank` branch's blank-page retry is same-session with the reread; no delayed recall is scheduled. The plan applies this insight to Week 4 ("reconstructing something you read an hour ago mostly tests working memory") but not to its own re-encode loop | High | ✔ | ✔ | ✔ (Blocker 1) |
| 4 | §5 step 1 (a small, concrete target for the item) is not stated at the gate | High | ✔ | ✔ | ✔ |
| 5 | No "if still blank after re-encoding" branch; no §5 step 6 (again, with less help) | Medium | ✔ | ✔ | ✔ |
| 6 | "Partial-completion retry" is unexecutable on a text ADR without the §5 AI prompt ("give it back with a piece removed, no answers") — the beginner package spells this prompt out; the senior one doesn't | Medium | missed | partial ("no concrete source for the completion problem") | ✔ (Blocker 2) |
| 7 | Point-of-use *why* is missing on the completion step — the one place the reader is in Track B mode | Low | ✔ | ✔ | ✔ |

## Debated items

| Claim | Lead (round 1) | Codex | Antigravity | Resolution |
|---|---|---|---|---|
| A per-item `I can… \| Proof \| Date` table for flagged items is required (§5 step 1 + a done-criterion + a place to record the delayed pass) | proposed it | the *function* is required, the *format* isn't — satisfy it inline | the "I can" statement is required; a Proof/Date table is §11 bureaucracy — the beginner's Proof column exists for a hiring-signal reason (`web-engineer-prep/README.md`), not as canonical Track B | **Lead conceded.** The question bank already *is* Track A's per-item competency list: each gate ADR maps to questions whose answer-key pointers are the reference answer (§3.4). The record goes next to the existing cold mark, dated. |
| Does a pre-written question + pointers satisfy §5 step 1 / §3.1, or must the learner write the "I can…" line themselves? | open question | yes for Track A — self-authorship matters in Track B, where small self-set targets build early wins | yes — Track A starts at step 4; §3.1's "write" exists for test-format alignment, which the bank already fixes ("answer out loud, 2–4 min"); ICAP's generate-don't-receive applies to encoding and retrieval, not goal-setting | **Settled: no new "I can" lines.** Codex's caveat kept: the ADR→question mapping must be *stated at the gate*, not left to be inferred from the coverage checklist. |

Round 2: both legs conceded all four parts of the proposed resolution. Nothing escalated.

## Falsifiers offered

- **Codex:** the main defect collapses if Week 1's `blank` items already have a checklist elsewhere that schedules delayed retrieval and names the completion-problem source. *(Checked: none exists — the only downstream reference is `error-log.md`'s `Route` legend, which points back to the same Week 1 loop.)*
- **Antigravity:** none beyond the two blockers; both accepted.
- **Lead:** the per-item table is bureaucracy if the gate flags ≤2 items. *(Moot — the table was dropped regardless; the dated mark costs nothing at any count.)*

## Provenance

| Leg | Read in full | From general knowledge |
|---|---|---|
| Claude (lead) | All 12 package files; framework §2, §3, §5, §6, §8, §10, §11. Analysis written to scratchpad before reading either leg. | — |
| Codex | Every `.md` in both folders; framework §0–§3, §5, §6, §8, §10, §11 | "none material" |
| Antigravity | Framework §0–§6, §8, §10, §11 + Appendix; `study-plan`, `README`, `competency-list`, `error-log` (interview-prep); `README`, `competency-list` (web-engineer-prep) — did not list `question-bank.md`, `role-and-evidence.md`, `external-comparison.md`, `CHANGELOG.md`, `prerequisite-sketch.md`, `error-log.md` (web) as read | "None" |

Antigravity's round-1 read did not include `question-bank.md`; round 2 attached it explicitly and its concession on part 1 (the bank as the per-item competency list) was made with the file in hand. No bare approvals in either round.

## Actionable recommendations (not applied — owner's call)

**1. `study-plan.md`, Week 1 — replace the `blank` line and add the done-rule.** Proposed text:

> - `blank` → re-encode first, ~50 min. Name the question-bank items this ADR answers (0016 → 4.1 / 4.2 / 4.3 / 4.8 · 0013 → 2.1 / 2.2 / 3.7 · 0008 → 1.2 / 1.4 / 3.4 · 0009 → 1.7 / 2.5 / 2.8); their pointers are your reference answer. Reread the ADR. Then ask an AI to hand it back with the mechanism, the failure mode and the rejected alternative blanked out — no answers — and fill them in. Going straight from rereading to a blank page is the cliff people quit at; this is the ramp. Then retry from a blank page, compare, and log.
>
> A blank-page retry twenty minutes after rereading is a comprehension check, not the retrieval that makes it stick. A re-encoded item — `recognizes` or `blank` — is done when a cold pass *opens a later* repo-conceptual session and holds. Date it next to the question's mark: `blank 9/2 → defends 9/4`. Still blank then? `Route = never-encoded` stays, and the next block goes to it before you claim `defends`.

**2. `question-bank.md` header — one clause:** "mark the result next to the question number" → "…and date it; when a re-encoded item later passes cold, add that too (`blank 9/2 → defends 9/4`)."

**3. `study-plan.md`, Week 1 — the budget hole identified 2026-08-30:** "drop [ALT]-table depth first" names a Week 2 cut. Replace with: "If two or more come back blank: skip the baseline pass this week — the gate result is your baseline — write the architecture summary last, from memory, after re-encoding, and move sections 1 and 4 to week 2 in place of the three [ALT] tables."

**4. `CHANGELOG.md`** — one row for this pass, linking here.

Not recommended: a per-item "I can…" table, a Proof column, or restating the framework's rationale throughout — all three reviewers called those §11 bureaucracy for a Track A reader.
