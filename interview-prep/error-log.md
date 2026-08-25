# Error log

Append-only. Write the row **before** you look up the answer — blocked >10 min, log it first.

| Date | Source | What I got wrong | What I thought was true | What's actually true | Why I made this error | Route | Confidence before | Scored | AI |
|---|---|---|---|---|---|---|---|---|---|
| | | | | | | | | | |

**Source** = `QB §4.2` · `NeetCode: <problem>` · `mock #2` · `timed design` · `Anki`
**Route** (added 2026-08-01) = `decayed` — you passed a present-tense cold attempt on this item (the Week 1 gate, or a fresh blank-page check right now if it predates the gate — never "I'm confident I once knew this," that's the retrospective self-report this column exists to rule out), Track A is still correct, this miss is a spacing problem · `never-encoded` — the cold-gate routed this to B-lite/B-full, or would if you ran it now; "I just forgot" for one of these is not decay, it's the encoding never having happened at all (see below) · `unknown` — haven't run a present-tense cold attempt on this item yet; do that before assuming either
**AI** = `—` none · `hint` · `answer` · **`caught`** = the model asserted something false and you spotted it

---

## Why these columns

**`Why I made this error`.** A miss that becomes an Anki card preserves the *fact* and never fixes the *misconception*. Make the card too — but the row is what fixes the thinking.

**`Confidence before`.** Rate 0–100% before checking. The gap between confidence and score is the only reliable way to find what you don't know that you don't know, and weeks 3–6 target exactly that gap.

### Why `caught` earns its own value

`role-and-evidence.md` has a row waiting on exactly this — *"one case where AI was confidently wrong and you caught it"* — and it is the highest-value item in that table, because it's the only one an over-reliant candidate cannot manufacture. It's also the one you will absolutely fail to remember six weeks from now unless you capture it the day it happens. One word in this column is the capture.

### Your inspection mechanism is the mock, not a reviewer

Person 2's copy of this file has three AI columns *and a rule that Person 1 reads them* — because a beginner cannot catch their own slide from "I attempted it first" to "I glanced at it first," and the only person qualified to notice was otherwise never assigned to look.

You have no such reviewer, so that mechanism doesn't transfer. **What you have instead is already in the plan: every mock is an AI-disabled self-test.** The coding mock, the timed design, the behavioral — all unassisted, all scheduled, all graded. If the `answer` count in this column is climbing while mock performance is flat or falling, that is §8's one metric telling you something, and the mocks are what make it visible. Watch that pairing rather than the column alone.

---

## Weekly review of this file (30 min, part of the weekly review)

Read for **patterns, not entries**.

- Three rows about the same misconception is a curriculum item, not three mistakes. It goes at the top of next week's repo-conceptual work.
- **Where did confidence most exceed score?** That gap is next week's syllabus. A systematically overconfident category is more dangerous than a low-scoring one — you'll never choose to study it.
- Rows where the *why* is "I just forgot": that's not an analysis. Check the `Route` column first. If it says `decayed`, this is genuinely a spacing problem — schedule it. If it says `never-encoded` or `unknown`, "I just forgot" is the wrong diagnosis: the encoding never happened (possibly because the concept was AI-introduced and only approved, not derived) — send it to repo-conceptual work as a real Track B item (see `study-plan.md`'s ownership cold-gate), not to Anki.

## Week 6

Re-answer the 10 worst-graded items **and** the ones where confidence most exceeded score. The second set is the more dangerous one and is easy to skip because it doesn't look like failure.
