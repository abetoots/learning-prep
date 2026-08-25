# Roles & Deliverables — Multi-Model Review

**Date:** 2026-07-22
**Panel:** Claude Opus 4.8 (lead) · Gemini 3.1 Pro High (via Antigravity) · GPT-5.2 (via Codex)
**Scope:** (1) target roles for both learners under AI-era market conditions · (2) the artifact set for each directory · (3) scoped verdict on `learn-cli-README-draft.md` · (4) second pass on `study-plan.md`
**Method authority:** `~/learning-system/LEARNING-SYSTEM.md`

> **Who this is for: Person 1.** It is a decision record — why each file exists and what was argued about. It is written for someone who already works in this field.
>
> **It is not written for Person 2, and handing it to them unfiltered is a mistake.** It contains blunt statements about the entry-level market, including that a pathway they may be counting on has broken. Person 1 should carry the conclusions across in conversation, where questions can be answered, rather than passing along a document that delivers discouraging macroeconomics without any of the "here's what we do about it" that lives in `web-engineer-prep/`.

---

## Executive summary

The panel converged on a finding that reframes the question you asked. You asked whether you can recommend your own path (Udemy + roadmap.sh) to a beginner. The answer is no — **but not because AI made the roadmap wrong. AI removed the slack that was hiding the fact that the roadmap was already wrong.** roadmap.sh is a topic list, and `LEARNING-SYSTEM.md §3.1` has always said goals must be "I can do Y," not "I know about X." Udemy video sits at Passive/Active on the ICAP hierarchy (§4.1) and never withdraws its scaffold (expertise reversal, L2). Both failed the framework in 2019. In 2019 a motivated beginner could absorb that inefficiency because entry-level hiring was forgiving. It is not forgiving now.

That reframing matters because it tells you what to *keep* from your own experience rather than discarding it wholesale.

On roles: **Person 1's target does not change.** The market moved toward your differentiator, not away from it. **Person 2's target changes only cosmetically** — and the panel's central correction is that for a beginner, the role label is a second-order decision. The first-order problem is that the artifact which used to prove a beginner could code — a portfolio app — has been commoditized to approximately zero as a hiring signal. The role didn't die. **The evidence died.**

On artifacts: both directories get *smaller* than instinct suggests. Person 2 ships **three files on day 0**, not a curriculum. The signal problem and the AI-dependency problem are solved by adding *columns to existing files*, not by adding files — this was Codex's contribution and it is the single best idea to come out of the panel.

On `learn`: **DEFER**, unanimously (Gemini opened at KILL and conceded the trigger). It is a genuinely well-designed learning tool that is pointed at the wrong substrate for the next six weeks.

---

## Evidence base

Live data pulled 2026-07-22. Only the lead ran live search in round 1; Gemini answered from training data and disclosed this when challenged, then searched before round 2. Codex was run without web access by design (time-boxed) and reasoned from panel-supplied data.

| Source | Finding |
|---|---|
| **Bloomberry** — 180M global postings, Jan 2023–Oct 2025, ML-classified into 650 titles (updated 2026-06-17) | Market baseline **−8%** in 2025. **Software engineering is resilient** — most SWE titles at or above baseline. **Frontend engineering declined most of any SWE title.** ML engineers **+40%** (after +78% in 2024). ICs **−9%** · managers **−5.7%** · senior leadership **−1.7%**. |
| Bloomberry author's own caveat | "I doubt AI is getting rid of sophisticated frontend work… perhaps it's having an impact on the less complicated work." |
| **Stanford Digital Economy Lab** (Brynjolfsson, Chandar, Chen) | Devs aged 22–25 down **~20%** from late-2022 peak; **~16%** decline in early-career employment across most AI-exposed occupations. |
| **Revelio Labs** | US entry-level postings down **~35%** since Jan 2023 — **across all white-collar work, not just tech.** |
| **NBER w34836** (~6,000 C-suite) | AI had **little to no measurable impact** on employment or productivity in **~90% of firms** over three years. The counterweight to the doom framing. |
| Interview-format reporting (Educative, Course Report, 2026) | Loops weight system behavior, debugging and operational judgment more; raw coding speed less. AI-assisted rounds and "explain how you used AI" take-homes are **additive**, not replacements. |

**The through-line the panel adopted, and it is Bloomberry's own:** the split is not AI-exposed vs. AI-safe. It is **execution vs. judgment.** Creative execution roles fell while creative direction held. ICs fell four times harder than leadership. That single axis predicts everything else in this document.

---

## 1. Roles

### Person 1 — **no change to the role. Change the evidence.**

**Target confirmed: Senior Software Engineer — Backend / Product Platform.** Unanimous.

The market moved *toward* this position. Bloomberry: backend complexity is valued while frontend commoditizes; seniority is the strongest protective factor in the dataset; SWE as a category held. Your `role-and-evidence.md` is an inventory of exactly the work AI is worst at — multi-tenancy invariants, optimistic CAS, crash-window reasoning, recovery philosophy, operating what you built. That is judgment-class work on the execution/judgment axis.

**Do not chase "AI Engineer."** ML engineer postings at +40% are real and tempting. They are also the one cohort with genuine credentials, and you have zero evidence rows for modeling work. Repositioning into it on a six-week runway trades a strong claim for a weak one.

**Refinements the panel added:**

- **Company archetype:** Series A–C product companies where correctness is money-critical — billing, fintech, comms platforms, infrastructure tooling. Not FAANG, where the loop is more algorithm-gated and the ladder is deeper. At <50 engineers the founding/lead-backend framing still holds.
- **One genuine gap: AI-collaboration fluency.** 2026 senior loops probe it — AI-permitted coding rounds, take-homes asking how you used AI, PR-review-of-AI-generated-code rounds. Your package has **zero** evidence rows for this. The irony is that you have the evidence and are throwing it away: you ran a multi-model adversarial review workflow to produce these very artifacts, and `role-and-evidence.md` currently dismisses it ("Multi-model AI review is interesting but is not a substitute for human org influence"). That dismissal is *correct for the Staff claim* and wrong as a reason to leave it unused as senior AI-fluency evidence. Two different claims.

### Person 2 — **Junior Product Engineer (full-stack-leaning, web). But the label is second-order.**

**`frontend-engineer-prep/` should be renamed.** Frontend is the worst-performing SWE title in the largest dataset available, and entry-level frontend is where the commoditization is concentrated. Recommended: **`web-engineer-prep/`** or **`product-engineer-prep/`**.

