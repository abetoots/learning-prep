# How this works — Person 1's operating doc

**Audience: you (Person 1).** Not written for Person 2. Their three files are self-contained, and everything they need is already in them.

**Status: living.** This model has been wrong five times so far. When Saturday stops matching what's written here, change this file rather than working around it.

**Why it exists:** the Saturday protocol and its bookkeeping used to live inside Person 2's files — mentor instructions sitting in a beginner's reading path, adding load they didn't need. It lives here now. If you find it creeping back into their files, pull it out again.

---

## The model in one page

| Thing | Who owns it | Cadence |
|---|---|---|
| **The sequence** — what order topics come in | **The course** — freeCodeCamp CFSD. Not you, not them | Fixed by the syllabus |
| `competency-list.md` — "I can…" lines + proof | **Person 2 writes.** You read, never edit | Daily |
| **The week's 2–3 lines** — which ones they work | **Agreed together** | Saturday |
| `prerequisite-sketch.md` §2 — this week's table | **You** supply the judgment, they hold the pen | Saturday |
| `error-log.md` | **They write, you read** | Them: daily · You: every session |
| **Gap detection** — what the course assumes but never teaches | **You.** The one thing only you can do | Saturday |
| **Provenance and carry-over bookkeeping** | **You, in this file.** Deliberately not in theirs | Saturday |

**The rule that stops it drifting:** the sequence comes from the course, so the plan can't disagree with the course. Your job isn't ordering — it's finding what the course leaves out.

---

## The course decision

**Primary: freeCodeCamp — Certified Full-Stack Developer path.** `freecodecamp.org/learn/full-stack-developer-v9/`

Both model legs opened by recommending Colt Steele and **both conceded** once shown what CFSD actually contains now. Their objection — "freeCodeCamp is tiny guided steps that never fade the scaffold" — describes the *legacy* curriculum, which freeCodeCamp rebuilt specifically to fix. Quincy Larson, announcing it: *"we'll drop you into the 'blank canvas' style coding labs much earlier into the curriculum, to minimize hand-holding."*

Why it wins on the design you're already running:

| The design needs | CFSD ships |
|---|---|
| Worked examples (§3.4) | 513 short lectures + 64 step-by-step workshops |
| Completion problems (§5 step 3) | The workshops *are* these — so the AI-generated ramp becomes a backup, not the mechanism |
| Blank-file rebuild (§5 step 4) | **83 labs: blank editor + a test suite you have to make pass** |
| A reference answer (§3.4) | The test suite — free, instant, impartial, and available Tuesday at 11pm when you aren't |
| Spacing (L6) | Built-in spaced repetition, plus a daily coding challenge |
| A hiring signal that AI can't fake | Community-reviewed capstone + proctored 90-question exam |

That last row matters more than it looks. This project's founding diagnosis was that **the portfolio app has been commoditized to zero — the evidence died, not the role.** A proctored exam and a reviewed capstone are the shape of signal that survives that. Codex's caveat is right and worth repeating to them: employers won't weight it like a degree or prior job. Its value is as *fraud-resistant supporting evidence*, which beats another tutorial-built CRUD app.

**The test suite is the sleeper benefit for you.** It answers "is this correct?" every day for free, which protects your Saturday hour for the only question it can't answer: *is this design any good?*

### Colt Steele's role: the gap shelf, not the spine

You own *The Web Developer Bootcamp*. It is **not** a second course to work through in parallel — that would give you two sequences to reconcile, which is the failure this whole design exists to prevent.

It is your **named teaching source for `G` lines** (Saturday, step 4). When you spot something CFSD assumes but doesn't teach, you owe them a way to learn it — and "watch this specific section of Colt" is a perfectly good answer, already paid for. Both legs independently landed on the same framing: Colt is the narrative backup for a stuck week, not the spine.

### Verify before Saturday one — 10 minutes, and it's a real risk

Codex found that CFSD was still beta as of Sept 2025, with backend coursework and the exam environment not live, and a Jan 2026 forum answer still describing backend as in development. The live curriculum page as of now lists CFSD **not** marked "(Beta)" — while fCC's language certs on the same page *are* marked beta — but titles it "Curriculum" where the others say "Certification".

**Log in and check:** are the HTML/CSS/JavaScript modules and their labs fully live? That's all Person 2 touches for months, and it's the only part that has to be solid on day one. Backend, capstone, and exam are a year away; if they land late it costs nothing now.

**If the early modules are not solid, switch to Colt Steele as primary** — that is the fallback, and the whole design works with either. Don't agonise; check, pick, start.

---

## Saturday — your hour

**1. Course first (2 min).** They read out the next 2–3 section titles from the contents page. That's the sequence. You don't invent one.

**2. Convert to "I can…" lines (10 min).** Together, into their competency list. Then interrogate — this is what earns the hour:

