# Plan Sign-off — Stage 0 — AI-Ownership-Gap Fix

Reviews the plan at `~/.claude/plans/please-read-the-learning-mellow-moore.md` (not the interview-prep content itself — that's Stage 1). Panel: Claude Opus/Sonnet (lead) · GPT-5.2/Codex · Gemini 3.1 Pro High (via Antigravity). Both external legs read the plan and all five grounding files directly (confirmed in-response, not assumed).

## Executive summary

Both legs independently converged on the same core defect from different angles, which is a stronger signal than either alone: **the plan's "self-tagging" step, as originally scoped, asks the user to retrospectively judge whether they knew something before an AI proposed it — and that judgment is exactly the kind of thing the framework itself says is unreliable** (fluency illusion, hindsight bias, L9 miscalibration). Neither leg gave a bare approval. Plan revised in response; Stage 1 may proceed with the tightened scope below.

## Consensus findings

1. **The two-category frame conflates provenance with encoding depth.** "Known-but-AI-implemented" vs. "AI-introduced-and-approved" describes *who proposed it*, not *whether it was ever actually learned*. Both legs gave concrete counter-examples where provenance and encoding come apart in both directions:
   - Codex: a user recognizes a concept as "known" before the AI wrote it, but under cold questioning can't reconstruct the invariant — the real problem is shallow prior encoding, not AI involvement at all.
   - Antigravity: an AI proposes an architecture but the user then spends days arguing edge cases and writing the ADR (ICAP-Interactive engagement) — provenance says "AI-introduced" but encoding is as deep as anything self-derived. Inversely, a user asks for something they understand at a high level ("add a queue") but the AI quietly picks retry/idempotency semantics the user rubber-stamped — provenance reads as "user-originated" but the actual implementation detail was never examined.
2. **Retrospective self-tagging is the wrong instrument.** Both legs, citing the same framework section (L9 calibration) independently of each other, said a memory survey ("did I know this before?") will systematically mis-tag in the direction of overconfidence — today's familiarity with an ADR the user has now read several times will get misremembered as having been there from the start.
3. **The fix is a present-tense diagnostic, not a memory question.** Both legs converged on the same replacement: route by the result of a blank-page attempt *right now*, not a recollection of the past. Historical provenance becomes context for *why* a gap exists (useful for the honesty framing in role-and-evidence.md), never the basis for *deciding whether* one exists.
4. **No blocker to starting Stage 1**, contingent on the scope tightening below actually landing in the Stage 1 prompt.

## Debated / leg-unique points — and resolution

- **Antigravity's structural blocker (Track B budget):** flagged that once an item fails the cold-attempt test, Track A retrieval is actively counterproductive per the framework's own L5 warning ("retrieval practice on material you never understood just entrenches confusion") — and study-plan.md's ~11hr/week, 6-week budget has no named slack for real Track B work (worked example → completion problem → blank editor). Codex's review didn't raise this independently.
  **Resolution: adopted as a hard requirement for Stage 1.** The panel must design where a flagged item's re-encoding time comes from, following the same explicit-tradeoff discipline study-plan.md already uses elsewhere (e.g. "the one hour that moved," "the 12 hours that have to come out"). No silent budget growth.
- **Codex's multi-axis reframing:** prior exposure (knew/partial/new/unsure) × origination (user-derived/AI-proposed/jointly-shaped/contested) × current cold ability (defends/recognizes/blank) × interview-claim strength (designed/evaluated-and-approved/adopted-with-caveat/learned-afterward). Antigravity's counter-examples independently motivate the same structure without naming it as axes.
  **Resolution: adopted.** This is the cleanest way to satisfy both legs' point 1 without inventing a third ad hoc category — routing is driven by `current cold ability` alone (a demonstrated fact), while the other three axes only shape *how a claim gets worded* in role-and-evidence.md/question-bank.md.
- **Codex's pilot-before-rollout:** test the mechanism on ~4 representative items before touching the whole package. No objection from Antigravity; low-cost, high-value.
  **Resolution: adopted.**

## Actionable recommendations (folded into the plan file already)

1. Stage 1's dispatch prompt now specifies present-tense cold-attempt routing (not memory survey) as the mechanism's core.
2. Stage 1's dispatch prompt now specifies the four-axis model in place of the two-bucket framing.
3. Stage 1's dispatch prompt now requires an explicit Track-B routing + budget-fallback design as part of its output, not left implicit.
4. Stage 1 will pilot the resulting mechanism on 4 representative items (one ADR-grounded [DYD] question, one non-DYD question, one evidence-table row, one AI-collaboration placeholder row) before Stage 2's full-package edit pass.
5. The open question of whether this generalizes to `~/learning-system/LEARNING-SYSTEM.md` remains open for Stage 1 to answer — not decided here.

## Sign-off

| Leg | Verdict | Notes |
|---|---|---|
| Claude (lead) | ADOPT both legs' consensus fix | Independent convergence from two different framework sections (L9 alone vs. L9+L5+ICAP) on the same mechanism change is stronger evidence than a single leg's opinion; folded in verbatim rather than diluted |
| Codex (GPT-5.2) | No blocker; explicit falsifier given and resolved | Confirmed reading all 6 files before answering |
| Antigravity (Gemini 3.1 Pro High) | 2 blockers + 1 major; both resolved by plan edits above | Given file paths directly per skill protocol (no inlined content) |

**Stage 0 status: SIGNED OFF.** Proceeding to Stage 1 with the revised scope.
