# Changelog — interview-prep

What each review round changed and why, with the alternatives that were rejected so they don't get re-litigated. Not needed to run the plan. Panel transcripts are in the linked `*_MULTI_REVIEW.md` files one level up.

| Date | Round | What changed |
|---|---|---|
| 2026-07-08 | First pass | Package built. Codex defined acceptance criteria against the repo before drafting; external-bank contents verified against live pages; audited against LEARNING-SYSTEM.md layer by layer and taken through four review rounds by GPT-5/Codex and Gemini 3.1 Pro |
| 2026-07-22 | Second pass — AI-era role check | Role held. `error-log.md` created as a real file. AI-collaboration round added to week 4, two AI STAR skeletons to week 5, a routing row and a rubric row. The `learn` CLI design deferred. [ROLES-AND-DELIVERABLES_MULTI_REVIEW.md](../ROLES-AND-DELIVERABLES_MULTI_REVIEW.md) |
| 2026-08-01 | Third pass — agentic-coding ownership gap | Week 1 ownership cold-gate; per-item cold marking in the question bank; `[DYD]` → `[EVAL]`/`[ADOPT]` relabel rule; `Route` column in the error log; "mixed-track" concept pushed upstream into LEARNING-SYSTEM.md §2/§10. [PLAN-SIGNOFF_MULTI_REVIEW.md](../PLAN-SIGNOFF_MULTI_REVIEW.md), [AI-OWNERSHIP-GAP_MULTI_REVIEW.md](../AI-OWNERSHIP-GAP_MULTI_REVIEW.md) |
| 2026-08-29 | Simplicity pass | Review reasoning moved out of the operating files into this changelog. Five-axis ownership tag reduced to one cold mark plus the relabel rule; 66 per-question stub lines removed. `learn-cli-README-draft.md` moved to `../parked/`. `Scored` column defined. Readability pass on every file. Three question stems (1.3, 4.5, 5.6) rewritten domain-neutral and "ESP" expanded so every question works outside email. Readiness rubric pulled out into `competency-list.md` with week 1 / week 6 score columns — the §3.1 artifact restored as a file. [SIMPLICITY-PASS_MULTI_REVIEW.md](../SIMPLICITY-PASS_MULTI_REVIEW.md) |

---

## First pass (2026-07-08)

### Framework audit

Audited against [LEARNING-SYSTEM.md](../../learning-system/LEARNING-SYSTEM.md) layer by layer, then taken through four review rounds by two independent models (GPT-5/Codex and Gemini 3.1 Pro). Both signed off. What the audit changed:

| Layer | Finding | Fix |
|---|---|---|
| **L1** goals | Readiness rubric existed but sat at the end, unread until week 6 | Promoted to Week 0 as the competency list; scored in week 1 for a baseline |
| **L8** feedback | "A miss = an Anki card" preserved the fact but never fixed the misconception | Error log with a mandatory *why* column; both the card and the entry |
| **L9** calibration | "Self-grade" and "score honestly" are not calibration | Confidence ratings 0–100% before checking answers, weeks 3–6; new Calibration row in the rubric; week 6 targets the questions where confidence most exceeded score |
| **L6** spacing | Second-pass re-solves waited until week 5 — a 3–4 week gap on *already-failed* items, whose retrieval strength is gone by then | Re-solves start week 2 and run weekly, explicitly capped |
| **L0** foundations | Absent entirely from a 6-week push | Sleep floor, implementation intention, stuck-rule — all in Week 0 |
| **L3** load | Week 1 stacked ADRs + READMEs + summary + question bank + 8–10 problems + Anki setup | READMEs deferred to week 2 |
| **L11** artifact creep | Artifacts accumulated with no keep/cut test | Added to the weekly review, with a three-condition test for what counts as practice vs. bureaucracy |
| **Naming** | This plan and the framework both said "Track A/B/C" meaning different things — a reader could conclude Track A means "skip LeetCode" | Renamed to work types here; Track reserved for learner starting states |

**The budget was the hardest finding, and it was pre-existing.** Both models independently did arithmetic the plan had never had done to it: at the plan's own 25-min-per-problem bar, Drills was asking for ~5.75 hours inside a 3-hour slot, and the headline "9 hrs/week" was fiction once Anki and the weekly review were counted. It is now ~11 hrs/week with the numbers shown, plus a reduced-scope variant that actually reaches 9 by naming what it cuts. A budget you cannot hit reads as personal failure rather than a planning error, which is why this mattered more than it looks.

### Where the plan deviates from the framework, and why

This is a **Track A (Reactivate)** instantiation of the framework: existing competence that needs to become accessible under pressure. Track A's binding constraints are retrieval and calibration — which is why testing is the study method from day one and why confidence ratings appear throughout. The framework has authority over *method*; the plan has authority over *what a senior backend loop actually demands*.

Naming: the plan's three **work types** are concurrent activities. They are unrelated to the framework's **Tracks**, which are learner starting states. Different axis, deliberately different word.

