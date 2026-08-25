# 6-Week Study Plan — Senior Backend / Product Platform Engineer

**Tonight: 60 minutes.** Read the readiness rubric at the bottom of this file, then do the three Week 0 tasks. Then stop. Everything else starts tomorrow.

**The premise.** You already know this material — you proved that by building the system. What you can't reliably do yet is produce it on demand, out loud, with a clock running. So this plan *tests* you from day one rather than teaching you. Re-reading your own docs is not the study method here; it's raw material for recall, nothing more.

**The premise's one qualification (added 2026-08-01).** "You already know this" assumed the repo was entirely hand-written. Some of it was built via agentic coding: parts you already understood but an AI implemented (the premise still holds — you reviewed and reasoned about them), and parts an AI proposed as best practice that you approved at the time without independently deriving them (the premise may not hold — real first-time understanding may never have happened, which means jumping straight to retrieval tests memory of something that was never learned, not something that decayed). Whether you actually knew a given concept before the AI proposed it is a fact only you hold — no doc, ADR, or git history can determine it, and *asking yourself to remember* is unreliable too (today's familiarity with an ADR you've now read several times gets misremembered as having been there from the start). So this isn't solved by memory. Week 1 opens with an **ownership cold-gate** that decides it the honest way: by what you can produce right now, cold, before rereading anything. See [`AI-OWNERSHIP-GAP_MULTI_REVIEW.md`](../AI-OWNERSHIP-GAP_MULTI_REVIEW.md) for the full design discussion.

**The cost: ~11 hours a week for six weeks (≈67 hours).** If that isn't available, there's a 9-hour version below that names exactly what it gives up.

**Three kinds of work run in parallel every week**, and they train different things — see the budget table below. Doing only the one that feels productive is the most common way this fails.

## The honest budget

**~11 hrs/week (≈67 total, including a 1-hour Week 0).** The earlier "9 hrs/week" figure did not survive arithmetic: at the plan's own bar of 25 minutes per problem, 8 NeetCode problems is 3.3 hours by itself, before daily Anki or re-solves. A budget you cannot hit is worse than an honest one, because you'll read the shortfall as a personal failure rather than a planning error.

| | Per week | What it covers |
|---|---|---|
| **Repo conceptual** | 2–4h | The question bank, ADRs, architecture summaries. Trains explanation, tradeoff reasoning, your project narrative. *Your differentiator.* |
| **Drills** (standardized) | 3–4h | NeetCode problems and re-solves. Trains algorithm speed under a clock. *Repo prep cannot substitute — see "Honest routing".* |
| **Simulation** | 1–4h | Mocks, timed design. Trains delivery under observation. |
| **Anki** | ~1.5h | 15 min/day, 6 days. **Tracked outside the streams** — it's a daily habit, not a session, and burying it inside Drills is what made the old budget lie. |
| **Weekly review** | 0.5h | See below. Not optional; it's where the error log turns into next week's plan. |

### If you genuinely only have 9 hours/week

That's 55 hours, so **12 hours have to come out** — and there is no painless way to do it. Trimming a little from everything gets you to about 10.4 hrs/week, not 9. Here is a set of cuts that actually reaches the number:

| Cut | Saves | What it costs you |
|---|---|---|
| Anki to 10 min/day | 3h | Slower deck maturation; the ≥85% retention bar gets harder |
| Drills to 6 problems every week (6·6·6·6·6·4 = **34**) | 2.5h | Below the 40–50 bar. Algorithm speed is the signal you're sacrificing |
| Repo conceptual to 2h from week 2 onward | 5h | Less depth on the question bank; fewer [ALT] alternatives tables |
| Drop mock #3 (the 45-min live coding mock **plus its debrief**) | 1.5h | One less rep under observation — the most painful cut here |
| **Total** | **12h** | **≈55h, ~9 hrs/week** |

**Then mark "Coding" and "Conceptual depth" as "not yet" in the readiness rubric unless you clear those bars anyway.** The point of a rubric is that you don't get to move the bar because you ran out of time. Cutting scope explicitly beats missing a budget silently — but it is still cutting scope, and the plan won't pretend otherwise.

### The one hour that moved (2026-07-22)

The AI-collaboration round in week 4 costs 1 hour. It is **funded from Repo conceptual, not Drills** — week 4 goes repo conceptual 3h→2h, simulation 2h→3h. Total budget unchanged.

