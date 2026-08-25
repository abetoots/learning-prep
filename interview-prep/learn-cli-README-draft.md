> ## ⏸ STATUS: DEFERRED — do not build during the job hunt
>
> Multi-model panel verdict, 2026-07-22 (see `../ROLES-AND-DELIVERABLES_MULTI_REVIEW.md` §3). Unanimous DEFER.
>
> **This is not a rejection of the design.** The tool encodes the learning system correctly — confidence before reveal (L9), FSRS spacing (L6), an error taxonomy rather than bare correctness (L8), provenance discipline, and an AI policy that keeps the model out of answer-generation (§8). As a design document it is better aligned to the framework than most commercial learning tools.
>
> **Two reasons it is deferred:**
>
> 1. **Wrong substrate.** Its corpus is generated from docs you wrote yourself, so it can only train recall of the material you are *already strongest on*. It cannot touch what `external-comparison.md` identifies as the actual gaps: canonical system-design vocabulary, foreign design prompts, and timed algorithms.
> 2. **It violates LEARNING-SYSTEM §3.4.** Your own docs are not an *external* reference answer. §3.4 requires that something outside your own head can tell you you're wrong. For re-onboarding to your own codebase — the stated primary use — that's fine, because the code arbitrates. For interview prep it silently substitutes self-authored recall for market-shaped feedback.
>
> **The honest framing:** this is a legitimate product conflated with an illegitimate study method. Those are two projects with different acceptance criteria, and this README is written as if they are one thing.
>
> ### Trigger to build — all six must hold
>
> 1. ≥10 consecutive study days, or 2 calendar weeks, whichever is later
> 2. The manual markdown loop has produced ≥30 answered prompts/problems
> 3. ≥10 `error-log.md` entries with *analyzed causes*, not just misses
> 4. **≥3 misses recur specifically because of scheduling, provenance drift, or calibration-tracking overhead** — not because the corpus is weak
> 5. External gap work is already running (timed algorithms + canonical design prompts in the loop)
> 6. You can complete this sentence with numbers: *"The CLI removes X minutes or Y recurring errors per week that the markdown loop cannot remove."*
>
> **Condition 4 is load-bearing.** It requires the friction to be of the exact class this tool removes. "I ran markdown for two weeks and got bored" is avoidance of harder practice wearing a tooling costume — which is §11's named failure mode, and exactly how this project would fail.
>
> Note the trigger makes employment status irrelevant. Signing an offer is a calendar event, not a learning-system criterion. Unemployed and all six hold → build it. Employed and they don't → don't.

---

# learn

> A stale-aware memory for your codebase.
> *(working name — command shown as `learn` throughout)*

`learn` is a local-first CLI that turns your repo's documentation and decisions
into a living test suite for your own understanding — scheduled by spaced
repetition, grounded in verbatim evidence, and invalidated automatically when
the source changes.

You wrote the architecture. You understood the tradeoffs. That was four months
and two refactors ago. `learn` is the tool that notices.

## What it does

```bash
# Compile your docs into evidence-grounded questions
learn compile ./docs

# Review what's due — 5 minutes, in your terminal
learn review

# See what changed underneath your knowledge
learn stale

# Evidence-cited analysis of where your understanding is weak
learn journal
```

Every question carries provenance: the file, the span, the verbatim quote it
was generated from, and the hash that detects when that evidence changes.
When your docs or code move on, `learn` flags the affected questions instead
of quizzing you on a world that no longer exists.

## What it is

- **A retention tool for things you already understood once.** Your
  architecture decisions, retry semantics, failure modes, invariants — the
  knowledge that silently decays between the day you write it and the day
  you need it in an incident.
- **A re-onboarding accelerator to your own code.** The primary user is
  future-you, returning to a repo present-you understands.
- **Stale-aware by design.** Classic spaced repetition assumes the truth
  holds still. Codebases don't. `learn` treats "the source changed" as a
  first-class event, distinct from "you forgot."
- **Local-first.** One SQLite file you own. Your answer history, confidence
  ratings, and weakness map never leave your machine. Bring your own model —
  it runs against the coding-agent subscription you already pay for
  (Claude Code, Codex) instead of metered API calls.
- **Evidence-disciplined.** Questions that can't cite verbatim source text
  are dropped at generation time by a deterministic check — not by asking
  the model to promise it isn't hallucinating. The journal follows the same
  rule: every claim about your weaknesses must cite the specific review
  events that support it, or it doesn't get made.

## What it is not

- **Not an interview prep tool.** For standardized public question banks
  (LeetCode grinding, "top 100 system design questions"), curated resources
  are better and always will be. `learn` only helps with interviews
  indirectly: feed it *your own* study notes and it will maintain your
  retention of them.
- **Not a course, tutor, or content generator.** It doesn't teach you things
  you never learned. It generates questions exclusively from sources you
  provide; if the knowledge isn't in your docs, notes, or decisions, it has
  nothing to test.
- **Not a chat wrapper.** The LLM is a replaceable backend used for two
  narrow jobs: compiling sources into questions, and batch-classifying your
  answers after sessions. The product is the durable state — the event log,
  the scheduler, the provenance graph. Delete the LLM and your data still
  means something.
- **Not gamified.** No streaks, no XP, no leaderboard. The only score is
  whether you still understand your system, and whether you know when
  you're overconfident.

## How a review works

1. A question is due (FSRS scheduling, per learning-unit, not per-card).
2. You answer in your own words, then rate your confidence — *before*
   seeing anything.
3. The rubric and evidence are revealed; you self-grade. Instant, offline,
   no LLM in the loop.
4. Later, an async batch pass (`learn analyze`) classifies your answer
   against a fixed failure taxonomy — confident-wrong, mechanism-vs-symptom
   confusion, implementation-without-principle — citing your own words as
   evidence. When its verdict contradicts your self-grade, that
   disagreement is logged as a calibration signal: the map of where you
   *think* you know things.

## Why not Anki?

Anki is excellent for stable knowledge and manual card curation. `learn`
differs on exactly three points, and if you don't need them, use Anki:

1. **Generation from your sources**, with provenance, instead of hand-writing
   cards for a codebase that changes weekly.
2. **Staleness detection** — cards that know when their source truth moved.
3. **Mastery attached to concepts, not cards** — questions are disposable
   renderings; your learning history survives their regeneration.

## Philosophy

The techniques `learn` applies — retrieval practice, spacing, interleaving,
confidence calibration — are the small set with robust evidence behind them
(see `docs/evidence.md` for citations). It applies them inside the loop
instead of recommending them, and when the journal suggests an intervention,
it must cite both the research and your data. If it can't point at the
evidence, it doesn't get to make the claim.

## Status / Roadmap

- **v1 (this):** markdown/docs adapter, FSRS review loop, hash-based
  staleness, async metacognition analysis, journal & knowledge-debt reports.
- **Exploring:** PR/diff adapter (reasoning-history questions), code-verified
  evidence (doc/code mismatch detection), MCP learner-profile export,
  additional source adapters (PDFs, notes).
- **Explicit non-goals for now:** team dashboards, manager-visible metrics,
  goal-based curriculum generation from thin air.

---

*Your learning telemetry belongs to you.*
