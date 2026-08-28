# 6-Week Study Plan — Senior Backend / Product Platform Engineer

**Tonight: 60 minutes.** Read the readiness rubric at the bottom of this file, then do the three Week 0 tasks. Then stop. Everything else starts tomorrow.

**The premise.** You already know this material — you proved that by building the system. What you can't reliably do yet is produce it on demand, out loud, with a clock running. So this plan *tests* you from day one rather than teaching you. Re-reading your own docs is not the study method here; it's raw material for recall, nothing more.

**One qualification.** "You already know this" assumed the repo was hand-written. Part of it was built with agentic coding — some of it you understood and an AI implemented; some of it an AI proposed and you approved without deriving it yourself. For the second kind there may be nothing to reactivate. You can't tell which is which from memory (a reread ADR feels known whether or not it is), so Week 1 opens with a cold-gate that decides it by what you can produce right now.

**The cost: ~11 hours a week for six weeks (≈67 hours).** If that isn't available, there's a 9-hour version below that names exactly what it gives up.

**Three kinds of work run in parallel every week**, and they train different things — see the budget table below. Doing only the one that feels productive is the most common way this fails.

## The budget

**~11 hrs/week (≈67 total, including a 1-hour Week 0).** At 25 minutes per problem, 8 NeetCode problems is 3.3 hours by itself, before Anki or re-solves — which is why the earlier 9-hour figure didn't hold.

| | Per week | What it covers |
|---|---|---|
| **Repo conceptual** | 2–4h | The question bank, ADRs, architecture summaries. Trains explanation, tradeoff reasoning, your project narrative. *Your differentiator.* |
| **Drills** (standardized) | 3–4h | NeetCode problems and re-solves. Trains algorithm speed under a clock. *Repo prep cannot substitute — see "Where repo prep loses".* |
| **Simulation** | 1–4h | Mocks, timed design. Trains delivery under observation. |
| **Anki** | ~1.5h | 15 min/day, 6 days. **Tracked outside the three work types above** — it's a daily habit, not a session, and burying it inside Drills is what made the old budget lie. |
| **Weekly review** | 0.5h | See below. Not optional; it's where the error log turns into next week's plan. |

### If you genuinely only have 9 hours/week

That's 55 hours, so 12 have to come out. Trimming a little from everything doesn't get there; these cuts do:

| Cut | Saves | What it costs you |
|---|---|---|
| Anki to 10 min/day | 3h | Slower deck maturation; the ≥85% retention bar gets harder |
| Drills to 6 problems every week (6·6·6·6·6·4 = **34**) | 2.5h | Below the 40–50 bar. Algorithm speed is the signal you're sacrificing |
| Repo conceptual to 2h from week 2 onward | 5h | Less depth on the question bank; fewer of the question bank's alternatives tables |
| Drop mock #3 (the 45-min live coding mock **plus its debrief**) | 1.5h | One less rep under observation — the most painful cut here |
| **Total** | **12h** | **≈55h, ~9 hrs/week** |

**Then mark "Coding" and "Conceptual depth" as "not yet" in the readiness rubric** unless you clear those bars anyway. Cutting scope explicitly beats missing a budget silently — but it is still cutting scope.

---

## Week 0 — Before you start (60 min, once)

Three things to write tonight. Skipping them is the most common way a plan like this quietly fails.

1. **Competency list.** You already have one: the **readiness rubric** at the bottom of this document. Read it *now*, not in week 6. It defines what "ready" means in testable terms, and every week's work should visibly move a rubric row. Score yourself against it honestly in week 1 to get a baseline — you cannot see progress without one.
2. **Error log.** Open [`error-log.md`](error-log.md) and read the column legend. The first row goes in during week 1. The *why* column is the point — a miss that only becomes an Anki card preserves the fact but never fixes the misconception. Both go in.
3. **Implementation intention.** Write the literal sentence: *"After [something I already do every day], I will do [repo conceptual / drills / simulation] at [place]."* Motivation is not a plan. Also fix your stuck-rule now: **if blocked >10 minutes, write the error-log entry before looking anything up.**

**Sleep floor: 7–8 hours, non-negotiable, especially weeks 3 and 6.** Sleep loss before study impairs encoding; sleep loss after impairs consolidation. Cutting sleep to add study hours is a net loss, and it is the single most common self-inflicted wound in a 6-week push.

---

## Week-by-week

*The hours below cover that work type only. **Anki (15 min/day) and the weekly review (30 min) run outside them**, every week. Problem counts total **40** across six weeks (8·8·6·8·6·4), which lands at the floor of the 40–50 bar. That is what actually fits at 25 minutes per problem. Add more only if you are genuinely finishing early — not by compressing time-per-problem, which defeats the point.*

***Re-solves are capped at 2 problems (~40 min) per week.*** *In the 3-hour Drills weeks, six new problems consume 2.5h and only one re-solve fits — do one. An uncapped "re-solve your misses" is how a bounded week quietly becomes an unbounded one.*