> - What should they actually be able to *do* after this section?
> - Does it quietly assume something nobody taught them?
> - **"Did the video actually cover that, or did it just use it?"**
> - Is this small enough to finish in a week?

That third question is the most valuable thing you'll ask all hour. Courses use things they never explain, constantly, and Person 2 cannot notice — not knowing what you weren't told is the definition of the problem.

**A concrete one, from later in the course.** A section called something like *"make the button do something"* has them writing functions — but the course doesn't *explain* functions until two sections further on. It uses them first. Person 2 has no way to spot that: they'd work the section with a hole where functions should be and conclude they were slow. You add `I can explain what a function is and when it runs` as a **`G`** line, name where they'll learn it, and the hole never opens. **That single line is the whole argument for your involvement** — the course doesn't catch this about itself, and the beginner can't.

**3. Mark provenance.** Every line is `C`, `G`, or `R`. Keep this in your own notes; it's bookkeeping, not something they need to carry.

| Mark | Means | Rule |
|---|---|---|
| **C** | From a course section | — |
| **G** | A gap you found — the course needs it but never teaches it | **Must name a teaching source before it enters the week.** See below |
| **R** | Redo: proof failed, or it keeps recurring in the error log | — |

Unmarked lines don't go in. You *should* add `G` lines — that's why you're here — but naming them as gaps is what stops gap-detection quietly becoming you inventing a syllabus.

**4. `G` lines need a teacher — this is a hard rule.** A `G` line by definition has no course section behind it, so if you don't name where the explanation comes from, you've assigned homework with no textbook. Before it enters the week, one of these must be true:

- **You explain it** — then and there, 10 minutes, at the whiteboard
- **You name one specific thing** to read or watch — a page, a video, a section of a different course
- **You point at a section further along** in their own course and they jump to it

If none of the three is available, the line doesn't go in this week. Park it.

**5. Keep / Split / Replace.** Don't rewrite the table — survivors carry forward with a new date.

| Do this | When |
|---|---|
| **Keep** | Still matches where the course is, still the right size |
| **Split** | Too big, or the proof failed. Cut it in half |
| **Replace** | The course moved on, or a gap turned up |

All Keep is a good week, not a wasted ritual. The output of Saturday isn't three new rows — it's the two of you agreeing this week's work is still the right work.

**6. Read the error log — including the AI columns.** Two minutes. This control only works because someone else looks; a record nobody reads is decoration. Note that they now log *every* AI use, not just the ones that went badly — see "What to watch".

**7. Classify stalls, don't blame them.** Too big → split. Missing prerequisite → add it ahead. Not enough attempts → shrink the next target. Almost every stall is one of the three, and all three have a fix.

**8. Name one thing to stop doing.** Every week. There's always one.

---

## Week 1 — the cold start

Week 1 is not a normal week with less history. It has setup that never happens again, and it's missing four things a normal week assumes are already in place:

- No previous Saturday, so nobody has set this week's lines
- Nothing to recall on Monday morning
- An empty error log
- An unsigned feedback contract

It is also when quitting is most likely, and most of this design's protections are Saturday-shaped — they arrive at the *end* of the week. So week 1 gets a session at the front instead.

### Where they actually start — check this first

**CFSD is not one course.** It's an umbrella: six certifications, then a final exam. The `full-stack-developer-v9` page is a **tracker**, not a place to study — it shows an exam and six things marked "Not Passed."

Do not point a beginner at it on day one. Their actual starting URL is:

> **`freecodecamp.org/learn/responsive-web-design-v9/`**

The CFSD page is where you go to see progress. Both model legs assumed CFSD was a single linear path and got this wrong; it's an easy mistake and a discouraging first screen.

### Day 0 — before Monday, one sitting, 75–90 minutes

**Do not fold this into Monday's first study session.** If contract, course check, first lines, local-file setup, and lesson one all land in one go, their first experience of this system is admin followed by failure. That's the worst possible opening for the one risk that actually ends this — giving up.

| Time | What |
|---|---|
| **00:00 — 15 min** | **Sign the contract.** Open `prerequisite-sketch.md` §1 and fill in the cadence blank together. Use Saturday unless there's a real conflict. They need to know exactly when their work gets read. |
| **00:15 — 10 min** | **Course check.** Log in, open Responsive Web Design v9, confirm the first modules and their labs are live and usable. Don't study yet. |
| **00:25 — 25 min** | **First lines.** Read the first few course items aloud and turn them into **3–5** "I can…" lines — more than the usual 2–3, because week-1 lines are small enough that several land in a single day. From your first Saturday onward it's 2–3. They hold the pen. Your question for each: *"is that something you could prove from a blank file?"* |
| **00:50 — 25 min** | **The local-file gap.** freeCodeCamp lives in the browser and never teaches you to make a file. Teach it now: create an `.html` file, save it somewhere they'll find again, open it in their own browser, change something, refresh. This is the first `G` line and you are its teaching source. |
| **01:15 — 5 min** | **Name Monday.** Point at the exact first item. Nothing is left to decide on Monday morning. |