**Why Week 0 has three items and not the framework's three.** Framework §3 asks for a competency list, a prerequisite sketch, and an error log. The prerequisite sketch exists to stop a learner studying above their level — a Track B and C problem. A Track A learner already has the prerequisites; what Track A fails on is showing up consistently under deadline pressure, so the sketch is replaced with an implementation intention (L0). If the learner is repeatedly blocked by missing fundamentals, that assumption was wrong — build the sketch.

Four places the plan deliberately does something the framework would otherwise discourage:

- **Artifacts from day one, against §11's "start tiny."** §11's target is artifacts that *organize* practice — note systems, card decks, dashboards — which displace retrieval while feeling productive. The plan's artifacts *are* the retrieval: an architecture summary written from memory is blank-page recall; a timed design artifact is the exam itself. The three-condition test (produced under test-like constraints, checked immediately against a reference, no ongoing maintenance cost) is what keeps the line from letting anything through. Honest weak case: the week-1 baseline recording is a calibration instrument rather than retrieval practice; it earns its place as *one* recording that establishes a baseline, and should not become a habit of recording everything.
- **Blocked practice in weeks 1–5.** The framework prefers mixing problem types, but also says not to mix before baseline competence — so NeetCode runs blocked by category through week 5, and week 6 goes fully mixed and timed. That is the framework's own rule, correctly applied.
- **Heavy volume on a deadline.** The framework optimizes for durable learning; the plan optimizes for peak performance on a known date. Some of the week-6 taper is deliberately about accessibility rather than long-term retention.
- **Recognition-heavy source material.** Re-reading your own ADRs is low-value by framework standards. It is retained only as *input* to a from-memory reconstruction — never as the study method itself.

Where the framework does **not** yield: no plan is valid without delayed retrieval, analyzed errors, and a calibration check. Those were added, not negotiated away.

## Second pass (2026-07-22) — AI-era role check

Re-audited after a multi-model panel re-established the target role under AI-era market conditions ([ROLES-AND-DELIVERABLES_MULTI_REVIEW.md](../ROLES-AND-DELIVERABLES_MULTI_REVIEW.md)). Panel: Claude Opus 4.8 (lead, live web research) · Gemini 3.1 Pro High · GPT-5.2/Codex.

**The role did not change** — Senior Backend / Product Platform survived scrutiny and the market moved *toward* it: software engineering resilient at the category level; seniority the strongest protective factor (ICs −9% vs leadership −1.7%); backend complexity valued while frontend commoditizes. Do not repackage as "AI Engineer": ML postings are genuinely up ~40%, but there are no evidence rows for modeling work. Four amendments followed:

| # | Change | Why |
|---|---|---|
| 1 | `error-log.md` now exists as a real file; Week 0 links it | It was a concept in a document, never an artifact on disk — the most common way the highest-leverage part of a plan quietly never happens |
| 2 | AI-collaboration round added to week 4 (1h) | 2026 senior loops probe it directly; the package trained none of it |
| 3 | Two AI STAR skeletons added to week 5; new routing row; new rubric row | The new evidence needs a spoken form and a pass bar, or it isn't trained |
| 4 | Hour funded from Repo conceptual (architecture summary #3, "tenant isolation as an invariant", cut from week 4), **not** Drills | See below |

**The hour that moved.** Week 4 goes repo conceptual 3h→2h, simulation 2h→3h; total budget unchanged. Summary #3 was the cut because, of the three from-memory summaries, it had the lowest marginal return and the invariant is already covered in question-bank §5. Two alternatives rejected:

- **Cutting Drills (NeetCode).** Proposed at 30–40% during review and withdrawn under challenge. The plan sits at 40 problems against its own stated pass bar of 40–50. Cutting below the rubric on a gate that verifiably still exists, to fund a round type that is real but not yet universal, trades a known gate for a speculative one. Coding rounds have been *added to*, not replaced.
- **Adding the hour to the total.** The budget already survived one honest-arithmetic pass. Growing it silently is how it becomes fiction again.

**Evidence strength of the AI-collaboration row.** The role findings came from hard data — 180M job postings, Stanford's employment series, an NBER firm survey. The claim that 2026 loops contain AI-review and AI-permitted rounds came from trade press and interview-coaching sites, parties with an incentive to say the interview changed; no hiring data was found establishing how common those rounds are. The row is kept on a cost argument: the prep is one hour, it reuses code-review judgment the learner already has, and the *verbal* probe ("so how do you use AI?") is near-universal and cheap to fail regardless. That is a bet, labelled as one — which is why the plan says to cut this row first if anything has to go.

**Also deferred:** the `learn` spaced-repetition CLI (now in `../parked/`). Unanimous DEFER — right product, wrong substrate for interview prep: its corpus is the learner's own docs, so it trains what they're already strongest on, and it violates framework §3.4 by substituting self-authored recall for an external reference answer. The six-condition build trigger is at the top of that file.

## Third pass (2026-08-01) — agentic-coding ownership gap

Audited after the user flagged that the repo was built partly via agentic coding, breaking the plan's "you already know this" premise for an unknown slice of the content. Two-stage review: Stage 0 signed off the fix plan ([PLAN-SIGNOFF_MULTI_REVIEW.md](../PLAN-SIGNOFF_MULTI_REVIEW.md)), Stage 1 designed the mechanism ([AI-OWNERSHIP-GAP_MULTI_REVIEW.md](../AI-OWNERSHIP-GAP_MULTI_REVIEW.md)). Panel: Claude (lead) · GPT-5.2/Codex · Gemini 3.1 Pro High.

**The user's own hypothesis — "only the timeline changes" — was tested and rejected by both external legs independently.** Three things change: the *method* for flagged items (present-tense re-encoding, not just more Track A hours), the *interview claim* (a design you can't defend cold and never originated can't be worded as "I designed"), and only as a consequence, the timeline.

| Change | Why |
|---|---|
| Week 1 opens with an ownership cold-gate (60 min, before ADRs are reread) | Reading first contaminates a same-day encoding check with the fluency illusion; both legs independently cited the framework's own L9/L5 warnings |
| Routing on present-tense cold ability only | Provenance and encoding depth are different things — an AI-proposed idea the user grilled for days is well-encoded; a user-requested feature whose details were rubber-stamped isn't. Routing on provenance would misroute both |
| Re-encoding funded from Repo-conceptual breadth, never Drills | Same precedent as the second pass: don't trade a verified gate for a speculative one |
| `[DYD]` relabeled `[EVAL]`/`[ADOPT]` when the claim isn't "designed" | Makes the honesty fix visible at the point of use instead of in metadata nobody checks |
| No AI-inferred classification of real content | Only the user knows what they knew before an AI proposed something; an AI-run "audit" would be provenance-by-proxy and would perform the exact diagnostic the learner is supposed to do themselves |

**Rejected:** having the panel classify real ADRs, evidence rows and questions by provenance now, to save the user the work later. Violates the self-tagging constraint and risks a confidently-wrong classification the framework specifically warns against (§14).

**Mechanism note.** This pass originally introduced a four-axis self-tag (prior exposure · origination · current cold ability · claim strength) on every question and evidence row. The simplicity pass reduced it to the one axis that routes (cold ability) plus the relabel rule, because the doc itself said the other axes "only affect how you word the claim" — and the relabel rule already handles the wording.

## Simplicity pass (2026-08-29)

Triggered by the owner noting that this package felt more complex than `../web-engineer-prep/`, though both derive from the same framework. Multi-model review ([SIMPLICITY-PASS_MULTI_REVIEW.md](../SIMPLICITY-PASS_MULTI_REVIEW.md)): Claude (lead) · GPT-5.2/Codex · Gemini 3.1 Pro High (Antigravity).

**Diagnosis.** The beginner package had a reader who wasn't its author, so each review round forced a rewrite for that reader, and the mentor's reasoning was kept out of the beginner's files. This package's reader *is* its author, who sat in every review round, so each round's reasoning was written into the operating docs "so it doesn't have to be re-derived" — but the person running the plan isn't re-deriving it. The reviewer's voice was in the runner's reading path.

**What moved or went:** three sign-off records, the framework-alignment audit, the "hour that moved" note, two rubric caveats and ten dated `(added …)` markers → this file. 66 identical per-question tag stubs and the PE/ORIG/CLAIM/ROUTE axes → cut; one cold mark plus the relabel rule does the work. `learn-cli-README-draft.md` → `../parked/`. The 9-hour variant kept its cost table and lost its surrounding paragraphs.

**What stayed, deliberately:** three parallel work types, the readiness rubric, external routing, confidence-before + scored, the `Route` column (it routes remediation to Anki vs re-encoding, which `Why` doesn't), the cold-gate as a distinct pre-reading step, and `external-comparison.md` as a standalone reference. All of it is the cost of a senior loop testing four signals where a beginner course tests one.

**Follow-up, same day — the competency list.** Since the first pass the competency list had lived inside `study-plan.md` as the readiness rubric (see the L1 row above). The substance was right — Track A phrasing, pass bars — but it wasn't an artifact you could write in: no score column, and the plan needed two signposts to say "the rubric is your competency list." It is now `competency-list.md`, with week 1 / week 6 score columns, and Week 0 links to it. The prerequisite sketch stays out, as decided in the first pass: a Track A learner has the prerequisites, and for the Track B pockets the cold-gate's re-encoding loop (reread → self-explain → rebuild) is the per-item substitute. Faithfulness sign-off: [FAITHFULNESS-SIGNOFF_MULTI_REVIEW.md](../FAITHFULNESS-SIGNOFF_MULTI_REVIEW.md) — both external legs signed off on both decisions and found nothing lost in the simplification. All three reviewers independently found the same pre-existing §8 gap: the error log's AI column only fired on a miss or a stall, so it could never count the request that leaves no trace. Fixed with a third error-log trigger (log every AI use), and the AI-disabled mocks are now named as the framework's self-test. Lead-only addition: a one-line prerequisite check on the Week 4 gap topics — §3.2 applied to the only material in the plan the learner never built.
