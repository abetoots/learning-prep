# Error log

Append-only. Write a row when any of these happen:

1. **You got something wrong.**
2. **You were stuck for more than 10 minutes.** Write the row *before* you look anything up.
3. **You used AI at all** — even if nothing went wrong. Asking straight away means you were never stuck and nothing broke, so the first two triggers never fire; that is exactly the habit the AI column exists to catch. *"asked for a hint on 4.2, got it in one, fine"* is a good row.

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

**Nobody else reads this file, so the mocks are your inspection** — they are the framework's AI-disabled self-test, and the plan runs one in weeks 3, 5 and 6. If the `answer` count here climbs while mock performance is flat or falling, that is the one metric that matters. If a mock collapses, cut back to hint/critique-only until it doesn't.

## Weekly review of this file (30 min)

Read for **patterns, not entries**.

- Three rows about the same misconception is a curriculum item, not three mistakes. It goes at the top of next week's repo-conceptual work.
- Where did confidence most exceed score? That is next week's syllabus. A systematically overconfident category is more dangerous than a low-scoring one — you'll never choose to study it.
- Rows whose *why* is "I just forgot": check `Route`. `decayed` → schedule it. `never-encoded` or `unknown` → the encoding never happened; send it to re-encoding, not Anki.

## Week 6

Re-answer the 10 worst-graded items **and** the ones where confidence most exceeded score. The second set is the more dangerous one and is easy to skip because it doesn't look like failure.