### Monday — the first real session

**07:30 — Predict, 10 min.** There's nothing to recall yet, so don't fake it. Instead: *"What do you think HTML is for? What do you think will happen when you change the file and refresh?"* Write the guess down. Being wrong here is free and it's the same muscle the recall block uses every other day.

**07:40 — The course, 45 min.** First item, in order. If it's a step-by-step workshop, the workshop *is* the ramp — pause before each reveal and guess first.

**08:25 — Completion problem: probably skip it this week.** freeCodeCamp's early modules are already step-by-step with pieces missing. That's the ramp, already built. Adding an AI-generated one on top is busywork. **Use the AI prompt only when a course item is a lecture or a finished example with no missing pieces** — which is the rule from week 2 onward too, not a week-1 exception.

**08:45 — Real file, 45 min.** Rebuild the smallest thing from the lesson in a local file on their machine. Open it. Change one visible thing. Refresh. **This is the proof for the `G` line and it is the step to protect.**

**09:30 — Compare and log, 20 min.** The error log starts today. If genuinely nothing went wrong, write the row anyway — *"used AI: no, nothing broke."* An empty log in week 1 is not a clean week, it's an unused instrument.

**10:00 — Practice, 60–90 min.** Same shape, tiny variations. Same tags, different words. Less help each time.

**13:30 — Wrap, 20 min.** Tick what landed. Add `?` lines for anything confusing. Don't pick tomorrow's work — Day 0 already did.

### Tuesday to Friday

Steady state, with one rule: **every session opens with recall from yesterday, even when yesterday feels too small to be worth remembering.** Especially then.

### The three deviations, and the one hazard

Week 1 legitimately differs in exactly three ways. Everything else is permanent:

1. Monday opens with a **prediction** instead of recall, because there's nothing behind it yet
2. The first error-log read has **no pattern to find** — that's fine, it's one week
3. AI completion problems are **skipped while the course is already shipping workshops**

**The hazard is the blank-file rebuild.** freeCodeCamp is comfortable, self-contained, and gives you a green checkmark without ever leaving the browser. A beginner will want to stay there — and if they skip the local rebuild in week 1, "staying in the browser" hardens into a habit that quietly removes the one step where real difficulty lives. Watch for it on Saturday. It's the single most likely way this design fails in month one.

---

## Week 2 — the first normal week

**Every week after this one looks like this one.** Week 2 is the first week with a real Saturday behind it, a log with rows in it, and the full session shape. Nothing here is a special case — but several things happen for the *first* time, and those are flagged, because a first time is where the mistakes are.

### What your first Saturday produced

You ran it at the end of week 1. It set three lines:

| Line | Mark | Teaching source |
|---|---|---|
| I can nest a list inside another list, from a blank file | **C** | Course — next workshop |
| I can save an HTML file where I'll find it again, and open it in my browser | **G** | *You showed them on Day 0 — carried over* |
| I can explain why a heading is a heading and not just big text | **R** | — *proof failed: they could type it, couldn't say why* |

**Three firsts in that table.**

The **`G` line carried over** — the local-file gap from Day 0 didn't close in one week. That's normal and it's the right call. A gap line that survives a week isn't failure; it's a line that was bigger than one session, and next Saturday you either split it or it finally lands.

The **first `R` line.** They typed the heading fine but couldn't say why it was a heading. That's a proof that failed, not a misconception yet — one miss is a data point. If it shows up again in three weeks, *then* it's a pattern and gets real time.

**"All Keep" would also have been fine.** If the week's lines are still the right lines, the Saturday output is agreement, not new rows.

### Monday

**07:30 — Recall, 15 min. This is the first real one.** Week 1's Monday used a prediction because nothing existed yet. Now it does: before opening anything, what's left from Friday? Two days have passed and some of it is gone. **Writing down the half-remembered, slightly wrong version is the mechanism** — not a warm-up for it.

**07:45 — The course, 45 min.** Next item, in order. Pause before each reveal and guess first.

**08:30 — Completion problem — *check whether you need one*.** While the course is shipping step-by-step workshops, it's already the ramp; skip it. **The first time a course item is a lecture or a finished example with nothing missing, the AI prompt starts:** *"Give this back with one piece removed and a comment saying what belongs there. Don't show me the finished version."* Watch for that switch — it may land this week.

**09:00 — Blank file, 45 min.** Build it from nothing, in a real file on their machine. This is where it comes apart, and that's expected. Stuck >10 min → error-log row written *before* anything gets looked up.

