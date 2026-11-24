# ai-engineer-prep — learning path

Copied from `~/learning-system/template/` on 2026-10-14. The template owns the **shape** of these files; you own everything written in them. Framework: `~/learning-system/LEARNING-SYSTEM.md` — not needed to run this plan.

**Goal:** transition from Senior Backend / Product Platform engineer to **Senior AI Engineer (LLM application and agentic systems)** — the role that builds products on top of models: tool use, retrieval, agent loops, evals, serving and cost. Why this role: in 2025–2026 primary sources (Huyen/Orosz, swyx) it is defined as "software engineering with models in the stack", and its production failures — non-deterministic outputs, zombie agent steps, retries, rate spikes, tenant isolation — are the correctness problems `../interview-prep/role-and-evidence.md` already proves. **Not** ML engineer (trains models; math-gated) and **not** AI inference/platform infrastructure (GPU serving, Kubernetes — the one area the evidence file names as *not* yours). Roles rejected and the adjacent one kept in view: [CHANGELOG.md](CHANGELOG.md).

**Target performance, every line — all three, not one:** *explain it from first principles with no notes · say what breaks if it's wrong · build the smallest working version from a blank file.* There is no interview; this is the exam.

## Files

| File | What it is | When you touch it |
|---|---|---|
| [competency-list.md](competency-list.md) | "I can…" lines with proof, date, score. Provisional for two weeks (new-field rule) | end of every session; weekly review |
| [prerequisite-sketch.md](prerequisite-sketch.md) | the answer-key contract — **what grades each line, and the bar** — what must be true first, this week's targets | week 0, then weekly |
| [error-log.md](error-log.md) | append-only rows; the *why* column is the point | any miss, any stall over 10 min, **any AI use** |
| [CHANGELOG.md](CHANGELOG.md) | review rounds, what changed, what was rejected | review rounds only. Not needed to run the plan |

Intake answers are the `## Plan` block below. Struck at intake: `drill-bank.md` (every line has an external key — a grader or a measurement), `decision-log.md` (not a judgment domain), `mentor/` (self-directed). Add nothing until the plan has run two weeks and you can name the problem the addition solves.

## Setup

**1. Fill the three `<…>` fields in `## Plan`:** hours per week, which day gets which block, and the review day. Everything else is decided.

**2. Day 0 — the blank-page pass, one sitting, about 75 minutes, before you open any course material.** For each of the 13 lines in `competency-list.md`: 5 minutes, everything closed, write what you can produce right now. Then mark its Track column — `A` if the page filled (you have it; just test it), `C` if you can name the parts but can't start (learn it from a worked example first), `B` if neither (same, but smaller steps and no mixing). This is a *cold* test on purpose: taken before re-reading anything, so familiarity can't pass for knowledge. Four of the lines transfer from a repo that was partly built with agentic coding, which is exactly where familiarity lies.

**3. Line 1 decides what Monday is.** Python is the field's language and your evidence is TypeScript.
- Line 1 came up `A` → enrol in the Hugging Face Agents Course and open unit 1. That enrolment signs the answer-key contract in `prerequisite-sketch.md §1`.
- Line 1 came up `B` or `C` → Python first, on **Exercism's Python track** (free; each exercise is a worked example with a test suite you run locally and community solutions to compare against *after* you pass). Do not enrol in the course until line 1's `B` proof exists — a cold rebuild with the tests green.

**4. Monday's first item is already set** at the bottom of `## Plan`.

## Plan