**But the panel's most important finding is that this rename buys you very little,** and you should know that before you act on it:

Entry-level postings are down ~35% across *all* white-collar work, while SWE as a category is resilient. Decompose that and Person 2's compression is **mostly a level problem, not a role problem**. Relabeling the target from "frontend engineer" to "product engineer" changes the word on the goal, not the barrier. Gemini opened by arguing the pivot was decisive; challenged with the decomposition, it revised to: the pivot survives only because it changes *what Person 2 does on a Tuesday* — owning business logic, data flow, and API integration rather than translating designs into components. That is a real difference, but it is a difference in **practice content**, not in job-title targeting.

**What actually changed for beginners — the panel's central finding:**

> The portfolio app has been commoditized to zero as a hiring signal. Employers now assume a standard CRUD project is AI-generated, because it probably is. The role didn't die; the *evidence* died.

Everything in Person 2's artifact set follows from this.

**Codex's correction, which the panel adopted:** do not jump straight to "manufacture an un-fakeable public signal." That is a month-three problem. **The day-zero problem is §3.4 — a beginner needs a source of worked examples and reference answers, something outside their own head that can tell them they are wrong.** In 2026 the tempting answer is "AI," and §8 says that is exactly where a beginner is most at risk, because they cannot distinguish a good AI answer from a confident wrong one. The first scarce asset is **externally checked correctness**, not public polish.

**Is roadmap.sh + Udemy defensible? Split verdict.**

| Component | Verdict |
|---|---|
| roadmap.sh **as a map** | **Keep.** The dependency graph is intact. HTTP, the DOM, SQL and the request lifecycle did not get automated. |
| roadmap.sh **as a curriculum** | **Reject** — and it was always wrong. It is a topic list; §3.1 requires "I can do Y." It fails L1 independently of AI. |
| Udemy **as worked examples** (§3.4) | **Conditional keep.** Video is a legitimate *encoding* input for a Track B learner who has no mental map of the field yet. |
| Udemy **as the study method** | **Reject.** Passive/Active on ICAP (§4.1); never fades its scaffold (L2 expertise reversal); "tutorial hell" is the named failure. |

Gemini's round-1 position — "actively harmful" — was overstated and it revised. The accurate statement is the one at the top of this document: AI didn't break the roadmap; it removed the slack that hid the fact it was already broken.

---

## 2. Deliverables

### `interview-prep/` (Person 1 — Track A)

| File | Verdict | Rationale |
|---|---|---|
| `README.md` | **Keep** | Orientation. Update the file table after the changes below. |
| `role-and-evidence.md` | **Keep + amend** | Add an **`AI Collaboration Evidence`** section (see below). Not a new file — §11 applies to you too. |
| `question-bank.md` | **Keep** | The retrieval corpus. Untouched. |
| `external-comparison.md` | **Keep** | *Contested — see Debated Items.* One-shot routing decision record, zero maintenance cost. Archive it only when it stops changing what you practice. |
| `study-plan.md` | **Keep + amend** | See §4. |
| `error-log.md` | **ADD — day 0** | The plan mandates it; the file does not exist. §3.3 makes it non-optional, and it is the highest-leverage artifact in the entire system. Columns: `DATE \| What I got wrong \| What I thought was true \| What's actually true \| Why I made this error \| Confidence before answering`. |
| `learn-cli-README-draft.md` | **Keep as a parked design doc** | Not an active artifact. See §3. |

**The `AI Collaboration Evidence` section** (inside `role-and-evidence.md`, ~5 rows, same claim→artifact format as the existing table):
- Where AI is used for critique, test generation, refactoring, design review — and where it is deliberately not.
- **One case where AI was confidently wrong and you caught it.** This is the highest-value row; it is the one a candidate who over-relies cannot produce.
- One PR-style review of AI-generated code, with the invariants you checked.
- The delegation boundary: what you delegate, what you verify, what you never outsource.
- The multi-model adversarial review process behind this package and `LEARNING-SYSTEM.md` — framed as *process rigor*, explicitly **not** as a Staff-influence claim.

A standalone `ai-collaboration.md` earns its existence only if the section becomes too dense to use. Until then it is premature bureaucracy.

### `web-engineer-prep/` (Person 2 — Track B)

**Day 0 — exactly three files.** This is §3's mandated set, and shipping more to a Track B beginner is the named Track B failure mode: planning and tool-shopping before any loop data exists.

| File | Day 0? | Design note — this is where the AI-era adaptation lives |
|---|---|---|
| `competency-list.md` | **Yes** | Tiny "I can do Y" statements, day-sized (§3.1, L12: early wins are the mechanism). **Add a `Proof` column.** That column is where the signal problem lives — it makes the competency list evidence-shaped without adding an artifact. |
| `prerequisite-sketch.md` | **Yes** | Two levels deep, hard stop (§3.2). Track B's binding constraints are sequence (L2) and load (L3). This is the file that prevents "I must learn how the internet works before I write HTML." |
| `error-log.md` | **Yes** | Standard §3.3 columns **plus three AI columns**: `AI used?` · `Did I ask for an answer, or a hint/critique?` · `Could I redo this without AI?`. This operationalizes §8's one metric and its monthly self-test **without a separate `ai-policy.md`**. |

**Earned later, never at day 0:**

| File | Earned when |
|---|---|
| `feedback-sources.md` | Only if §3.4 is not resolvable in one paragraph inside `prerequisite-sketch.md`. **Resolving §3.4 is the true day-0 blocker for Person 2** — name the thing outside their own head that can say they are wrong (a test suite, a compiler, a code reviewer, a graded course, a mentor) before any studying starts. |
| `portfolio-evidence.md` | After ≥2 weeks of loop data, and only once Person 2 can name the concrete signal failure it solves. A ledger — task, artifact path, skills shown, constraints, feedback received, next gap — **not** a showcase plan. |
| review schedule / deck | Week 2 at the earliest (§13), and only if delayed recall is measurably being missed. |
| `study-plan.md` | **Not yet.** Cannot be written until Person 2's real constraints are known (see Open Inputs). |

**Explicitly not created:** `README.md`, `resources.md`, `ai-policy.md`, `projects.md`, `roadmap.md`. Each is a §11 violation at day 0.

**The asymmetry is deliberate.** Person 1 gets six files because Track A's constraint is retrieval and calibration against a rich existing corpus. Person 2 gets three because Track B's constraint is sequence, load, and not quitting. Symmetric artifact sets would be a design error.