### Week 1 — Baseline + foundations
- **Repo conceptual (4h): the ownership cold-gate runs first (60 min), before you open any ADR.** For each of the four core ADRs (0008, 0009, 0013, 0016), state from memory alone the mechanism, the failure mode it prevents, and one rejected alternative. Reading first would contaminate this — a freshly reread ADR feels known whether or not it is. Mark each one:
  - `defends` — mechanism, failure mode and a rejected alternative mostly right (≥70%), unaided. Carry on below.
  - `recognizes` → re-encode first, ~25 min: reread the ADR, self-explain it, retry from a blank page, compare and log.
  - `blank` → re-encode first, ~50 min: the same, with a worked-example read and a partial-completion retry before the blank attempt.

  Re-encoding time comes out of this week's Repo-conceptual budget (drop [ALT]-table depth first), never out of Drills. If re-encoding across the plan passes 4 hours, mark `Conceptual depth` "not yet" on the rubric rather than absorbing it silently. Skipped the gate for an item and later found you can't defend it? That's an error-log row with `Route = never-encoded`.

  *Then, for the ADRs you could defend:* read the four core ADRs *as an outsider*, write a one-page architecture summary from memory, then diff it against the docs. Answer question-bank sections 1 and 4 aloud, ungraded — this is your **baseline pass**. *(Defer the campaigns/profiles/engines READMEs to week 2 — this week is already at the edge of what fits.)*
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

  *That 20-minute table is a **comprehension check**, not the retrieval that makes this stick. Reconstructing something you read an hour ago mostly tests working memory. **The real retrieval is scheduled for week 6**, after some forgetting.*
- **Drills (4h):** NeetCode: heaps + intervals + greedy (**8 problems**). Re-solve 2 of week 3's misses. (Your Anki deck now includes the week-3 miss cards.)
- **Simulation (3h):** Timed design run #2 on a *non-repo-shaped* prompt you've never built: news feed or chat system (from Hello Interview / ByteByteGo lists) — tests transfer, not recall. **Plus the AI-collaboration round (1h):** three steps, and the order is the whole point.

  1. **The answer key was built last week** (week 3, 15 min). Don't re-read it.
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

## Where repo prep loses — use the standard tools

This package's question bank trains **explanation and judgment**. Four interview signals it cannot train, and what to use instead:

| Signal | Why repo prep fails | Use instead | Cadence & success bar |
|---|---|---|---|
| **Algorithm speed under pressure** | Nothing in a CRUD-plus-queues production codebase exercises binary-search-on-answer, DP, or graph traversal under a 25-min clock. Production code optimizes for clarity, not asymptotics. | **NeetCode 150** (Blind-75-first ordering), category by category as scheduled above. LeetCode for company-tagged sets in the final week before a real loop. | 40–50 problems in 6 weeks, ~70% medium. Bar: solve an unseen medium in ≤25 min with working code + complexity analysis, talking aloud. |
| **Recall atoms** (complexities, definitions, command/API trivia) | Reading your own ADRs re-recognizes; interviews demand *production* of facts from a cold start. Recognition ≠ recall — only testing-effect repetition builds the latter. | **Anki** with the decks above. | 15 min/day, ≥5 days/wk. Bar: mature-card retention ≥85%. |
| **Standard system-design vocabulary and canonical problems** | The repo teaches one architecture deeply. Interviewers calibrate on the canon (rate limiter, URL shortener, news feed, chat, notification fan-out) and on shared vocabulary (consistent hashing, CDC, cell-based isolation) you didn't need at this scale. | **System Design Primer** for vocabulary; **Hello Interview / ByteByteGo** problem walkthroughs (ByteByteGo & Grokking are paid — see external-comparison.md); one *foreign* timed design in weeks 4 and 6. | 2 canonical problems studied + 2 attempted cold. Bar: complete a foreign prompt's full artifact (requirements → estimates → API → data → deep-dives) in 45 min. |
| **Behavioral recall under stress** | Knowing your stories ≠ retrieving the right one in 5 seconds when asked "tell me about a conflict." | STAR skeletons (week 5) + **Tech Interview Handbook's behavioral question list** as the drill bank; optionally an Anki deck of story-name → 3 bullets. | 5 polished stories mapped to ~20 standard questions. Bar: any standard behavioral question → correct story chosen and delivered in <3 min without notes. |
| **AI-collaboration judgment** | Reading your own ADRs trains none of it, and neither does any question bank. 2026 loops probe it directly — AI-permitted coding rounds, "how did you use AI" take-homes, PR-review-of-agent-output rounds. These are **additive to** the traditional rounds, not replacements. | Week 4's AI-code-review round + the `role-and-evidence.md` AI-collaboration table + the two week-5 STAR skeletons. | Bar: on a PR whose defects are **known in advance**, find ≥2 of them in 45 min with ≤1 false positive; state the delegation boundary unprompted in <2 min. |

What repo prep **wins** at — and standardized banks can't provide: a real production narrative with money-critical correctness decisions, honest failure stories, and artifacts (ADRs, runbook, pinned tests) you can walk through. Lead with it in project deep-dives; lean on the standard tools for everything above.

---

## Readiness rubric (this is your competency list — read it in week 0, score it in week 1 and week 6)

Pass = every row at "ready". Any "not yet" adds a week of that kind of work.

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

**If you have to cut a rubric row, cut AI-collaboration's review round first** and keep the two week-5 STAR skeletons. The verbal probe ("how do you use AI?") is near-universal; the formal review round is the part resting on weaker evidence.

## Weekly time audit

Log actual hours per work type weekly. If Drills repeatedly starves (the common failure — conceptual reading feels productive, drilling feels bad), swap the order: drills first in every session, reading second.

---

## What counts as practice, not bureaucracy

This plan has you making artifacts from week 1 — summaries, diagrams, debriefs, timed designs — which §11 of the learning framework this plan derives from ([LEARNING-SYSTEM.md](../../learning-system/LEARNING-SYSTEM.md)) would normally warn against. The line: a practice artifact qualifies only if it is **produced under test-like constraints** (from memory, or timed), **checked immediately against a reference**, and **carries no ongoing maintenance cost**. Anything you have to keep tidy, reorganize, or migrate has failed the third test. The weekly keep/cut audit applies this.

The full alignment audit against the framework and the sign-off record for each review round are in [CHANGELOG.md](CHANGELOG.md).
