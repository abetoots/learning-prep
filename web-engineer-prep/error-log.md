# Error log

Append-only. Never delete a row. This one file does more work than everything else here combined.

**The *why* column is the whole point.** A list of mistakes nobody ever reads back is a list, not a log. The learning is in working out why it happened.

**Write a row when any of these three happen:**

1. **You got something wrong.**
2. **You were stuck for more than 10 minutes.** Write the row *before* you look anything up — that's harder, and that's why it works.
3. **You used AI at all** — even if nothing went wrong, even if it took ten seconds, even if you'd have got there anyway.

**That third one matters more than it looks.** The first two only fire when something goes badly. But the habit worth catching early is asking AI *straight away* — and when you do that, you never get stuck and nothing goes wrong, so the first two triggers never fire and the whole thing stays invisible. A row that says *"asked for a hint on the click handler, got it in one, fine"* is a perfectly good row. Write it.

---

## The log

| Date | What I got wrong | What I thought was true | What's actually true | Why I made this error | AI used? | Answer, or hint/critique? | Could I redo this without AI? |
|---|---|---|---|---|---|---|---|
| *(example)* 2026-07-22 | My button did nothing when clicked | The script tag could go anywhere | The script ran before the button existed on the page | I didn't know the page loads top to bottom | yes | hint | yes |
| | | | | | | | |

---

## The three AI columns

These exist because of one specific failure: **being unable to work without AI, and not noticing until it matters.**

- **AI used?** — yes / no.
- **Answer, or hint/critique?** — did you ask it to *tell you the answer*, or to *critique an attempt you already made*?
- **Could I redo this without AI?** — answer honestly, right then. Not "probably."

**The one number to watch:** what share of your AI use is answer-seeking versus hint-seeking. If the answer-seeking share is going up, your own ability is going down. That's the trade, and this is how you see it happening rather than finding out in an interview.

**Once a month, test it.** Pick something you've already done. Do it again with AI completely switched off. If it falls apart, go back to critique-only until it doesn't.

---

## Read this file for patterns every week

Not for entries — for **patterns**. Three rows about the same misunderstanding is not three mistakes. It is one thing you haven't learned yet, and it belongs at the top of next week's list.

Take the patterns to your review with Person 1. "I keep getting this wrong and I don't know why" is the single most useful thing you can bring them.

**Person 1 reads this file every session — the AI columns included.** That is part of the contract, not you being checked up on. You are being asked to notice your own slide toward asking AI for answers, and that is genuinely hard to see from the inside; it happens one small step at a time. Somebody else has to look, or the columns are just decoration.

Related: [[competency-list]] · [[prerequisite-sketch]]