```
Track: C, routed per item — backend-transferable items are A; LLM-specific items are C; Python decided by the Day 0 pass
Domain class: procedural (building) + conceptual (design). Not judgment.
Reader model: self   Mentor: —
Reference answer: external. Grader — the Hugging Face Agents Course for lines 4, 5, 11 (unit quiz ≥80%; capstone benchmark at the course's passing score). Measurement — every other line, with the bar written next to it in prerequisite-sketch.md §1 before the attempt (e.g. line 1: tests green on a cold rebuild; line 6b: recall@5 ≥ 0.8 and beats a keyword baseline). Design quality is outside "done" for every line — a reviewer's job later
AI-assisted material: yes — lines 2, 4, 5, 9 transfer from websand-v4, which was partly built with agentic coding. The Day 0 pass is the per-item cold gate; a blank routes that line to the worked-example loop below regardless of what the evidence file says
Files: README, competency-list, prerequisite-sketch, error-log, CHANGELOG
Hours/week: <n>   Deadline: —   Weeks total: open — ends at the competency list
Budget: skipped on purpose (no deadline)

Session protocols: <day → block, for each study day>. The blocks:
  60 (new material)
    0–5   blank-page recall of the last session — this is the block that builds memory
    5–10  optional: try it before any instruction
    10–45 the worked example, explaining each step to yourself
    45–55 close everything, rebuild it
    55–60 compare, log why you diverged, card only atomic facts; put today's material in tomorrow's recall slot
  30 (practice day)
    3 recall · 20 one small build or re-solve · 5 close the source, sketch what you did · 2 log gaps. No rereading
  120 (build day)
    0–5     recall, then write what you'll build and the stuck-rule: blocked >10 min → error-log row before asking anything
    5–55    build the line
    55–65   real break
    65–105  deliberate practice on whatever the first block exposed
    105–120 blank-page synthesis, one transfer attempt, error log

Who sets the order: the course's unit order for C items; A items have no order — test them and move on

Core loop, per line:
  1  DEFINE    the "I can" line
  2  STRUGGLE  10–15 min before instruction (skip for B-routed lines)
  3  ENCODE    the worked example, explained to yourself
  4  RETRIEVE  close everything, blank page
  5  FEEDBACK  compare to the key, write why you diverged — the binding step: no PRACTICE on a line whose key isn't named
  6  PRACTICE  with less help each time
  7  INTEGRATE into the capstone agent
  8  SCHEDULE  the review; card only atomic facts
  9  TRANSFER  teach it cold, or an unseen problem
  10 UPDATE    error log → next target
  A-routed line: start at 4.
  B-routed line: 1 → 3 → completion problem (ask AI to give the example back with one piece blanked out) → 4 → 5 → 6. No struggle, no mixing, until 6 is comfortable.

"I can" phrasing rule: best guess, marked ?, revised at two weeks — the revision is the learning

AI policy: Attempt first. Then: "Here's my attempt. What's wrong with my reasoning?" · "Ask me questions until I find it myself." · "Give this worked example back with one piece removed and a comment saying what belongs there. Don't show me the finished version." Never: "What's the answer?" / "Fix this." Metric: share of AI requests asking for a final answer vs a hint. Count each request as you make it. Monthly: one problem with AI fully off; if it collapses, critique-only until it doesn't. This is a new domain — verify against primary docs until you have your own judgment, especially for anything an AI says about AI

Thresholds: same misconception three rows running → one curriculum item, top of next week · answer-seeking share rising → critique-only until it turns · confidence most exceeds score in a category → that category is next week · "I just forgot" only counts when the error log's Route column (where the fix goes) says forgot, not never-learned · stalled line → never worked on? smaller; needs something first? add it ahead; too big? split · weeks 3–4 feel worse — that is the mechanism

Weekly review: <day>, 60 min — blank-page dump of the week · error log for patterns, not entries · prune the deck · one teach-it-cold on a line that is not this week's · update the list and next week's targets. Once a month: open roadmap.sh/ai-engineer and check for a blind spot the list doesn't cover — that is all roadmap.sh is for

First keep/cut test: 2026-10-28 — does each artifact still earn its place?

Monday's first item — the branch Day 0 chose for line 1:
  A      → rebuild line 1 cold (functions, dataclass, one async call, one pytest test) until the tests are green; then course unit 1
  B or C → Exercism Python, first concept exercise: read its example · blank out one piece and fill it · rebuild from an empty file with the tests green. No course material until line 1's B proof exists

Weeks:
| Week | Add | Remove | Metric | Checkpoint |
| 1 | Day 0 pass; the line-1 branch; blank-page recall after every session | reading ahead in the course; roadmap.sh browsing | share of session time spent retrieving (>30%) | can you recall yesterday cold? |
| 2 | a deck for atomic facts only (API shapes, terms), ≤15 cards/day; prerequisite sketch §2 filled | carding anything you could look up | deck stays lean (>20 min → prune) | first revision of the ? lines |
| 3 | deliberate practice on the weakest sub-skill the log shows; error log in anger | looking at the course solution before a real attempt | error-log rows analysed, not logged | same error recurring? |
| 4 | confidence rating before every graded attempt; first teach-it-cold; mixed sets across units — only if familiar problems are reliable, else stay blocked | labelled-only practice; answer-seeking AI use | performance on the course's unseen benchmark items | does confidence match score? |
| 5+ | written by each weekly review, one row ahead | | | |
```

## Runtime

Compile once, at path start, into whatever you run the plan in. Tables marked **Database:** are databases — header row is the schema, import as CSV. Everything else is page content. **Never re-import.** A structural change mid-path (a new column, a new `Route` value) is made in the runtime and gets one line in `CHANGELOG.md` so the next compile carries it.