---

## 3. `learn-cli-README-draft.md` — verdict: **DEFER**

**Panel:** Codex DEFER · Lead DEFER · Gemini opened KILL, conceded the trigger.

**It is not fake productivity by design.** The panel unanimously agreed the tool encodes the framework correctly: confidence rating before reveal (§9.1, L9), FSRS spacing (L6), an error taxonomy rather than bare correctness (L8, which matters — §L8 notes >38% of feedback interventions make performance *worse*, and bare-correctness feedback is ES ≈ 0.05), provenance discipline, and an AI policy that keeps the model out of answer-generation (§8). The "Why not Anki?" section is honest. The "What it is not" section is unusually disciplined. As a design document it is better aligned to `LEARNING-SYSTEM.md` than most commercial learning tools.

**It is pointed at the wrong substrate.** Its corpus is generated from docs Person 1 wrote themselves. That means it can only train recall of the material Person 1 is *already strongest on*, and cannot touch what `external-comparison.md` identifies as the actual gaps: canonical system-design vocabulary, foreign design prompts, and timed algorithms. It would industrialize the best-covered corner of the package.

**The contradiction neither the lead nor Gemini named, found by Codex:**

> `learn` violates **§3.4**. Person 1's own docs are not an *external* reference answer. §3.4's requirement is that "something outside your own head can tell you you're wrong." For re-onboarding to your own codebase — the tool's stated primary use — that is fine, because the code is the arbiter. For interview prep it silently substitutes self-authored recall for market-shaped feedback.

This also resolves the panel's one live disagreement. Gemini held that the tool converts passive re-reading into active retrieval, which is true and is a real answer to the "recognition-heavy source material" concern at `study-plan.md:162`. Codex's point is orthogonal and both stand: the *retrieval mode* is upgraded; the *reference answer* is still self-authored.

**Ceremony or justified?** Neither, cleanly — and that is the useful answer. It is a legitimate product conflated with an illegitimate study method. The README is written as if those are one thing. They are two projects with different acceptance criteria, and separating them is the actual recommendation.

**The trigger condition** (Codex's, which supersedes the lead's weaker "run markdown for N weeks"). Build only when **all** hold:

1. ≥10 consecutive study days, or 2 calendar weeks, whichever is later;
2. the manual loop has produced ≥30 answered prompts/problems;
3. ≥10 error-log entries with *analyzed causes*, not just misses;
4. **≥3 misses recur specifically because of scheduling, provenance drift, or calibration-tracking overhead** — not because the corpus is weak;
5. external gap work is already running (timed algorithms + canonical design prompts are in the loop);
6. Person 1 can complete this sentence with numbers: *"The CLI removes X minutes or Y recurring errors per week that the markdown loop cannot remove."*

Condition 4 is the load-bearing one. It requires the friction to be of the **exact class the CLI is designed to remove**. "I ran markdown for two weeks and got bored" is avoidance of harder practice wearing a tooling costume — which is precisely the §11 failure mode, and precisely how this project would fail.

Note the trigger deliberately makes **employment status irrelevant.** Gemini's original trigger — "the day Person 1 signs an offer" — is a calendar event, not a learning-system criterion; it conceded this. An unemployed Person 1 who has hit all six conditions may build it. An employed Person 1 who hasn't, may not.

---

## 4. `study-plan.md` — second pass

Upstream inputs held: the role did not change, so the plan's architecture stands. Four amendments follow from the AI-era findings.

| # | Change | Why |
|---|---|---|
| 1 | **Week 0: create `error-log.md` as an actual file**, alongside the competency list and implementation intention. | It is currently a concept in a document, not an artifact on disk. §3.3. |
| 2 | **Add an AI-collaboration round to Stream 3.** One 45-min mock in week 4 or 5: review a flawed, complex PR of the shape an AI agent produces — critique its invariants, tenancy handling, failure modes. Plus one AI-permitted coding rep. | These rounds are now real in 2026 senior loops and the package trains none of it. Reporting indicates they are **additive to** coding rounds, not replacements. |
| 3 | **Fund those hours from Stream 1, not Stream 2.** | Stream 1 is the most over-served stream and the plan itself flags repo re-reading as recognition-heavy (line 162). Stream 2 is already at the floor of its own 40–50 bar. |
| 4 | **Add ~2 evidence rows** to the week-5 behavioral prep covering the AI delegation boundary and the "AI was confidently wrong and I caught it" story. | New `role-and-evidence.md` section needs a spoken form. |

**Explicitly rejected: cutting NeetCode volume.** Gemini proposed a 30–40% cut to Stream 2 and withdrew it under challenge. The plan sits at 40 problems against its own stated pass bar of 40–50; cutting below your own rubric on a gate that verifiably still exists, to fund a round type that is real but not yet universal, trades a known gate for a speculative one. If a bar has to move, move it explicitly and mark the rubric row "not yet" — the plan's own discipline (line 31).

---

## Debated items and final verdicts

| # | Dispute | Positions | Verdict (lead's casting vote) |
|---|---|---|---|
| D1 | Is entry-level frontend "dead"? | Gemini: "pure UI coding is fully automated." Lead: strongest form unsupported. | **Gemini conceded.** Supported claim: AI has commoditized *low-complexity* UI execution; sophisticated state-heavy frontend is intact. The Bloomberry author, who found the decline, declines to draw the strong conclusion. |
| D2 | Does relabeling Person 2's role solve anything? | Gemini: decisive pivot. Lead: mostly a level problem; rename is cosmetic. | **Split, resolved.** Gemini revised. The rename is worth doing but is second-order; the practice-content shift (business logic + APIs over design translation) is what carries the weight. |
| D3 | Cut `external-comparison.md` as §11 bureaucracy? | Gemini: cut. Lead + Codex: category error — §11 targets *maintained* systems that displace retrieval. | **Gemini conceded. Keep it.** Zero maintenance cost; it already paid for itself; it is what stops over-indexing on the repo. |
| D4 | Cut NeetCode 30–40%? | Gemini: cut. Lead + Codex: takes Person 1 below their own bar. | **Gemini conceded. No cut.** Take hours from Stream 1. |
| D5 | `learn-cli` trigger | Gemini: signing an offer. Lead: §11's "name the friction." Codex: name the friction *of the right class*, with thresholds. | **Codex's wins.** Adopted verbatim above. |
| D6 | Does `learn` contradict `study-plan.md:162`? | Lead: yes, it industrializes low-value self-authored material. Gemini: **HELD** — it converts passive re-reading into active retrieval. | **Gemini's HOLD is correct on its own terms; the lead's objection was misaimed.** Codex reframed it correctly as a **§3.4** violation (self-authored reference answer), which is the real defect. Both findings recorded. |
| D7 | Is the beginner's problem "signal" or "feedback"? | Lead: manufacture an un-fakeable signal. Codex: too early — the first scarce asset is externally checked correctness, not public polish. | **Codex's correction adopted.** Signal is a month-3 problem; §3.4 feedback source is the day-0 blocker. This changed `portfolio-evidence.md` from a day-0 file to an earned one. |