Two rejected alternatives, recorded so the reasoning doesn't have to be re-derived:

- **Cutting Drills (NeetCode).** Proposed at 30–40% during review and withdrawn. This plan sits at 40 problems against its own stated pass bar of 40–50. Cutting below your own rubric on a gate that verifiably still exists, in order to fund a round type that is real but not yet universal, trades a known gate for a speculative one. Coding rounds have been *added to*, not replaced.
- **Adding the hour to the total.** The budget already survived one honest-arithmetic pass. Growing it silently is how it becomes fiction again.

What the hour costs: architecture summary #3. Named, not hidden — see week 4.

---

## Week 0 — Before you start (60 min, once)

Three things to write tonight. Skipping them is the most common way a plan like this quietly fails.

1. **Competency list.** You already have one: the **readiness rubric** at the bottom of this document. Read it *now*, not in week 6. It defines what "ready" means in testable terms, and every week's work should visibly move a rubric row. Score yourself against it honestly in week 1 to get a baseline — you cannot see progress without one.
2. **Error log.** [`error-log.md`](error-log.md) — **it now exists as an actual file; open it and add the first row in week 1.** Until 2026-07-22 this was a concept in a document rather than an artifact on disk, which is the most common way the highest-leverage part of a plan quietly never happens. Every entry: `DATE | What I got wrong | What I thought was true | What's actually true | Why I made this error | Route | Confidence before`. (`Route` — added 2026-08-01 — distinguishes decayed retrieval from never-encoded; see `error-log.md`.) The *why* column is the point — a miss that becomes an Anki card preserves the *fact* but never fixes the *misconception*. Both go in.
3. **Implementation intention.** Write the literal sentence: *"After [something I already do every day], I will do [repo conceptual / drills / simulation] at [place]."* Motivation is not a plan. Also fix your stuck-rule now: **if blocked >10 minutes, write the error-log entry before looking anything up.**

**Sleep floor: 7–8 hours, non-negotiable, especially weeks 3 and 6.** Sleep loss before study impairs encoding; sleep loss after impairs consolidation. Cutting sleep to add study hours is a net loss, and it is the single most common self-inflicted wound in a 6-week push.

---

## Week-by-week

*The hours below cover that work type only. **Anki (15 min/day) and the weekly review (30 min) run outside them**, every week. Problem counts total **40** across six weeks (8·8·6·8·6·4), which lands at the floor of the 40–50 bar. That is what actually fits at 25 minutes per problem. Add more only if you are genuinely finishing early — not by compressing time-per-problem, which defeats the point.*

***Re-solves are capped at 2 problems (~40 min) per week.*** *In the 3-hour Drills weeks, six new problems consume 2.5h and only one re-solve fits — do one. An uncapped "re-solve your misses" is how a bounded week quietly becomes an unbounded one.*