**09:45 — Compare and log, 20 min.** Not "I forgot the closing tag." *"I thought the browser would work it out."* That row explains six future bugs.

**10:30 — Practice, 90 min.** Three variations, each from blank, less help each time. AI *generates* the exercises, never solves them.

**13:30 — Integration, 90 min.** The ongoing thing they're building. Today's piece goes in for real.

**15:00 — Wrap, 30 min.** Close everything and sketch what they just did. Tick any line whose proof landed. Add a `?` line if something came up. No deciding tomorrow's work — Saturday did that.

Done by 15:30. About 5 hours, of which **roughly 45 minutes was new material.** At 25 hrs/week the pull toward five hours of course a day is enormous and it is the failure mode. They can consume five hours; they can't absorb it.

### Tuesday–Thursday

Same shape. The opening recall gets richer — yesterday, plus something from earlier in the week that's had time to fade. The `G` line gets its own session, using the source you named on Saturday.

### Friday — gathering day

**No new material.** Blank-page dump of the week first. Then **rebuild Monday's work from scratch** — four days of forgetting makes this the highest-value retrieval of the week, worth far more than Monday's attempt twenty minutes after the lesson.

Then read the error log and collect for tomorrow: the `?` lines, anything undone all week, anything they now think was a bad idea.

**The first log read is thin, and you should read it differently.** One week of rows is signal, not proof. Don't hunt for deep patterns that can't exist yet — read it for **compliance**: are they writing rows at all? Are AI uses being recorded, including the ones where nothing went wrong? An empty or AI-free log after a full week is the thing to ask about, and it's the only question that's really available this early.

**They gather. They don't judge.** They're not asked to decide whether a line is a real ability or a topic in disguise — that's the expertise they're building, so they can't rule on it. That's your call tomorrow.

**Sunday: off.** Not a soft recommendation. It's where the week consolidates, and a beginner at 25 hrs/week is exactly who'll try to buy hours from it.

---

## What to watch

| Signal | What it means |
|---|---|
| List filling with "I can center a div", emptying of "I can explain why the page did that" | Optimising for the mechanical. Earliest visible symptom, and you'll see it before they do |
| `answer` appearing more than `hint` in the AI columns | §8's one metric moving the wrong way. Cut back to critique-only until it turns |
| **Rows that say "used AI, nothing went wrong"** | **Good — that's the log working.** Their absence is the worry, not their presence |
| Lots of ground covered, little rebuilt from blank | Watching instead of doing. The same failure that cost you time on Udemy |
| Same misconception three weeks running | Not three mistakes. One curriculum item, top of the week |
| Saturday consistently running long | You're transferring answers instead of asking questions. Lowest-value use of the hour |

**Weeks 3–4 will feel worse than week 2.** Delayed recall and rebuilding suppress how competent you feel while doing them, and that's exactly when people quit — it reads as getting worse. Tell them in advance. It lands completely differently as a prediction than as a diagnosis.

---

## Still weak

**L12 — motivation, not quitting.** Both model legs named this as the remaining exposure at 20–28 hrs/week, and no artifact closes it. The design still offers routes to concluding you're personally at fault: the course assumes things, the scaffold is hard, proofs fail. Stall classification helps by making "stuck" diagnostic. The rest is your hour.

**Saturday asks them to write "I can…" lines for sections they haven't studied yet.** Predicted by the Gemini leg as the next defect. Drafting a target for a concept you can't yet define is a thin exercise — expect these lines to be vague on Saturday and to need sharpening mid-week. If it becomes a real problem, the fix is to write the line *after* the first session on that section, not before.

**Ordering is authored Saturday but sometimes needed Wednesday.** Accepted, not solved. If it bites, set 3–4 lines instead of 2–3. Do **not** move to on-demand ordering — that turns your hour into an on-call rotation and reintroduces the split ownership this design removed.

---

## Changelog

| Round | Changed |
|---|---|
| 1 | Three §3 artifacts; Proof column added |
| 2 | Readability gate. Proof column converted from *judgment* to *selection* — it was the beginner's quit point |
| 3 | Session loop added (§3.4 was half-resolved: no worked-example source was ever named) |
| 4 | Ownership split fixed; the sketch re-scoped to one week |
| 5 | Course owns the sequence; gap detection with `C/G/R`; Keep/Split/Replace; Person 1 reads the error log; Friday gathers, Saturday judges |
| 6 | `G` lines must name a teaching source · error log fires on **any** AI use, not just misses · provenance bookkeeping moved out of the beginner's files into this one |

Full reasoning and the model-panel record: [`../ROLES-AND-DELIVERABLES_MULTI_REVIEW.md`](../ROLES-AND-DELIVERABLES_MULTI_REVIEW.md)
