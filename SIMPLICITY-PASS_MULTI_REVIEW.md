# Simplicity pass on `interview-prep/` — multi-model review

**Date:** 2026-08-29 · **Panel:** Claude Fable 5 (lead) · GPT-5.2/Codex · Gemini 3.1 Pro High (Antigravity) · **Rounds:** independent analysis, then one debate round on the lead's unflagged claims.

**Question put to the panel:** both `interview-prep/` and `web-engineer-prep/` derive from `~/learning-system/LEARNING-SYSTEM.md`. The owner says the senior one feels unnecessarily complex. How much of that is the senior target, and how much is accretion?

## Executive summary

Most of it was accretion, and the cause is structural rather than a matter of taste. `web-engineer-prep/` had a reader who was not its author, so every review round forced a rewrite for that reader, and the mentor's reasoning was explicitly kept out of the beginner's files. `interview-prep/`'s reader *is* its author, who sat in every review round — so each round's reasoning was written into the operating docs "so it doesn't have to be re-derived." The person running the plan isn't re-deriving it. Three review passes layered patches instead of rewriting: one idea from the 2026-08-01 pass ("check cold before you claim you designed it") landed in nine places, including a five-axis tag stamped on all 66 questions.

The senior package *is* legitimately more complex than the beginner one — it trains four interview signals where a course trains one — and all three legs named the same set of things to keep. Everything else moved to a changelog or was cut. Net: 941 → 715 operating lines across the folder (incl. the new changelog), with the question bank losing 66 lines of identical boilerplate and the study plan losing ~90 lines of audit trail.

## Consensus findings (all three legs, independently)

