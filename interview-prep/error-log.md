# Error log

Append-only. Write the row **before** you look up the answer — blocked >10 min, log it first.

| Date | Source | What I got wrong | What I thought was true | What's actually true | Why I made this error | Route | Confidence before | Scored | AI |
|---|---|---|---|---|---|---|---|---|---|
| | | | | | | | | | |

- **Source** — `QB §4.2` · `NeetCode: <problem>` · `mock #2` · `timed design` · `Anki`
- **Why** — the misconception, not the fact. A miss that only becomes an Anki card preserves the fact and never fixes the thinking. Make the card too; the row is what fixes the thinking.
- **Route** — where the fix goes:
  - `decayed` — you passed a cold attempt on this item (the Week 1 gate, or a blank-page check right now). A spacing problem: Anki and re-solves.
  - `never-encoded` — the cold attempt failed, or you never ran one. Never learned: re-encode it (`study-plan.md`, Week 1), not Anki.
  - `unknown` — run a cold attempt before assuming either.

  "I just forgot" is only a diagnosis for `decayed`.
- **Confidence before** — 0–100%, rated before you check. **Scored** — what you actually got after checking: hit / partial / miss, or the share of the question's answer pointers you hit. The gap between the two is the only reliable way to find what you don't know you don't know.
- **AI** — `—` none · `hint` · `answer` · **`caught`** — the model asserted something false and you spotted it. Write this one the day it happens: `role-and-evidence.md` has a row waiting on exactly this, it's the highest-value row in that table, and you will not remember it in six weeks.

**Nobody else reads this file, so the mocks are your inspection.** Every mock in the plan is AI-disabled. If the `answer` count here climbs while mock performance is flat or falling, that is the one metric that matters, and the mocks are what make it visible.

## Weekly review of this file (30 min)

Read for **patterns, not entries**.

- Three rows about the same misconception is a curriculum item, not three mistakes. It goes at the top of next week's repo-conceptual work.
- Where did confidence most exceed score? That is next week's syllabus. A systematically overconfident category is more dangerous than a low-scoring one — you'll never choose to study it.
- Rows whose *why* is "I just forgot": check `Route`. `decayed` → schedule it. `never-encoded` or `unknown` → the encoding never happened; send it to re-encoding, not Anki.

## Week 6

Re-answer the 10 worst-graded items **and** the ones where confidence most exceeded score. The second set is the more dangerous one and is easy to skip because it doesn't look like failure.