### Week 1 — Baseline + foundations
- **Repo conceptual (4h): the ownership cold-gate runs first (60 min), before you open any ADR.** For each of the four core ADRs (0008, 0009, 0013, 0016), attempt cold — from memory alone, nothing open — to state the mechanism, the failure mode it prevents, and one rejected alternative. Reading first would contaminate this: a freshly-reread ADR feels "known" whether or not it actually is (the fluency illusion). Rate each item on four axes (legend and format in `question-bank.md`'s header): **P**rior exposure, **O**rigination, **C**urrent cold ability, **C**laim strength. **Current cold ability is what routes you** — the other three only affect how you *word* the claim later, never whether you need more study:
  - `defends` (≥70% of the answer-pointer essentials, unaided, names the invariant/failure mode, gives one rejected alternative when relevant) → you're in Track A for this item, continue below.
  - `recognizes` (partial, no real reconstruction) → **B-lite** (25 min): 8 min re-read the ADR · 7 min self-explain · 7 min blank-page retry · 3 min compare/log.
  - `blank` → **B-full** (50 min): 15 min worked-example re-read · 15 min completion-problem/partial retry · 15 min blank attempt · 5 min compare/log.

  **Funding rule:** re-encoding time comes out of this week's remaining Repo-conceptual time — drop [ALT]-table depth first. It never comes out of Drills; NeetCode already sits at the floor of its own 40–50 problem pass bar (see the rejected 30–40% Drills cut below), and trading a verified gate for a speculative one is the wrong trade twice over. **If total re-encoding time across the plan exceeds 4 hours, mark `Conceptual depth` "not yet" on the rubric rather than silently absorbing the cost** — same rule the plan already applies to the Coding row in week 6.

  *Then, for whatever routed Track A:* read the four core ADRs *as an outsider*, write a one-page architecture summary from memory, then diff it against the docs. Answer question-bank sections 1 and 4 aloud, ungraded — this is your **baseline pass**. *(Defer the campaigns/profiles/engines READMEs to week 2 — this week is already at the edge of what fits.)*
- **Drills (4h):** NeetCode: arrays & hashing + two pointers (**8 problems**, medium-weighted). Separately, set up Anki with the starter decks (below) and start the daily 15 min.
- **Simulation (1h):** **Record yourself** answering Q1.1 and Q4.1 — these two only; this is the baseline *recording*, distinct from the ungraded baseline pass above. Listen back. Note filler, missing structure.
- **Checkpoint:** baseline pass done · Q1.1/Q4.1 recorded · rubric scored for the first time · 8+ problems solved · architecture summary written · Anki streak ≥3 days.

### Week 2 — Concurrency + data modeling
- **Repo conceptual (3h):** Skim the campaigns/profiles/engines READMEs. Question bank sections 2 and 3 aloud (16 questions). For 3 of the [ALT] questions, write the alternatives table from memory first, then check the ADR. Write architecture summary #2: "how a profile write stays correct under concurrency" (1 page, no peeking).
- **Drills (4h):** NeetCode: sliding window + stack + binary search (**8 problems**). **Re-solve 2 of week 1's misses from scratch** — a failed problem left for four weeks has decayed to nothing; catch it while the trace is still there.
- **Simulation (2h):** One self-timed system design run (45 min): "design a webhook ingestion pipeline" (Q1.5) on a whiteboard/Excalidraw, full artifact.
- **Checkpoint:** 16 questions answered aloud · 2 written summaries · 16+ cumulative problems · week 1 misses re-solved · 1 timed design artifact.

### Week 3 — Distributed systems deep week
- **Repo conceptual (4h):** Section 4 (reliability) — every question aloud, and for 4.2/4.5/4.9 *draw the crash windows* on a timeline. Re-derive the outbox and claim state machines from scratch on paper. **Before checking each answer, write your confidence 0–100%.** Then grade against the answer pointers: a miss = an error-log entry *and* an Anki card.
- **Drills (3h):** NeetCode: linked list + trees (**6 problems** — repo conceptual is heavy this week). Re-solve 1 of week 2's misses.
- **Simulation (2h):** Mock #1 (peer, or interviewing.io/Pramp-style): **system design**, ask for the "campaign sender" or any queue-heavy prompt. Debrief in writing. **Then, 15 min: build next week's answer key.** Have an agent implement a task *in your own domain* — a tenant-scoped write path, a retryable job handler. List the invariants it must satisfy, note which it actually violated, **write the key down and close it.** You have ground truth because you built the real thing. *(Alternative: a real PR whose defects were found later.)* Building it a week early is deliberate — it makes next week's review genuinely cold instead of a memory test.
- **Checkpoint:** section 4 complete with confidence ratings logged · crash-window diagrams drawn · mock #1 done + written debrief · answer key written and closed · 22+ problems.

### Week 4 — Security, testing, breadth vocabulary
- **Repo conceptual (2h):** Sections 5 and 6 aloud, with confidence ratings. Do the external-comparison gap list (see `external-comparison.md` → the **"SD component vocabulary"** row, marked *Better drilled elsewhere*): pick the 3 weakest (typically: consistent hashing, sharding/partitioning strategy, cache invalidation, consensus/leader election). **70 min reading them as case studies** — for each, where it was actually used, what it cost, and where it failed; self-explain rather than skim. Then **20 min sources-closed**: sketch a contrasting-case table — *when you'd reach for it, when you deliberately wouldn't, what breaks if you pick wrong* — check it, and log the misses.

  *That 20-minute table is a **comprehension check**, not the retrieval that makes this stick. Reconstructing something you read an hour ago mostly tests working memory. **The real retrieval is scheduled for week 6**, after some forgetting.* *(Summary #3, "tenant isolation as an invariant", is **cut** — see the hour reallocation note below. Of the three from-memory summaries it had the lowest marginal return, and the invariant is already covered in question-bank §5.)*
- **Drills (4h):** NeetCode: heaps + intervals + greedy (**8 problems**). Re-solve 2 of week 3's misses. (Your Anki deck now includes the week-3 miss cards.)
- **Simulation (3h):** Timed design run #2 on a *non-repo-shaped* prompt you've never built: news feed or chat system (from Hello Interview / ByteByteGo lists) — tests transfer, not recall. **Plus the AI-collaboration round (1h, new):** three steps, and the order is the whole point.

  1. **The answer key was built last week** (week 3, 15 min — see below). Don't re-read it.
  2. **Review cold (45 min).** Post-quality review, as you'd actually write it.
  3. **Grade against the key (15 min).** Count hits, misses, **and false positives** — things you flagged that weren't defects.

  Both numbers matter. Recall alone is gameable by flagging everything; a reviewer who raises twenty concerns to catch two is not a reviewer anyone wants. Misses go in `error-log.md` with the *why* — "I checked behaviour, not the invariant" is the most common and the most useful entry you'll write this week.
- **Checkpoint:** 3 gap topics with a **from-memory contrasting-case table**, checked and misses logged · mock-quality design artifact on foreign territory · AI-code-review written with invariant findings · 30+ problems.

### Week 5 — Operations + behavioral + integration
- **Repo conceptual (3h):** Sections 7 and 8 aloud. Write the five STAR stories (8.1, 8.2, 8.4, 8.5, 8.6) as bullet skeletons — never scripts. **Add two more skeletons from the AI-collaboration table in `role-and-evidence.md`:** (a) the delegation boundary — what you hand off, what you verify, what you never outsource; (b) the time a model was confidently wrong and you caught it. Story (b) is the one an over-reliant candidate cannot produce, which is exactly why it gets asked. Practice the 5-minute architecture pitch (Q1.8) three times, cutting it to 4 minutes. Prepare the "ideal vs shipped" answer (Q2.9): rehearse defending the thrown-typed-errors reality against the Reader/Result ideal without sounding like you abandoned rigor.
- **Drills (3h):** NeetCode: graphs + 1-D DP intro (**6 problems**). Re-solve 1 of week 4's misses.
- **Simulation (3h):** Mock #2: **behavioral + project deep-dive** (a peer grills you on your own system for 45 min, hostile-skeptic mode: "why not just use SQS/Postgres/Temporal?"). Mock #3: one live coding mock (45 min).
- **Checkpoint:** 5 STAR skeletons written · pitch ≤4.5 min · mocks #2–3 done with debriefs · 36+ problems.

### Week 6 — Simulation + spaced review
- **Repo conceptual (2h):** Re-answer the 10 questions you graded worst across weeks 1–5 — **and the ones where your confidence most exceeded your score**, which are the more dangerous set. **Redraw the week-4 gap-topic contrasting-case table from memory** — two weeks of forgetting is what makes this the retrieval that counts, as opposed to week 4's same-day check. Final pass on the readiness rubric.
- **Drills (3h):** Mixed timed sets: two 45-min sessions of 2 problems each, random category (interview conditions — no hints, talk aloud). Plus **up to 2** final re-solves on the highest-priority remaining misses. Anything still failing after that keeps **Coding** at "not yet" in the rubric — you don't get to clear the row by running out of weeks.
- **Simulation (4h):** Full loop simulation: 1 system design mock **on a foreign, never-seen prompt** + 1 coding mock + 1 behavioral, ideally same week, different days. Written debrief each.
- **Checkpoint:** readiness rubric scored honestly · full-loop simulation complete · 40 problems total · up to 2 final re-solves done, with any still-failing problems recorded and **Coding** marked "not yet".

---

## Weekly review (30 min, end of each week)

Not new material. Four things:

1. **Read the error log for *patterns*, not entries.** Three entries about the same misconception is a curriculum item, not three mistakes.
2. **Check calibration.** Where did confidence most exceed performance? That gap is your syllabus for next week — it's where you don't know that you don't know.
3. **Prune Anki.** If reviews exceed 20 min/day, the deck is wrong. Cut anything you could cheaply look up.
4. **Keep/cut audit.** For each artifact this plan has you making — summaries, diagrams, debriefs, STAR skeletons, timed logs, decks — ask: *has it improved my performance, and does it cost less than it returns?* If no, stop making it. The plan serves the prep, not the other way round.

---

## Spaced repetition (all six weeks)

Anki, 15 min/day, 5+ days/week. Decks:

1. **Curated external decks** (start here, prune aggressively): a CS-fundamentals deck covering Big-O, core data structure ops/complexities, OS/networking basics (e.g., the "CS fundamentals"/tech-interview decks on AnkiWeb — pick one, don't hoard), plus a SQL-vs-NoSQL/system-design-vocabulary deck.
2. **Self-made cards** — the highest-value deck. Add a card for: every question-bank answer pointer you missed, every NeetCode problem whose *trigger* you failed to recognize ("monotonic stack when…"), Mongo specifics (partial index semantics, E11000 behavior, `$setOnInsert`, transaction limits), BullMQ/Redis vocabulary (stalled jobs, job states, concurrency options), HTTP/auth (JWT vs session, CORS, OAuth flows).
3. Rule: a card you can't answer in 10 seconds gets rewritten or split. Cards are for *recall atoms*, not concepts — concepts live in Repo conceptual.

---

## Honest routing: where repo-based prep loses (use the standard tools)

This package's question bank trains **explanation and judgment**. Four interview signals it cannot train, and what to use instead:

| Signal | Why repo prep fails | Use instead | Cadence & success bar |
|---|---|---|---|
| **Algorithm speed under pressure** | Nothing in a CRUD-plus-queues production codebase exercises binary-search-on-answer, DP, or graph traversal under a 25-min clock. Production code optimizes for clarity, not asymptotics. | **NeetCode 150** (Blind-75-first ordering), category by category as scheduled above. LeetCode for company-tagged sets in the final week before a real loop. | 40–50 problems in 6 weeks, ~70% medium. Bar: solve an unseen medium in ≤25 min with working code + complexity analysis, talking aloud. |
| **Recall atoms** (complexities, definitions, command/API trivia) | Reading your own ADRs re-recognizes; interviews demand *production* of facts from a cold start. Recognition ≠ recall — only testing-effect repetition builds the latter. | **Anki** with the decks above. | 15 min/day, ≥5 days/wk. Bar: mature-card retention ≥85%. |
| **Standard system-design vocabulary and canonical problems** | The repo teaches one architecture deeply. Interviewers calibrate on the canon (rate limiter, URL shortener, news feed, chat, notification fan-out) and on shared vocabulary (consistent hashing, CDC, cell-based isolation) you didn't need at this scale. | **System Design Primer** for vocabulary; **Hello Interview / ByteByteGo** problem walkthroughs (ByteByteGo & Grokking are paid — see external-comparison.md); one *foreign* timed design in weeks 4 and 6. | 2 canonical problems studied + 2 attempted cold. Bar: complete a foreign prompt's full artifact (requirements → estimates → API → data → deep-dives) in 45 min. |
| **Behavioral recall under stress** | Knowing your stories ≠ retrieving the right one in 5 seconds when asked "tell me about a conflict." | STAR skeletons (week 5) + **Tech Interview Handbook's behavioral question list** as the drill bank; optionally an Anki deck of story-name → 3 bullets. | 5 polished stories mapped to ~20 standard questions. Bar: any standard behavioral question → correct story chosen and delivered in <3 min without notes. |
| **AI-collaboration judgment** *(added 2026-07-22)* | Reading your own ADRs trains none of it, and neither does any question bank. 2026 loops probe it directly — AI-permitted coding rounds, "how did you use AI" take-homes, PR-review-of-agent-output rounds. These are **additive to** the traditional rounds, not replacements. | Week 4's AI-code-review round + the `role-and-evidence.md` AI-collaboration table + the two week-5 STAR skeletons. | Bar: on a PR whose defects are **known in advance**, find ≥2 of them in 45 min with ≤1 false positive; state the delegation boundary unprompted in <2 min. *Weakest-evidence row in this table — see the caveat under the rubric.* |

What repo prep **wins** at — and standardized banks can't provide: a real production narrative with money-critical correctness decisions, honest failure stories, and artifacts (ADRs, runbook, pinned tests) you can walk through. Lead with it in project deep-dives; lean on the standard tools for everything above.

---

## Readiness rubric (this is your competency list — read it in week 0, score it in week 1 and week 6)

Pass = every row at "ready". Any "not yet" extends that stream by a week.

| Signal | Ready looks like | Evidence |
|---|---|---|
| Architecture pitch | ≤5-min walkthrough, unprompted coverage of tenancy, ingestion, sends, metrics; concedes both known gaps before being asked | Recording, week 5–6 |
| Conceptual depth | 10 randomly drawn question-bank items: 8+ hit the answer-pointer essentials without notes | Self-grade sheet |
| Transfer | A never-seen design prompt produces a complete 45-min artifact with explicit tradeoffs | Week 4 & 6 artifacts |
| Coding | Unseen LeetCode medium in ≤25 min, talking aloud, correct + complexity stated, 3 of last 4 attempts | Timed logs |
| Recall | Anki mature retention ≥85%; core complexities/definitions instant | Anki stats |
| Behavioral | 5 STAR stories; any of ~20 standard prompts mapped to one in <5s | Mock #2 + drill |
| AI-collaboration judgment | On a PR with **known ground truth**: ≥2 of the known invariant defects found in 45 min, **with ≤1 false positive** (a "defect" that isn't one). Delegation boundary stated unprompted in <2 min | Week 4 artifact — answer key written *before* the review, findings graded against it |
| Failure-mode fluency | Can diagram outbox/claim/CAS crash windows from a blank page and name each residual | Week 3 diagrams |
| Calibration | Confidence ratings track actual scores within ~15 points; no category where you're systematically overconfident | Confidence log, weeks 3–6 |
| Simulation | Full mock loop completed; debriefs show no repeated failure pattern from earlier mocks | Week 6 debriefs |

### Caveat on the ownership-tag mechanism (added 2026-08-01)

The four-axis tags in `role-and-evidence.md` and `question-bank.md` are **self-tagged only** — never inferred by an AI from an ADR's prose or its git history, because whether you knew something before it was proposed is a fact only you hold. The `Current cold ability` axis is the one exception to "self-report is unreliable": it isn't a memory question, it's a right-now performance result (§8/§10 of the framework — route by present-tense cold attempt, never by recollection of the past). If you skip the cold-gate for an item and later find yourself unable to defend it, treat that discovery exactly like any other error-log entry whose `why` is "I never actually encoded this" — see `error-log.md`.

### Caveat on the AI-collaboration row

**This row rests on weaker evidence than every other row in the rubric.** The role findings behind this plan's second pass came from hard data — 180M job postings, Stanford's employment series, an NBER firm survey. The claim that 2026 loops contain AI-review and AI-permitted rounds came from trade press and interview-coaching sites, parties with an incentive to say the interview changed. No hiring data was found establishing how common those rounds actually are.

It is kept anyway on a cost argument, not an evidence argument: the prep is one hour, it reuses code-review judgment you already have, and the *verbal* probe ("so how do you use AI?") is near-universal and cheap to fail regardless of whether the formal rounds are. That is a bet, and it is labelled as one.

**If you want to cut something, cut this row first** — keep the two week-5 STAR skeletons, drop the review round. That preserves the answer to the common probe and costs you only the artifact behind it.

## Weekly time audit (keep yourself honest)

Log actual hours per stream weekly. If Drills repeatedly starves (the common failure — conceptual reading feels productive, drilling feels bad), swap the order: drills first in every session, reading second.

---

## Where the framework yields

> **Framework alignment** (audit trail — not needed to run the plan). This is a **Track A (Reactivate)** instantiation of [LEARNING-SYSTEM.md](../../learning-system/LEARNING-SYSTEM.md): existing competence that needs to become accessible under pressure. Track A's binding constraints are **retrieval** and **calibration** — which is why testing is the study method from day one and why confidence ratings appear throughout. The framework has authority over *method*; this plan has authority over *what a senior backend loop actually demands*.
>
> Naming: this plan's three **work types** are concurrent activities. They are unrelated to the framework's **Tracks**, which are learner starting states. Different axis, deliberately different word.
>
> **Where this instantiation is mixed-track, not pure Track A.** A repo built partly via agentic coding can leave a single "Track A" learner with real Track B pockets — items an AI proposed and the learner only approved, never independently derived. The framework now names this in §2 and §10 (added 2026-08-01); this plan's response is the Week 1 ownership cold-gate above, which routes *per item*, not per effort.
>
> **Why Week 0 has three items and not the framework's three.** Framework §3 asks for a competency list, a **prerequisite sketch**, and an error log. The prerequisite sketch exists to stop a learner studying above their level — a Track B and C problem. You already have the prerequisites; that is what "reactivate" means. What Track A actually fails on is showing up consistently under deadline pressure, so the sketch is replaced with an implementation intention (L0). If you find yourself repeatedly blocked by missing fundamentals, that assumption was wrong — go build the sketch.

The framework is general learning science; this plan encodes what a senior backend loop actually tests. Four places the plan deliberately does something the framework would otherwise discourage, and why:

- **Artifacts from day one, against §11's "start tiny."** The framework says produce three artifacts and add nothing for two weeks. This plan mandates a baseline recording, two architecture summaries, an alternatives table, and a design artifact inside weeks 1–2. That looks like a direct violation, and the distinction matters: **§11's target is artifacts that *organize* practice — note systems, card decks, dashboards — which displace retrieval while feeling productive. These artifacts *are* the retrieval.** An architecture summary written from memory is blank-page recall. A timed design artifact is the exam itself.

  So the line doesn't let anything through. A practice artifact qualifies only if it meets all three: **produced under test-like constraints** (from memory, or timed), **checked immediately against a reference**, and **carrying no ongoing maintenance cost**. Anything you have to keep tidy, re-organize, or migrate has failed the third test and is exactly what §11 is about.

  Honest weak case: the week-1 baseline recording doesn't fully qualify — it's a calibration instrument rather than retrieval practice. It earns its place by being *one* recording that establishes a baseline you can't otherwise see, and it should not become a habit of recording everything.
- **Blocked practice in weeks 1–5.** The framework prefers mixing problem types to train method selection. But it also says not to mix before baseline competence — so NeetCode runs blocked by category through week 5, and week 6 goes fully mixed and timed. That is the framework's own rule, correctly applied.
- **Heavy volume on a deadline.** The framework optimizes for durable learning; this plan optimizes for peak performance on a known date. Some of the week-6 taper is deliberately about accessibility rather than long-term retention.
- **Recognition-heavy source material.** Re-reading your own ADRs is low-value by framework standards. It is retained only as *input* to a from-memory reconstruction — never as the study method itself.

Where the framework does **not** yield: no plan is valid without delayed retrieval, analyzed errors, and a calibration check. Those were added above, not negotiated away.

---

## Sign-off record

### Third pass — 2026-08-01 (agentic-coding ownership gap)

Audited after the user flagged that the repo was built partly via agentic coding, breaking the plan's "you already know this" premise for an unknown slice of the content. Two-stage multi-model review: Stage 0 signed off the fix plan itself ([`PLAN-SIGNOFF_MULTI_REVIEW.md`](../PLAN-SIGNOFF_MULTI_REVIEW.md)), Stage 1 designed the mechanism ([`AI-OWNERSHIP-GAP_MULTI_REVIEW.md`](../AI-OWNERSHIP-GAP_MULTI_REVIEW.md)). Panel: Claude (lead) · GPT-5.2/Codex · Gemini 3.1 Pro High (Antigravity).

**The user's own hypothesis — "only the timeline changes" — was tested and rejected by both external legs independently.** Three things change: the *method* for flagged items (present-tense re-encoding via Track B, not just more Track A hours), the *interview claim* (a design you can't defend cold and never originated can't be worded as "I designed" even once you understand it), and only as a consequence, the timeline.

| Change | Why |
|---|---|
| Week 1 opens with an ownership cold-gate (60 min, before ADRs are reread) | Reading first contaminates a same-day encoding check with the fluency illusion; both legs independently cited the framework's own L9/L5 warnings for this |
| Four-axis self-tagging (prior exposure / origination / current cold ability / claim strength), routing on `current cold ability` only | Provenance and encoding depth are different things — an AI-proposed idea the user grilled for days is well-encoded; a user-requested feature whose implementation details were rubber-stamped isn't. Routing on provenance alone would misroute both |
| Track-B (B-lite/B-full) re-encoding funded from Repo-conceptual breadth, never Drills | Matches this file's own prior precedent: a Drills cut was proposed and explicitly withdrawn in an earlier round for trading a verified gate for a speculative one |
| `[DYD]` questions relabeled `[EVAL]`/`[ADOPT]` in question-bank.md when claim strength isn't `designed` | Makes the honesty fix visible at the point of use instead of a metadata system nobody checks |
| No AI-inferred classification of real content | Locked in at Stage 0: only the user knows what they knew before an AI proposed something; an AI-run "audit" would be provenance-by-proxy, and would perform the exact diagnostic the learner is supposed to do themselves |

**Rejected during review:** having the panel classify real ADRs/evidence rows/questions by provenance now, to save the user the work later. Both legs and the lead agreed this violates the self-tagging constraint and risks a confidently-wrong classification the framework specifically warns against (§14).

### Second pass — 2026-07-22 (upstream inputs re-examined)

Re-audited after a multi-model panel re-established the target role under AI-era market conditions (see [`../ROLES-AND-DELIVERABLES_MULTI_REVIEW.md`](../ROLES-AND-DELIVERABLES_MULTI_REVIEW.md)). Panel: Claude Opus 4.8 (lead, live web research) · Gemini 3.1 Pro High · GPT-5.2/Codex.

**The role did not change** — Senior Backend / Product Platform survived scrutiny and the market moved *toward* it (software engineering resilient at the category level; seniority the strongest protective factor, ICs −9% vs leadership −1.7%; backend complexity valued while frontend commoditizes). So the plan's architecture stands. Four amendments followed from the AI-era findings:

| # | Change | Why |
|---|---|---|
| 1 | `error-log.md` now exists as a real file; Week 0 links it | It was a concept in a document, never an artifact on disk — the most common way the highest-leverage part of a plan quietly never happens |
| 2 | AI-collaboration round added to week 4 (1h) | 2026 senior loops probe it directly; the package trained none of it |
| 3 | Two AI STAR skeletons added to week 5; new Honest-routing row; new rubric row | The new evidence needs a spoken form and a pass bar, or it isn't trained |
| 4 | Hour funded from Repo conceptual (summary #3 cut), **not** Drills | See "The one hour that moved" |

**Rejected during review:** a proposed 30–40% cut to Drills. It would put this plan below its own 40–50 problem bar on a gate that verifiably still exists. The leg that proposed it withdrew it under challenge. Recorded because the reasoning will otherwise be re-litigated.

### First pass

Audited against [LEARNING-SYSTEM.md](../../learning-system/LEARNING-SYSTEM.md) layer by layer, then taken through four review rounds by two independent models (GPT-5/Codex and Gemini 3.1 Pro). Both signed off APPROVED. What the audit changed:

| Layer | Finding | Fix |
|---|---|---|
| **L1** goals | Readiness rubric existed but sat at the end, unread until week 6 | Promoted to Week 0 as the competency list; scored in week 1 for a baseline |
| **L8** feedback | "A miss = an Anki card" preserved the fact but never fixed the misconception | Error log with a mandatory *why* column; both the card and the entry |
| **L9** calibration | "Self-grade" and "score honestly" are not calibration | Confidence ratings 0–100% before checking answers, weeks 3–6; new Calibration row in the rubric; week 6 targets the questions where confidence most exceeded score |
| **L6** spacing | Second-pass re-solves waited until week 5 — a 3–4 week gap on *already-failed* items, whose retrieval strength is gone by then | Re-solves start week 2 and run weekly, explicitly capped |
| **L0** foundations | Absent entirely from a 6-week push | Sleep floor, implementation intention, stuck-rule — all in Week 0 |
| **L3** load | Week 1 stacked ADRs + READMEs + summary + question bank + 8–10 problems + Anki setup | READMEs deferred to week 2 |
| **L11** artifact creep | Artifacts accumulated with no keep/cut test | Added to the weekly review, with a three-condition test for what counts as practice vs. bureaucracy |
| **Naming** | This plan and the framework both said "Track A/B/C" meaning different things — a reader could conclude Track A means "skip LeetCode" | Renamed to Streams here; Track reserved for learner starting states |

**The budget was the hardest finding, and it was pre-existing.** Both models independently did arithmetic the plan had never had done to it: at the plan's own 25-min-per-problem bar, Drills was asking for ~5.75 hours inside a 3-hour slot, and the headline "9 hrs/week" was fiction once Anki and the weekly review were counted. It is now ~11 hrs/week with the numbers shown, plus a reduced-scope variant that actually reaches 9 by naming what it cuts. A budget you cannot hit reads as personal failure rather than a planning error, which is why this mattered more than it looks.
