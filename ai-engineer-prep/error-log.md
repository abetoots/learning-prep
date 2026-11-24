# Error log

Append-only. Never delete a row. This one file does more work than everything else here combined.

**Write a row when any of these happen:**

1. **You got something wrong.**
2. **You were stuck for more than 10 minutes.** Write the row *before* you look anything up.
3. **You used AI at all** — even if nothing went wrong. Asking straight away means you were never stuck and nothing broke, so the first two triggers never fire; that is exactly the habit this column exists to catch. *"asked for a hint on the tool schema, got it in one, fine"* is a good row.

**The *why* column is the whole point.** A list of mistakes nobody reads back is a list, not a log.

- **Source** — `course U2` · `#5` (a competency line) · `benchmark` · `AI-off test` · `deck`
- **Route** — where the fix goes. `forgot`: you could do this once, from memory, and it faded — practise it again on a schedule. `never-learned`: you never could do it from memory — go back to the worked example; more repetition won't help. `unknown`: try it from memory now, then decide. "I just forgot" is only true for `forgot`.
- **Confidence before** — 0–100%, rated before you check. **Scored** — what you actually got: the grader's number, or hit / partial / miss. The gap between them is the only reliable way to find what you don't know you don't know.
- **AI** — `—` none · `hint` · `answer` · `caught` (it said something false about this field and you spotted it — write that one the day it happens; it is the best evidence you're building judgment).

**Weekly: read for patterns, not entries.** Three rows on one misunderstanding is one thing to learn, top of next week. Where confidence most exceeded score is next week's work. **Monthly:** one problem with AI fully off; if it falls apart, critique-only until it doesn't.

**Database: error-log**

| Date | Source | What I got wrong | What I thought was true | What is actually true | Why I made this error | Route | Confidence before | Scored | AI |
|---|---|---|---|---|---|---|---|---|---|
| | | | | | | | | | |