No dispute required escalation to you.

---

## Status — applied 2026-07-22

All panel recommendations have been implemented.

| # | Action | Status |
|---|---|---|
| 1 | `interview-prep/error-log.md` created, with confidence-before column | ✅ |
| 2 | `AI Collaboration Evidence` section added to `role-and-evidence.md`; the Staff-gap dismissal now cross-references it as a *separate* claim | ✅ |
| 3 | Four `study-plan.md` amendments applied (Week 0 links the real file · week-4 AI review round · week-5 STAR skeletons · new Honest-routing and rubric rows), plus an "hour that moved" note recording the rejected alternatives | ✅ |
| 4 | `interview-prep/README.md` file table updated; AI-era second-pass section added | ✅ |
| 5 | `learn-cli-README-draft.md` marked **DEFERRED** with the six-condition trigger at the top | ✅ |
| 6 | `frontend-engineer-prep/` → **`web-engineer-prep/`** | ✅ — user decision |
| 7 | Person 2's three day-0 files created | ✅ |
| 8 | **§3.4 resolved: Person 1 reviews Person 2's code.** Written into `prerequisite-sketch.md` as a feedback contract, with an attempt-first rule and a cadence field to fill in | ✅ — user decision |

### Decision 8 is the load-bearing one

A working senior engineer willing to review code is the reference answer most beginners never get, and it converts Person 2 from a Track B learner who cannot tell good work from bad into one who can. Two things protect it, both written into the contract:

- **Attempt first, always.** A review of work Person 2 did is worth a great deal. A review of work they didn't attempt teaches nothing and burns the favour.
- **Free answer keys are used first.** The browser, the error message, a test they wrote. Person 1 is reserved for the one question those cannot answer — *is this design any good?*

The realistic failure mode is not Person 2 abusing it; it is the cadence quietly lapsing after week three. The cadence field exists to make that visible.

---

## Still open — needed before Person 2's *plan* (not their artifacts)

The three day-0 artifacts are deliberately plan-free; Track B's §3 set is designed to work without a schedule. But a study plan cannot be written until:

1. **Hours per week, and whether there is a real deadline.** A learner with 6 hrs/wk and no deadline gets a different competency list than one with 25 hrs/wk and savings running out.
2. **Geography and market access.** Entry-level compression is not uniform. The realistic first role for a beginner in 2026 is frequently *not* at a tech company — internal tooling at a non-tech employer, agency work, or an apprenticeship. The high-status bootcamp→startup-junior pathway is the one that broke, and aiming at it by default is the most likely way this goes wrong.
3. **Person 1's sustainable review cadence** — the number that goes in the contract's blank.

Per §11 and §13, do not write that plan yet regardless. Person 2 runs the three artifacts for two weeks first; a review schedule joins in week 2 only if delayed recall is measurably being missed. **Building Person 2 a six-week plan on day 0 would repeat, in a new directory, the exact mistake this review was convened to diagnose.**

---

## Round 9 — week 1 and week 2 walkthroughs (2026-07-23)

**First run under the new "Assume parity first" rule, and it worked.** Both legs invoked their own research and `reviewing-readability` skills, both disclosed provenance unprompted, and they returned *different* findings — which is the entire point. Under the old pattern the lead would have handed both legs pre-digested research and collected two confirmations.

### What parity caught that pre-digestion would not have

Codex and Gemini reported different pictures of what freeCodeCamp's CFSD path opens with. Codex flagged its uncertainty explicitly (*"exact full first-module order… is unverified"*); Gemini stated a first module with no hedge. That disagreement sent the lead to the source, where **all three of us turned out to be wrong about the shape**: CFSD is not a linear course but an umbrella of **six certifications plus a final exam**. Day one is `responsive-web-design-v9`; the `full-stack-developer-v9` page is a progress tracker that greets a beginner with six "Not Passed" items. Corrected in both the README and the file Person 2 reads.

### Week 1 — accepted, with the lead's reframe

Codex's design was taken over Gemini's on two points:
- **Day 0 is a separate 75–90 min sitting, not folded into Monday.** Codex: fold them and *"the learner's first memory of the system is admin plus failure"* — the worst possible opening for the one risk that ends this.
- **Monday opens with a prediction, not a skipped recall.** Gemini said drop the block; Codex said replace it. Better — it keeps the slot and the habit, and guess-before-reveal is already how the design works.

**The lead's reframe, which neither leg proposed:** both filed "skip the AI completion problem" as a *week-1 exception*. It isn't. The permanent rule is *use it when the course item is a lecture or finished example; skip it when the item already ships missing pieces.* It merely happens to mean "skip" in week 1. Filing it as an exception would have created a habit needing to be unlearned.

Gemini's hazard framing was kept intact and is the sharpest line in the section: freeCodeCamp hands out a green checkmark without ever leaving the browser, so the local rebuild is the step that gets quietly dropped — and dropping it in week 1 hardens into a habit that removes the only place real difficulty lives.

### Gemini's two blockers — both real, both fixed

Codex signed off with no blocker. **Gemini returned two High findings and was right on both.**

1. **An unexplained three-way contradiction on line counts.** Four places said 2–3 lines, Day 0 said 3–5, the competency list said five. Verified by grep. Not wrong to differ — week-1 lines are small enough that several land in a day — but *unexplained* differences read as an error to a first-time mentor. All three now state the reason.
2. **A 45-word opening sentence carrying four cross-references**, in the highest-stakes position in the section. Gemini measured the section **in isolation**, which is the correct method and stricter than the lead's whole-file measurement — the lead's numbers had hidden it. Now a 20-word lead plus a bulleted list.

### Week 2 replaces week 3 — (B), over Gemini's objection

The user observed that week 2 is the first week resembling every week after it, and that week 3 was arbitrary. Three options were put to both legs: add week 2 (A), replace week 3 with week 2 (B), or neither (C).

