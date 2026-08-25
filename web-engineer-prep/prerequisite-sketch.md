# What has to be true first

Two jobs for this file. The first one is a hard blocker — do it before you study anything.

---

## 1. The feedback contract (do this first)

You cannot learn a technical skill alone if nothing can tell you you're wrong. Practice you never check doesn't fix your mistakes — it locks them in.

**Your answer key is Person 1.** They are a working senior engineer who has agreed to review your code. This is the single biggest advantage you have, and most beginners never get it. Protect it by not wasting it.

**The contract:**

| | |
|---|---|
| **Who** | Person 1 reviews your code and your explanations |
| **How often** | Agree on it now and write it here: _______ (e.g. once a week, on a fixed day) |
| **You bring** | The attempt *first*. Never a blank page and a question. |
| **You also bring** | What you already tried, and what you *think* is wrong |
| **You write down** | Why you were wrong — in [[error-log]], not in your head |
| **Person 1 reads** | [[error-log]] — **including the three AI columns** — and [[competency-list]]. Two minutes, every session |

**The rule that makes this work: attempt first, always.** A review of work you did is worth a great deal. A review of work you didn't attempt teaches you nothing and burns the favour.

**Why Person 1 reads the AI columns.** You're asked to record, honestly, whether you leaned on AI for answers instead of hints. That's a hard thing to be honest with yourself about — "I attempted it first" quietly becomes "I glanced at it first", and you won't catch the slide because it happens one small step at a time. A record nobody ever looks at is decoration. Somebody has to actually read it, and it can't be the person doing the sliding.

### The other answer keys, which are free and always available

You don't need a human for everything, and you shouldn't. These are impartial and instant:

- **The browser** — does the page do what you expected?
- **The error message** — read it. All of it. Beginners skip this and it is almost always the answer.
- **A test you wrote** — passes or fails, no opinion involved.

Use these first. Save Person 1 for the questions they can't answer: *is this design any good?* — which is the one question the browser cannot answer.

### About AI

You will be tempted to use AI as your answer key. Be careful here, and understand exactly why.

The risk is not that AI is wrong. It is that **you can't yet tell a good answer from a confident wrong one** — that judgment is the thing you are here to build. If you outsource it before you have it, you build a fluent, wrong picture of how things work, and that is expensive to undo later.

This isn't a guess — it has been tested. Students given an AI that would answer for them did better *while they had it*, and worse than everyone else once it was taken away. The harm disappeared when the AI was told to give hints instead of answers.

So the rule is not "don't use AI." It is:

> **Attempt first. Then ask AI to critique your attempt, never to hand you the answer.**

Good: *"Here's my code and what I think it does. What's wrong with my reasoning?"*
Good: *"Ask me questions until I find the bug myself."*
Bad: *"Fix this."*

You will track whether you're keeping to this in [[error-log]]. It has columns for it, and they are not decoration — they're the early warning.

---

## 2. This week's work

**Your course decides the order. Not Person 1, and not you.**

That is what a course is for — someone already worked out what has to come before what, and put it in that order. Person 1 has not taken your course, so if they invent their own order you end up waiting for a topic your course covers in three weeks, or never. When that happens people assume they're the problem. They aren't; the two plans just disagreed.

So Saturday starts with the course, and takes about ten minutes.

**How Saturday works:**

1. **You bring the next 2–3 section titles from your course.** That's it — open the contents page and read them out.
2. **Together you turn those sections into "I can…" lines** and put them in [[competency-list]].
3. **Person 1 checks them.** This is the part only they can do — see below.

### What Person 1 is actually for

Not ordering. **Finding what your course leaves out.**

Course sections have friendly names — "Build a Shopping Cart" — that hide what's really needed. Person 1's job is to read those titles and ask:

- What should you actually be able to *do* after this section?
- Does it quietly assume something nobody has taught you yet?
- Is anything here out of date, or taught in a way that'll cause you trouble later?
- Is this small enough to finish in one week?

**They should ask you questions, not just nod at the titles.** "Did the video actually cover that, or did it just use it?" is the most useful question in the whole hour — courses use things they never explain all the time, and you won't notice, because you don't yet know what you weren't told.

### Two kinds of line, and it's worth knowing which is which

Most weeks, every line comes straight from a course section. Some weeks Person 1 spots something the course *needs* but never teaches, and adds a line for it.

**When they do that, they owe you a way to learn it** — they'll explain it themselves, or point you at one specific thing to read or watch. A line with no course section behind it and nothing to learn from is not a line yet. **Ask where it's coming from.** That's a fair question and they should have an answer ready.

Beyond that, the bookkeeping is Person 1's job, not yours. They keep track of where lines came from and what carries over.

### Week of: _______

| This week I'm working on | Where I learn it |
|---|---|
| *(example)* I can make a button that changes the text on the page | Course, section 7 |
| | |
| | |

Some of these will carry over to next week, and that's normal — you're not meant to clear the board every Saturday.

---

## 3. What a session looks like

**You are still taking a course. Nothing here replaces that.**

**Your course is freeCodeCamp.** Work through it in order — that's where the concepts, the explanations, and the order come from.

**Start here: `freecodecamp.org/learn/responsive-web-design-v9/`** — that's the first of six certificates that together make up the Certified Full-Stack Developer path. Don't start on the full-stack page itself; it's a progress tracker, and on day one it just shows you six things you haven't done yet.

It was picked because it already contains the shape of a session: short lectures for the explanation, step-by-step workshops, then **labs that hand you a blank editor and a set of tests you have to make pass.** That last part is the hardest and most valuable thing to arrange for yourself, and it comes with a free, instant answer key — the tests either pass or they don't.

Person 1 also owns Colt Steele's *Web Developer Bootcamp*. **That is not your course.** It's the shelf you pull from when something is missing — see [[README]] for how that works. Don't work through both; two courses means two orders, and you'd spend your time reconciling them instead of learning.

What changes is not *whether* you take a course. It's what you do with each piece of it.

**A session, start to finish:**

1. **Pick one line** from [[competency-list]]. One line — not a chapter.
2. **Go through the example once.** This is the part where someone shows you a complete, working answer and explains why each piece is there.
3. **Get the same example back with pieces missing, and fill them in.** ← this one
4. **Close everything and build it from an empty file.**
5. **Compare yours to the working version.** Where they differ, write down *why* in [[error-log]] — the why, not just the what.
6. **Do it again with less help**, until it's boring.

### Step 3 is the one everybody skips

Going straight from watching someone build it to building it yourself from nothing is a cliff. Step 3 is the ramp.

It used to be that nobody could give you that ramp. No course shipped "the same thing, but with three lines blanked out," so you'd either take the cliff or quit at it. Most people quit at it. That is what people mean when they say they got stuck watching tutorials forever.

Now you can just ask for the ramp:

> *"Here's the example I just went through. Give it back to me with the part that handles the button click removed, and a comment saying what should go there. Don't show me the finished version — I want to fill it in myself."*

That last sentence matters. Left to itself an AI will often hand back the blank *and* the answer underneath it, which turns the exercise back into reading.

Thirty seconds, and you have it. **This is the most useful thing AI will do for you, and it's on the safe side of the rule above** — you're asking it to build you practice, not to hand you an answer.

### Two things that decide whether this works

**Thirty to sixty minutes is a session.** If it ends and you produced nothing yourself, that wasn't a session. That was watching.

**Start each session by trying to remember the last one, before you open anything.** It will feel bad, and you'll get some of it wrong. That is the part that works — the remembering is what builds the memory, not the reading.

Related: [[competency-list]] · [[error-log]]
