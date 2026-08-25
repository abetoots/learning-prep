# AI-Ownership-Gap Fix — Stage 1 — Content Design

Follows `PLAN-SIGNOFF_MULTI_REVIEW.md` (Stage 0, plan sign-off). This round designs the actual mechanism for `interview-prep/*` and decides whether it belongs upstream in `~/learning-system/LEARNING-SYSTEM.md`. Panel: Claude (lead) · GPT-5.2/Codex · Gemini 3.1 Pro High (Antigravity). Both legs re-read the revised plan and all five grounding files.

## Executive summary

**The user's hypothesis — "only the timeline changes" — is wrong, and both legs agree independently.** Three things change, not one: (1) the *method* for flagged items (present-tense re-encoding, not just more retrieval hours), (2) the *interview claim* itself (a design you can't defend cold and never originated can't be worded as "I designed" even after you now understand it), and (3), only as a downstream consequence of the first two, the *timeline*. Both legs also independently concluded this generalizes upstream to `LEARNING-SYSTEM.md` — agentic coding produces **mixed-track** learning efforts (Track A for what you wrote/verified, Track B for what you didn't), which the framework doesn't currently name.

## Consensus findings

1. **Four-axis tagging, routing on one axis only.** `Prior exposure` (knew/partial/new/unsure) × `Origination` (user-derived/AI-proposed/jointly-shaped/contested) × `Current cold ability` (defends/recognizes/blank) × `Interview-claim strength` (designed/evaluated-and-approved/adopted-with-caveat/learned-afterward). **Routing decision uses `Current cold ability` alone** — the other three axes only shape wording, never whether more study is needed. Both legs converged on this exact structure independently.
2. **The cold-gate runs at the start of Week 1, before reading the ADRs, inverting the current order.** Reading first contaminates the diagnostic (fluency illusion — a freshly-read ADR feels "known"). Both legs place it here specifically, not in Week 0 (Week 0 stays a clean 60-minute setup) and not spread across weeks.
3. **Question-bank tagging reuses the existing tag system rather than inventing new syntax.** When `Interview-claim strength` ≠ `designed`, a `[DYD]` question is relabeled `[EVAL]` or `[ADOPT]` (Antigravity's proposal, adopted) — this makes the honesty fix visible at a glance without a parallel metadata system nobody will maintain. Paired with a compact one-line diagnostic tag under the pointers (Codex's format, adopted for both question-bank.md and role-and-evidence.md, which gets a new "Ownership tag" column rather than rewritten claim prose — safer, since we don't know yet which real claims need rewording).
4. **role-and-evidence.md's ownership tags stay blank/self-tag placeholders in this pass.** Per the Stage 0 constraint, neither leg fabricated real classifications for the actual repo content — both explicitly marked pilot outputs as illustrative or `USER`-filled. This is preserved into Stage 2: the file changes add the *column and convention*, not invented answers.
5. **Both unfilled AI-collaboration placeholder rows in role-and-evidence.md stay unfilled.** Antigravity's pilot invented a plausible-sounding fill (a `$set`-vs-`$inc` catch story) — **this is not going into the real file.** It's a good illustration of the *shape* an entry should take, but inserting fabricated content into the user's own evidence table would be worse than the problem this whole effort exists to fix. Stage 2 adds the mechanism only.
6. **Upstream, not just local.** Both legs concluded the mixed-track problem and the retrospective-self-report failure mode are general enough to warrant a short addition to `LEARNING-SYSTEM.md` (near §2's track table and/or §10 diagnostics) — not a rewrite, one tight addition consistent with the framework's own §11 anti-bloat guardrail.

## Debated point — resolved

**Where does Track-B re-encoding time come from?** Codex: fund from Week 1/2 Repo-conceptual breadth only, never from Drills — citing the plan's own prior precedent (a proposed 30–40% Drills cut was reviewed and explicitly withdrawn in an earlier round, on the grounds that NeetCode sits at the floor of its own stated 40–50 pass bar). Antigravity: fund primarily by cutting NeetCode problems (2 problems per B-item), falling back to Repo-conceptual only once Drills hit the floor — but its own stated falsifier is that this exact cut is the failure mode ("if cutting Drills... drops the LeetCode completion rate below the 30-problem absolute floor").

**Resolution (lead's casting vote): Codex's position wins.** It's consistent with the file's own documented precedent, and Antigravity's own falsifier undercuts its primary recommendation rather than supporting it. Adopted rule: **Track-B time is funded from Repo-conceptual breadth (drop [ALT]-table depth first), never from Drills.** Named explicitly in study-plan.md, matching the file's existing convention for budget tradeoffs ("the one hour that moved").

## Concrete design (both legs' worked pilots, synthesized)

- **Routing thresholds** (Codex, adopted): `defends` = unaided, ≥70% of answer-pointer essentials, names the invariant/failure mode, gives one rejected alternative when relevant, states confidence before checking → **Track A**. `recognizes` (partial, no real reconstruction) → **B-lite** (25 min: 8 min re-read the grounding artifact · 7 min self-explain · 7 min blank-page retry · 3 min compare/log). `blank` → **B-full** (50 min: 15 min worked-example re-read · 15 min completion-problem/partial retry · 15 min blank attempt · 5 min compare/log).
- **Cold-gate placement**: replaces/precedes the first 60 minutes of Week 1's existing "Repo conceptual" block, run against the same four ADRs (0008/0009/0013/0016) already scheduled there. Output is a routing table (item → PE/ORIG/COLD/CLAIM/ROUTE), not prose.
- **Budget rule**: 2 hours of Repo-conceptual breadth is the named first cut for re-encoding time; if total re-encoding exceeds 4 hours, `Conceptual depth` gets marked "not yet" on the readiness rubric unless a week is explicitly added — the plan does not silently absorb unbounded Track-B cost, matching the file's existing "you don't get to move the bar because you ran out of time" convention (already used for the Coding row in week 6).
- **question-bank.md tag line** (per item, self-filled by the user, not by any model): `Ownership diagnostic: PE=? · ORIG=? · COLD=? · CLAIM=? · ROUTE=?`. If `CLAIM≠designed`, the `[DYD]` prefix becomes `[EVAL]` or `[ADOPT]`.
- **role-and-evidence.md**: new "Ownership tag" column, same four-field format, blank/self-tag by default; a documented rule that the claim cell's verb gets rewritten (e.g. "Designs for..." → "Can defend the design of...") only once the user's own tag says `CLAIM≠designed` — never rewritten speculatively.
- **error-log.md**: extend the schema with the ROUTE value as an explicit column (or fold into the existing `Why` column with a controlled vocabulary) so "I just forgot" (decayed — Track A refresh) is distinguishable from "I never actually encoded this" (Track B, AI-introduced or not) at the row level, not just in the weekly-review prose.
- **LEARNING-SYSTEM.md**: one short addition near §2 (mixed-track note: an AI-assisted build can leave a single "Track A" effort with Track-B pockets; per-item, not per-effort, is the right grain) and one new diagnostic row in §10 ("I can't tell if I actually knew this or just approved it" → route by present-tense cold attempt, never by memory of the past).

## Verdict

| Leg | Verdict |
|---|---|
| Claude (lead) | Adopt consensus; casting vote to Codex on the Drills-funding question, for the precedent reason above |
| Codex | No blocker; major constraint noted (pilot values are illustrative, not real self-tags) — respected |
| Antigravity | No blockers; falsifiers given (fluency illusion if cold-gate order is violated — mitigated by design; Drills-floor risk — resolved by adopting Codex's funding rule instead) |

**Stage 1 status: SIGNED OFF.** Proceeded to Stage 2 (apply).

## Stage 3 — re-review of the applied edits (2026-08-01)

Both legs re-read the five edited files fresh and found real issues (not bare GOs):

- **Codex, 2 majors:** `question-bank.md` had only the legend, not the per-item tag line Stage 1 called for (65 questions, 0 tagged); `error-log.md`'s `decayed` route still permitted "confident I once knew it" — the exact retrospective-self-report failure this whole mechanism exists to eliminate.
- **Codex, 1 minor:** `study-plan.md` Week 0's error-log schema description didn't mention the new `Route` column.
- **Antigravity, 1 low blocker:** two pre-existing broken links (`framework/LEARNING-SYSTEM.md`, a path that never existed) in `study-plan.md`, unrelated to this round's edits but caught in the same pass.
- **Antigravity confirmed, unprompted:** no fabricated content leaked into `role-and-evidence.md`'s two AI-collaboration placeholder rows, and it does not object to the Drills-funding resolution now that it sees it applied.

All four fixed: 65/65 per-item ownership-diagnostic lines added to `question-bank.md` (scripted, verified by count); `error-log.md`'s `decayed` definition now requires a present-tense cold attempt unconditionally; `study-plan.md`'s Week 0 schema description updated; both broken links repointed to `../../learning-system/LEARNING-SYSTEM.md`. Both legs re-verified against the fixes and signed off with no remaining issues.

**Stage 3-4 status: SIGNED OFF. No further iteration needed.**