**Codex: (B).** *"Keeping week 3 as the canonical normal week makes the document skip the transition where most operator mistakes will happen."*

**Gemini: against (B)** — week 3 shows steady state uncontaminated by first-time annotations, and its JavaScript example (a `G` line for functions, an `R` line for a broken handler) is a far richer illustration of gap detection than basic HTML/CSS can produce.

**Verdict: (B), with Gemini's objection preserved rather than overruled.** Three ~5-hour walkthroughs in a document carrying an explicit anti-bloat guardrail is the bloat it warns against. But Gemini was right that the functions example is the best teaching artifact in the file — so it was **moved into the gap-detection section**, where it illustrates the rule directly and is arguably where it always belonged. Nothing lost, no third walkthrough.

Both legs converged on what week 2 must annotate, and all of it is in: first Keep/Split/Replace (including that "All Keep" is a valid outcome), the first `G` carryover, the first `R` line with *proof-failed-once ≠ misconception*, the first genuine recall block, the workshop→lecture switch that fires the AI prompt, and — Gemini's sharpest contribution here — **the first log read is for compliance, not patterns**, because one week of rows is signal and not proof.

### Scorecard

| Leg | Provenance | Findings | Accepted |
|---|---|---|---|
| Codex | Ran own research + readability (noted script absent, ran qualitative) | 3 (Day-0 separation, deviation-hardening, AI-rule scope) | 3 |
| Gemini | Ran own research + own `measure.py` | 4 (line-count contradiction, isolated-section quit point, week-3 richness, compliance-read) | 4 |
| Lead | Live source check | Resolved the CFSD shape error all three had; reframed the AI rule as permanent | — |

**Measurement note.** Gemini measured the new section in isolation; the lead measured the whole file. The lead's method hid a quit point in a section whose surrounding text was fine. **Measure the section you changed, not the file it lives in.**

## Round 8 — the resource decision (2026-07-23)

**Question:** which of Colt Steele's *Web Developer Bootcamp* (owned), freeCodeCamp, or roadmap.sh becomes Person 2's §3.4 worked-example source — and what are the first five "I can…" lines.

**Outcome: freeCodeCamp's Certified Full-Stack Developer path, primary. Colt Steele becomes the named `G`-line teaching source.** roadmap.sh excluded as primary by prior rounds (a map, not a curriculum) and unchallenged.

### Both legs recommended Colt Steele. Both conceded.

Round 1 was unanimous for Colt, on a shared premise: *freeCodeCamp is tiny, heavily-guided browser steps that never fade the scaffold, so a learner finishes it and still can't start from a blank file.* Gemini called it "a fatal flaw for this specific framework."

**That premise described the legacy curriculum.** The lead's live research found freeCodeCamp had rebuilt it, and the rebuild targets that exact critique — Quincy Larson: *"we'll drop you into the 'blank canvas' style coding labs much earlier into the curriculum, to minimize hand-holding."* CFSD ships 513 lectures, 64 workshops, **83 labs that give you a blank editor and a test suite**, built-in spaced repetition, a reviewed capstone, and a proctored exam.

Put back to both legs, **both conceded outright.** Gemini disclosed, when asked directly, that it had again reasoned from training data without searching. Codex went further and ran its own research, which produced the round's most valuable finding (below).

**This was a lead process failure too, and the more instructive one.** The lead told Codex "no web needed" and dispatched a question whose answer turns entirely on current product state. Two legs then reasoned confidently from stale facts because the lead's prompt design permitted it. *Route questions of current fact to a leg with live search, or run the research first and hand it over as context — do not ask any leg to adjudicate present-tense product claims from memory.*

### Why CFSD wins on the design already built

| The design needs | CFSD ships |
|---|---|
| Worked examples (§3.4) | 513 lectures + 64 step-by-step workshops |
| Completion problems (§5 step 3) | The workshops *are* these — the AI-generated ramp drops to backup |
| Blank-file rebuild (§5 step 4) | 83 labs: blank editor + a test suite to make pass |
| Reference answer (§3.4) | The test suite — free, instant, impartial, available when Person 1 isn't |
| Spacing (L6) | Built-in spaced repetition + daily coding challenge |
| A signal AI can't fake | Reviewed capstone + proctored 90-question exam |

**The strategic argument neither leg made, which the lead raised in the debate round and both then endorsed:** this project's founding diagnosis was that *the portfolio app has been commoditized to zero — the evidence died, not the role.* A proctored exam and a community-reviewed capstone are precisely the signal shape that survives it. Codex's qualification is the honest one and is written into the README: employers will not weight it like a degree or prior job; its value is as **fraud-resistant supporting evidence**, which still beats another tutorial-built CRUD app.

**The sleeper benefit:** the test suite answers *"is this correct?"* daily for free, protecting Person 1's Saturday hour for the one question it cannot answer — *is this design any good?*

### Codex's falsifier, verified and acted on

Codex found CFSD was **still beta as of Sept 2025** — backend coursework and exam environment not live — with a Jan 2026 forum answer still describing backend as in development. The lead checked the live curriculum page: CFSD is listed and **not** marked "(Beta)", while fCC's language certs on the same page *are* — but it is titled "Certified Full-Stack **Curriculum**" where every sibling says "**Certification**", consistent with the exam still landing.

Resolution written into the README as a 10-minute pre-flight: **verify only that the HTML/CSS/JavaScript modules and their labs are live.** That is all Person 2 touches for months. Backend, capstone and exam are a year out; if they land late it costs nothing now. If the early modules are *not* solid, Colt Steele becomes primary — the design runs on either.

### "Pick one" held; the two-course tension dissolved

Both legs rejected sequencing (freeCodeCamp → Colt) as a §11 violation that would give Person 1 two syllabi to reconcile and turn gap-detection back into syllabus-invention. That verdict stands — **but the design already had a slot neither leg noticed.** Round 6 established that a `G` line cannot enter the week until Person 1 names a teaching source. Colt Steele, already owned, *is* that source. Only one thing owns the sequence; the other is a reference shelf. Not a compromise — a role that already existed.

### The first five lines

Written into `competency-list.md`, matched to where CFSD actually starts (Semantic HTML → CSS). Two are **conceptual** rather than mechanical, on the reasoning that a learner who only ever types ends up producing code they can't account for.