| # | Finding | Severity | Action taken |
|---|---|---|---|
| 1 | Sign-off records (three passes), "Where the framework yields", "The one hour that moved" + rejected alternatives, and ten dated `(added 2026-…)` markers sit inside the operating docs | High | Moved to `interview-prep/CHANGELOG.md`; the three-condition practice-artifact test stays in the plan because the weekly review uses it (Codex's nuance) |
| 2 | 66 identical `Ownership diagnostic: PE=? · ORIG=? · COLD=? · CLAIM=? · ROUTE=?` stub lines in `question-bank.md` | High | Deleted. Replaced by one instruction block: first attempt cold, mark `defends / recognizes / blank` next to the number |
| 3 | PE and ORIG axes are memory self-reports of exactly the kind the same paragraph says are unreliable; the doc itself says only COLD routes | High | Cut. CLAIM survives as the `[DYD]→[EVAL]/[ADOPT]` relabel rule, not a field; ROUTE was derived from COLD |
| 4 | `learn-cli-README-draft.md` (150 lines, DEFERRED) inside the active package, listed in the README file table | High (Codex) / Low (Antigravity) | `git mv` to `../parked/`; README now has a one-line pointer |
| 5 | `role-and-evidence.md` "Ownership tag" column with 11 `*self-tag*` cells | Medium | Column dropped; one sentence keeps the rule ("the claim verb has to survive a cold attempt") |
| 6 | `error-log.md` `Scored` column had no definition anywhere (Codex, unique) | Medium | Defined: hit / partial / miss, or share of pointers hit |
| 7 | Keep: three parallel work types, readiness rubric with pass bars, external routing, confidence-before + scored, the cold-gate concept, the 66 grounded questions | — | Kept |

## Debated items

| Claim (lead's) | Codex | Antigravity | Verdict |
|---|---|---|---|
| A. The 9-hour variant is a second plan embedded in the first; compress to one sentence | Concede | Refute — the "what it costs you" column is the point | **Split → casting vote:** keep the 5-row cost table, drop the two paragraphs around it |
| B. `Route` column duplicates `Why`; drop it | Refute — `Route` decides Anki vs re-encoding, `Why` states the misconception | Refute — same reasoning | **Lead conceded.** `Route` stays; legend tightened |
| C. The cold-gate is the old baseline pass renamed; reduce B-lite/B-full timings + funding rule to two sentences | Partial — the gate runs *before* reading and routes per item, the baseline pass is after and ungraded; but the minute allocations are over-specified and the funding rule is one sentence | Refute on "renamed" — the plan lists them as distinct sequential steps | **Lead was wrong on "renamed"; right on ceremony.** Gate kept as a distinct step; 8/7/7/3 and 15/15/15/5 breakdowns → "~25 min: reread, self-explain, blank retry, compare" and "~50 min: same, with a worked example first"; funding paragraph → one sentence + the 4-hour rubric consequence |
| D. Both rubric caveats are reviewer-facing disclaimers; move to changelog | Concede | Refute — each holds one actionable instruction | **Split → casting vote:** the two actionable sentences stay (one moved into Week 1, one under the rubric); the evidence-strength rationale moved to the changelog |
| E. `external-comparison.md` should be merged into README (Antigravity, round 1) | Keep as reference | Conceded in round 2 — sole home of verified URLs, Week 4 links a specific row, merging bloats the index | **Stays standalone** |

No item stayed divergent after one round, so nothing was escalated.

## Falsifiers offered

- **Lead:** the complexity is justified if the five-axis tags and two-budget arithmetic are consulted during study sessions rather than only during review sessions. Empty error log and every stub still reading `?` four weeks on says they are not.
- **Codex:** justified if the learner actually uses the review-history sections and per-question fields in weekly review to change next week's schedule or claim wording; accretion if read once or skipped.
- **Antigravity:** PE/ORIG tracking is justified only if a present-tense cold attempt can fail to predict understanding — i.e., someone could ace a blank-page reconstruction and still fundamentally misunderstand it because an AI proposed it. Framework §8/§10 make present-tense ability the arbiter, so it isn't.

## Provenance

| Leg | Read in full | Answered from general knowledge | Procedure named |
|---|---|---|---|
| Claude (lead) | All 11 `.md` files in both folders; LEARNING-SYSTEM.md §0–§3 + TOC; ADR directory listing in `~/websand-v4` | — | Independent analysis written to scratchpad before reading either leg |
| Codex | All 11 files; LEARNING-SYSTEM.md §0–§3, §8, §10, §11 | "the YAGNI artifact-review framing" | YAGNI artifact review: does the mechanism change a same-day action, feedback signal, routing decision, or interview claim? |
| Antigravity | All 11 files; LEARNING-SYSTEM.md §0–§3, §8, §10, §11 | — | Manual simplicity/YAGNI review against the framework's §11 |

Neither leg returned a bare approval in either round. No `bare-GO` or `stale-context` verdicts logged.

## Actionable recommendations

All applied in this pass:

1. `interview-prep/README.md` — rewritten as a short index (26 lines); dated sections → changelog; parked CLI gets a one-line pointer.
2. `interview-prep/study-plan.md` — 268 → 178 lines. Premise qualification compressed; budget arithmetic story cut to one sentence; 9-hour table kept, prose trimmed; "hour that moved" removed; Week 0 error-log story cut; Week 1 cold-gate rewritten as a three-mark list; Week 4 cut-note removed; caveats → one actionable line; framework-yields → three-condition practice test + pointer; sign-off record → changelog.
3. `interview-prep/question-bank.md` — 335 → 265 lines. 66 stubs deleted; five-axis legend → one cold-mark block plus the relabel rule.
4. `interview-prep/role-and-evidence.md` — tag column and dated notes removed; ADR count corrected to 22.
5. `interview-prep/error-log.md` — 43 → 27 lines; `Scored` defined; legend tightened; `Route` kept.
6. `interview-prep/CHANGELOG.md` — new; holds all three sign-off records, the framework-alignment audit, rejected alternatives, and this pass.
7. `parked/learn-cli-README-draft.md` — moved out; its relative link to `external-comparison.md` fixed.
8. `interview-prep/external-comparison.md` — unchanged.

Next: a readability pass on every edited file (the owner's step 2).

---

# Readability pass (lead only, after the simplifications)

**Floor reader:** Sam — a senior backend engineer with a comparable side project, handed this folder to run their own 6-week prep. Knows CAS, outbox, idempotency cold; has never read `LEARNING-SYSTEM.md`; never saw a review round. If a section fails for Sam, it fails. (The real reader — the owner, tired, six weeks from now — sits close to Sam on the framework-jargon axis.)

**Reader's path measured:** `study-plan.md` up to "What counts as practice"; `question-bank.md` header only (the questions are drill content, domain-dense by design); the other three files whole. `CHANGELOG.md` is off-path by design and was not reviewed for readability.

## Guards (Flesch-Kincaid grade / p90 sentence length, reader's path)

| File | Original (git HEAD) | After simplicity | After readability |
|---|---|---|---|
| study-plan.md | 9.6 / 36 | 7.8 / 27 | **7.7 / 28** |
| question-bank.md (header) | 10.7 / 29 | 10.8 / 28 | **10.7 / 28** |
| README.md | 16.4 / 46 | 11.5 / 22 | **11.5 / 22** |
| role-and-evidence.md | 12.4 / 33 | 10.7 / 32 | **10.8 / 32** |
| error-log.md | 10.5 / 49 | 5.9 / 28 | **6.0 / 28** |

Undefined-at-first-use terms on the study-plan path: original 6 (`Track A`, `B-lite`, `B-full`, `fluency illusion`, `essentials`, `[ALT]`), after simplicity 3 (`Track A`, `essentials`, `[ALT]`), after readability 0. The grade numbers are a regression guard only; the term count is the metric that binds.

## Quit point (R6) — fixed first

`study-plan.md`, Week 1 gate: *"`defends` (≥70% of the essentials …) → **Track A**, continue below"* and *"Then, for whatever routed Track A"*. Sam is mid-gate, executing, and is routed to a label that exists nowhere in the plan. Rewritten to *"Carry on below"* / *"for the ADRs you could defend"* — the label came off the path rather than being explained on it.

## Ranked findings after the quit point (all applied)

1. `[ALT]` used in the 9-hour cut table before Sam has opened the question bank → "fewer of the question bank's alternatives tables".
2. "essentials" undefined in the gate → "mechanism, failure mode and a rejected alternative mostly right (≥70%)".
3. Three uses of "stream(s)" against the plan's own "work types" naming → standardized.
4. Week 4 "(see below)" pointed at Week 3, which is above → removed.
5. `role-and-evidence.md` "each leg … the lead" — multi-model jargon in an interview-evidence row → "each model … the orchestrating model"; also pointed at the now-moved sign-off table → "changelog".
6. `error-log.md` "You have no reviewer" was unmotivated once the comparison to the beginner package was cut → "Nobody else reads this file"; `Route` legend split into a sub-list.
7. "the framework's §11" in the plan's last section → named and linked inline.
8. `question-bank.md` "(12 total)" ambiguous → "(12 of the 66)"; "Re-encode" given a four-word gloss.

## Verdict per criterion (post-fix, Sam)

| | Criterion | study-plan | question-bank hdr | README | role-and-evidence | error-log |
|---|---|---|---|---|---|---|
| R1 | One-read executable | PASS | PASS | PASS | PASS | PASS |
| R2 | Jargon defined at first use | PASS — `cold-gate` by function (l.7), `re-encode` by its steps, `stuck-rule`/`implementation intention` inline | PASS | PASS | PASS | PASS |
| R3 | Evidence density | PASS — 9h cost table stays; sign-off statistics moved to changelog | PASS | PASS | PASS | PASS |
| R4 | Tone at the work, not the reader | PASS — "you don't get to clear the row by running out of weeks" is aimed at the rule | PASS | PASS | PASS | PASS |
| R5 | Voice, no seams | WEAK — the rewritten "One qualification" and gate paragraphs are plainer than the surrounding original prose; no contradiction, slight register shift | PASS | PASS | PASS | PASS |
| R6 | Dropout | PASS after the Track A fix | PASS | PASS | PASS | PASS |
| R7 | Single-pass actionable | PASS — the one forward reference (`Route = never-encoded`) is routed through Week 0's "read the legend" | PASS — the Week 1 pointer is a handoff, not a lookup | PASS | PASS | PASS |
| R8 | Skimmable on return | PASS | PASS | PASS | PASS | PASS |

Domain complexity deliberately left alone: the question bank's answer pointers, the evidence table's artifact paths, the README thesis vocabulary (idempotent dispatch, tenancy invariants). Those are hard because the subject is hard; Sam knows them.