Line 4 — *"build a page as a real file on my own computer, not only inside the freeCodeCamp window"* — is a **`G` line, and it is in the starting set deliberately.** freeCodeCamp's browser environment hides local files, editors, and saving. It is the first gap the course creates, it is invisible to the learner, and it makes a concrete worked example of what Person 1's Saturday job actually is.

### Scorecard

| Leg | R1 position | After evidence | Unique contribution |
|---|---|---|---|
| Codex | Colt | **CONCEDE** → CFSD | The beta/completeness falsifier, self-researched, with sources — the round's most valuable finding |
| Gemini | Colt | **CONCEDE** → CFSD | The clearest steelman of narrative video for an L12 risk profile; disclosed its training-data reliance when asked |
| Lead | — | CFSD | Ran the research that overturned the shared premise; raised the hiring-signal argument |

## Round 7 — sign-off on the unreviewed change (2026-07-23)

Run under the updated `multi-model` verdict protocol: a bare GO is non-responsive; every leg must return **concrete blockers or an explicit falsifier**. Both legs returned blockers. Ledger rows appended (2 call, 2 synthesis).

**Subject:** four downstream propagations of the Round 4 framework edits. Three were mechanical. The fourth — rewriting Week 4's gap-topic block — had been applied by the lead **without leg review**, and was flagged as such when it was made.

### Both legs produced the same falsifier, independently

> *Is Person 1 Track A (has a trace to reactivate) or Track B (genuinely new) on consistent hashing, sharding, cache invalidation, and consensus?*

Everything hung on it: Gemini's High blocker was conditional on Track B, and Codex's medium blocker on the same axis. **The question was resolvable from the repo, so it was checked rather than argued:**

- `external-comparison.md`: *"you've never **needed** consistent hashing or cache invalidation at scale"* — never *needed*, not never encountered.
- `role-and-evidence.md`: cache invalidation is *"untested territory"* — untested, not unknown.
- The same person writes ADRs citing DDIA ch. 7.

**Verdict: Track A with vocabulary gaps.** By Gemini's own stated falsifier — *"If they are Track A, the lead's change is perfectly correct"* — its High blocker does not survive, and it is recorded as **not accepted**. Codex reached the same read unprompted: *"Person 1 is not a Track B beginner overall; this is a Track A plan with specific vocabulary gaps."*

### The real defect, which only Codex found

The lead's change was directionally right and **violated §6 in a way the lead did not notice**. §6 states that reconstructing material you saw twenty minutes ago *"mostly tests working memory… The retrieval that actually builds storage strength is the one that opens your next session, after a delay."* The rewrite put a from-memory table immediately after the reading and treated it as *the* retrieval — the precise error §6 exists to prevent, committed while fixing a different §6-adjacent error.

**Fix, combining both legs:** 70 min reading **as case studies** (Codex: "worked examples/case studies, not generic reading") · 20 min sources-closed table **explicitly labelled a comprehension check** · **the real retrieval moved to week 6**, folded into the existing repo-conceptual block. Two weeks of forgetting is what makes it count. Budget unchanged — 90 min inside the same 2h block, no new hours.

Also accepted from Codex's medium blocker: the encoding was too thin at ~20 min/topic. The 70/20 split addresses it without cutting to two topics.

### Gemini's two accepted findings

**The word "exception" was doing real damage.** The day-one mentor check was framed as *"one exception"* to "nobody else writes in it" — which implies someone else may write. Upstream §3.1 says *check*, and checking is not writing. Now: *"They say what they'd change; **you still type every word.** That's true on day one and every day after."* Codex read the same passage as compatible with the ownership rule; Gemini's reading is the one a beginner would actually have.

**A missed semantic propagation.** The lead grepped for stale *quotes* of the changed §2/§10 wording and found none — but never checked for *semantic* consequences. §10 now says "start with the lowest layer that explains the stall," and `competency-list.md`'s stall table was a flat, unordered list. It is now ordered lowest-layer-first: *never got worked on* (L0) → *something has to come first* (L2) → *too big* (L3). The blame-framing risk of leading with "you didn't do it" was handled by rewording to *"the sessions went elsewhere"* and keeping the "not a verdict on you" line.

### Scorecard

| Leg | Findings | Accepted | Unique |
|---|---|---|---|
| Codex | 2 medium | 2 | 2 (§6 violation · thin encoding) |
| Gemini | 1 high, 2 medium | 2 | 2 ("exception" wording · §10 propagation) |
| Lead | — | — | Resolved the shared falsifier against the repo |

**Process note.** The verdict protocol worked as designed. Neither leg stamped; both produced blockers; the one High blocker was refuted by evidence rather than by authority, using the leg's own falsifier. The lead's change survived in intent and was materially wrong in execution — which is the case for gating unreviewed edits, not a reason to have skipped the gate.

## Final gate — round 6 sign-off + readability (2026-07-22)

Design sign-off and a second readability pass, both legs invoking their own `reviewing-readability` skill. **Both returned APPROVED WITH CHANGES.** Both named a defect #5 — and they named *different ones*, both real.

### The two defect #5s

**Gemini — telemetry blindness. The best single finding of the whole session.**

> The error log fires on two triggers: you got something wrong, or you were stuck >10 minutes. But the behaviour the AI columns exist to catch is asking AI *instantly*. Do that and you never get stuck and nothing goes wrong — so neither trigger fires, and the slide is invisible by construction.

The control was blind to precisely the behaviour it was built to monitor. Fixed with a third trigger: **write a row on any AI use at all**, even when nothing went wrong. A row reading *"asked for a hint, got it in one, fine"* is now a good row — and their *absence* is the warning sign, not their presence.

**Codex — `G` lines have no teacher.** A gap line by definition has no course section behind it, so naming the gap without naming where the explanation comes from is assigning homework with no textbook. Codex's rebuttal to the obvious defence was correct: *"naming it is not a control."* Fixed with a hard rule — a `G` line cannot enter the week until one of three is true: Person 1 explains it there and then, names one specific resource, or points at a later section of the learner's own course. Otherwise it's parked.

### Gemini's hit on the lead, which landed

The README was justified under §11 on the grounds that it *removed* mentor content from the beginner's reading path. Gemini checked, and it hadn't:

> "The load wasn't removed; it was just duplicated into the README."

Correct. `prerequisite-sketch.md` still carried the full `C/G/R` table and the Keep/Split/Replace mechanics. The justification was a rationalisation until the content actually moved. It has now moved — the beginner's file keeps the *fact* that some lines come from gaps, plus permission to ask where a line came from; the notation and carry-over bookkeeping live in the README only.

That also resolved Gemini's beginner quit point, which was the `C/G/R` table itself — *"dumps administrative state directly onto the beginner."*

### Verdicts and quit points

| Floor reader | Quit point | Resolution |
|---|---|---|
| Beginner, first 20 min | `C/G/R` marks table (Gemini) · *"You cannot learn a technical skill alone if nothing can tell you you're wrong"* (Codex) | Marks table moved to README. Codex's is **kept** — classified hard-because-the-subject-is-hard: the social prerequisite is real and softening it would produce a confident, wrong reader |
| Person 1, first Saturday | *"07:30 — Blank page, 15 min…"* — the Monday walkthrough blocked the operational path | Saturday protocol moved **above** the week narrative |
| Person 1, 10pm logging a miss | *"Weeks 3–6 target exactly that gap (rubric row: Calibration)"* — both legs, independently | Table moved to the top; all explanation below it |

**Also fixed:** `Stream 1` references surviving in `interview-prep/error-log.md` after the study-plan rename (Codex, R2) · `Card made?` column dropped, 10 → 9 (both legs flagged column count; Codex's reasoning preferred — `Scored` stays because calibration needs confidence-vs-score) · "Udemy drift" as undefined local idiom (Gemini, R2).

### Measurements — reader's path

| Document | p90 | FK | Note |
|---|---|---|---|
| `competency-list.md` | 23 | 5.3 | |
| `prerequisite-sketch.md` | 25 | 5.3 | improved from 5.6 as mechanics moved out |
| `web-engineer-prep/error-log.md` | 22 | 5.9 | grew by the third trigger; acceptable |
| `web-engineer-prep/README.md` | 22 | 5.6 | audience is a senior engineer |
| `interview-prep/error-log.md` **(path)** | **22** | **6.8** | 3 sentences, 37 words to the table. Whole doc is FK 8.6 / p90 39, but that is explanation *below* the path |

### The disagreement, and its resolution

Gemini predicted Codex would object to hiding `C/G/R` from the learner — on the grounds that a beginner should know why a gap line exists, so it doesn't read as Person 1 inventing scope. That concern is legitimate. Resolved by splitting fact from notation: the beginner's file now says some lines come from things the course skips, that Person 1 owes them a way to learn those, and that **"ask where it's coming from" is a fair question**. The letter codes and carry-over tracking stay in the README. Both concerns satisfied; neither leg's position taken whole.

### Predictions on record

Codex predicted the next defect would be that `G` lines need a required teaching-source field — **implemented in this round**. Gemini predicted the learner being asked to draft "I can…" lines for course sections they haven't studied yet, which is a genuinely thin exercise — **logged in the README's "Still weak"** with the fix if it bites: write the line *after* the first session on a section, not before.

Both legs again named **L12 — motivation, not quitting** — as the residual exposure that no artifact closes.

## Panel round 3 — the coupling defects (2026-07-22, after the readability gate)

Four design defects surfaced *after* sign-off, during a walkthrough of what Person 2's week actually looks like. **All four were found by the user, none by any model leg.** Recorded because the pattern is more useful than the fixes.

| # | Defect | Root cause |
|---|---|---|
| 1 | No session loop existed | §3.4 was **half-resolved** — reference answers secured (Person 1), worked-example source never named. The files said "then go and do the thing" without ever saying what the thing was |
| 2 | Ownership drift between the two files | Split ownership on one artifact: the prerequisite sketch lived in Person 2's daily workflow but only Person 1 could author it |
| 3 | Ordering desync with the course | The sketch derived from Person 1's mental model; Person 2 lives inside a course sequence. Two competing authorities, one of them blind |
| 4 | "Write tomorrow's line" contradicted Saturday's ordering | Introduced by the fix for #2. Caught by Gemini |

**The pattern behind all four: a control that nobody inspects is decoration.** Codex's formulation. Writing something down does not create governance — the Proof column, the Friday self-review, the AI-usage columns and the `Week of` field were all written as if recording a thing made it true.

### The fixes

- **The course owns the sequence** — not Person 1, not Person 2. Saturday now starts with Person 2 reading out the course's next 2–3 section titles. This removes the desync by construction: the plan cannot disagree with the course if it is derived from it.
- **Person 1's real job is gap detection, not sequencing** — finding what the course assumes but never teaches. Gemini: course titles are marketing-shaped ("Build a Shopping Cart"), so Person 1 must *interrogate* them — "did the video actually cover that, or just use it?" — rather than rubber-stamp them.
- **Provenance marks on every line** (`C` course · `G` gap · `R` redo). Codex's guardrail: without them, "gap detection" slowly becomes inventing a syllabus, which is the failure being fixed.
- **Keep / Split / Replace instead of weekly rewrite.** Both legs called the discard-and-rewrite ritual churn dressed as hygiene — a learner rewriting the same three rows every Saturday will correctly stop. The anti-staleness property is preserved by carrying rows forward with a new date. *"The useful outcome of Saturday isn't three new rows; it's the two of you agreeing this week's work is still the right work."*
- **Person 1 reads `error-log.md` every session, AI columns included.** Unanimous fourth-defect find. A beginner self-reporting AI discipline cannot catch their own slide — "I attempted it first" becomes "I glanced at it first" one step at a time, and the only person qualified to notice was never assigned to look.
- **Friday gathers; Saturday judges.** Gemini's sharpest catch: asking a beginner to decide whether their own lines had "drifted back into topics" is a capability mismatch — *if they could reliably tell a topic from an ability, they wouldn't have written the topic.* This is the **same defect class as the original Proof column**, which means the panel made the identical mistake twice: assigning the system's hardest judgment to the node with the least context.
- **Stalled lines get classified, not blamed** — too big / missing prerequisite / not enough attempts. Codex's L12 fix: being stuck becomes diagnostic data rather than a verdict on the learner.

### What the legs said was still most exposed

Both named **L12 (motivation / not quitting)** as the remaining weak point at 20–28 hrs/week, on the grounds that the design still offers many ways for a beginner to conclude they are personally at fault. That is the constraint to watch, and no artifact closes it — only the Saturday hour does.

**Prediction on record.** Codex expects the next defect to be that `error-log.md` needs an explicit Saturday duty (now added). Gemini predicted the "write tomorrow's line" contradiction (found and fixed in the same round).

## Readability gate — 2026-07-22 (final)

Run under the `reviewing-readability` skill by all three legs, each invoking their own copy. Scope: every deliverable artifact doc. Floor readers were pinned per set, not left as "general audience".

| Set | Floor reader |
|---|---|
| `web-engineer-prep/` | A complete beginner who has never written a line of code, in their first 20-minute setup session |
| `interview-prep/` | A senior engineer, 8pm after work, six weeks out, tired, deciding whether to start tonight |
| this document | Person 1 — **corrected mid-review**, see below |

### The two quit points

**Both external legs independently named the same sentence for the senior reader** — the first line of `study-plan.md`:

> "This plan is a **Track A (Reactivate)** instantiation of framework/LEARNING-SYSTEM.md — existing competence that needs to become accessible under time pressure."

Measurement confirmed it: **four undefined technical terms in one sentence**, before the reader has been told to do anything. A tired reader deciding whether to start tonight quits at sentence one. The plan now opens with what tonight costs and what to do first; the framework provenance moved to the audit trail at the bottom.

**For the beginner, both legs landed one sentence apart in the same section** — `competency-list.md`'s Proof column. Codex: *"The Proof column is where you decide, up front, what would convince someone else."* Gemini: the example row *"A test you wrote that fails before your fix and passes after."* Same defect from two angles: the column demanded expert judgment from someone who does not yet have it, and every example offered as scaffolding was itself jargon.

**This was the panel's own celebrated idea.** The Proof column came out of the first round as the elegant fix to the beginner's signal problem, and it did not survive contact with the actual floor reader. It was not deleted — the underlying need is real and the subject is genuinely hard. It was converted from a *judgment* ("name what would convince someone") into a *selection* ("pick one of these five"), written in words a non-coder holds.

### Before / after on the reader's path

The binding metric is undefined-terms-at-first-use, not grade level.

| Document | Undefined terms | FK grade | p90 sentence |
|---|---|---|---|
| `study-plan.md` (path) | **7 → 1** | 8.3 → 6.9 | 25 → 23 |
| `competency-list.md` | 3 → 2 | 6.8 → 5.8 | 24 → 21 |
| `prerequisite-sketch.md` | 4 → 3 | 5.2 → 5.0 | 25 → 25 |
| `error-log.md` | 3 (unchanged) | 5.6 | 19 |

**The measurement trap fired exactly as the skill documents.** `competency-list.md` scored **FK 6.8 — "plain English"** — while two independent reviewers failed it for beginner dropout. Worse, the script strips markdown tables before measuring, so the proof-example row where Gemini located the quit point was **not in the measured text at all**. The formula could not see the defect even in principle. Grade level was used only as a regression guard; it never drove a decision here.

### Other findings applied

- **Notation removed from the reader's path, not explained.** `S1/S2/S3` → *Repo conceptual / Drills / Simulation* throughout; `§3`, `L0`, `Track A/B/C` moved off the path into the audit block. Unanimous across both legs.
- **Evidence tax cut.** The `48% / −17%` AI study figures in `prerequisite-sketch.md` are gone; the causal claim stays. A beginner in their first session is not a skeptic who needs convincing — they need the rule.
- **An impossible instruction fixed.** `prerequisite-sketch.md` asked a beginner to map which skills depend on which — a judgment that requires already knowing the field. Person 1 now drafts the first version with them. Gemini's find; neither other leg caught it.
- **Audience header added to this document.** Gemini returned R4 FAIL on tone here, on the grounds that telling a beginner their planned pathway "broke" spends trust before earning it. **That verdict was partly manufactured by the lead's own scoping** — the beginner was assigned as this document's floor reader, and that was the wrong call: this is a decision record for Person 1, and rewriting it for a beginner would destroy its function. Resolved by stating the audience at the top rather than rewriting. The underlying risk is real: handed over unfiltered, this document delivers discouraging macroeconomics with none of the "here's what we do about it."

### Verdicts

| Document | Verdict |
|---|---|
| `study-plan.md` | REWRITE → **applied**, re-measured, guards improved |
| `competency-list.md` | REWRITE SECTION → **applied** |
| `prerequisite-sketch.md` | REWRITE SECTION → **applied** |
| `web-engineer-prep/error-log.md` | **SHIP** — both legs, unchanged. Strongest beginner file in the set |
| `README.md`, `role-and-evidence.md`, `external-comparison.md`, `question-bank.md`, `interview-prep/error-log.md` | **SHIP** |
| `learn-cli-README-draft.md` | Gemini: REWRITE. **Overruled** — it is a parked design doc, not on any reader's path, and its deferred banner is the only part anyone needs to read |
| this document | Audience header added; not rewritten |

**Process note.** The Antigravity leg failed once on expired OAuth and was re-run after the user re-authenticated. Codex could not locate `measure.py` and ran the qualitative procedure only, disclosing this up front; the lead supplied all before/after numbers. Both external legs claimed the same top finding — that `study-plan.md` argues with its own framework instead of instructing the reader — and Gemini claimed it as uniquely its own, which it was not.

## Sign-off record

| Leg | Model | Round 1 | Round 2 | Final |
|---|---|---|---|---|
| Lead | Claude Opus 4.8 (1M) | Independent analysis + live web research (Firecrawl; Bloomberry, Stanford DEL, Revelio, NBER, interview-format sources) | Issued 6 challenges | **APPROVED** |
| 1 | Gemini 3.1 Pro High (Antigravity) | Full four-part analysis — **from training data, uncited** | Disclosed on challenge, then searched live. **4 CONCEDE · 1 REVISE · 1 HOLD** | **APPROVED WITH CHANGES** (all applied) |
| 2 | GPT-5.2 (Codex) | First run **failed** — 1800s idle timeout on a six-file + web-research prompt. Re-run tight and scoped, read-only. | Contributed the three sharpest results in the review | **APPROVED** |

**What each leg uniquely contributed.** Gemini named the frontend compression first and hardest, and its overstatement is what forced the level-vs-role decomposition that became the central finding — a wrong answer that produced the right question. The lead supplied the entire empirical base; every market number in this document came from its research leg, and without it the panel would have signed off on uncited training-data claims. Codex contributed the `Proof` column, the AI-instrumented error log, the six-condition trigger, and the §3.4 violation — collectively the difference between a document that lists artifacts and one that knows why each exists.

**Process note.** The lead's round-1 position on D6 was wrong, and Gemini's HOLD was correct; the finding survived only because Codex reframed it. Recorded because a sign-off record that shows only the lead being right is not a review.
