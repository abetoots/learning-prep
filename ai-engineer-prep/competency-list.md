# What I can do

Write in this file first, before you open the course. Every line is something you *do*, not something you know about, and every line is tested the same way:

> **explain it from first principles with no notes · say what breaks if it's wrong · build the smallest working version from a blank file**

**A line is done when all three proofs exist, not when you feel ready.** The Proof column tracks them: `S` said it out loud (two minutes, no notes, how it works, why, what breaks) · `B` built it again blind (empty file; it runs; the key in `prerequisite-sketch.md §1` says it's right) · `G` graded, where a grader exists. Tick each with a date. A quiz score alone finishes nothing.

**These lines are provisional.** This is a new field, so the first list will be wrong in places you can't see yet. Every line carries `?` until the two-week revision on 2026-10-28; rewriting them then *is* the learning, not a failure of the first draft.

**Track column** — filled by the Day 0 blank-page pass (README Setup step 2), before any reading. `A`: the page fills, so just test it, no relearning. `C`: you can name the parts but can't start — the course's worked example comes first. `B`: neither — go slower and smaller: worked example → completion problem → blank file, no mixing.

**Score** — the grader's number where there is one, else the measurement the sketch names for that line, else hit / partial / miss on the proof.

**Database: competency-list**

| # | I can… | Track | Proof | Date | Score |
|---|---|---|---|---|---|
| 1 | I can write a small Python program — a few functions, a dataclass, one async call, one pytest test — from a blank file without looking anything up. ? | | S B | | |
| 2 | I can call a model API from a blank file with streaming, structured (JSON-schema) output, and a retry/timeout policy, and explain why each matters when the output is non-deterministic. ? | | S B | | |
| 3 | I can explain tokens, context windows, temperature and sampling from first principles, and build a token counter that demonstrates what happens at the context limit. ? | | S B | | |
| 4 | I can implement tool calling — define a tool, dispatch the call, validate the arguments, return the result — from a blank file, and explain why idempotency matters here. ? | | S B G | | |
| 5 | I can build a single-agent loop (plan → act → observe) with explicit state and a step limit, from a blank file; kill it mid-run and show it resumes without repeating a side effect. ? | | S B G | | |
| 6a | I can chunk, embed and index a small document set from a blank file, and explain two chunking strategies and when each fails. ? | | S B | | |
| 6b | I can retrieve and rerank against that index, measure recall@5 on a labelled question set, and say what the number means and what moves it. ? | | S B | | |
| 7a | I can build an eval harness for one LLM feature — a labelled set, a scoring function, a regression check that fails on a bad prompt change — from a blank file, and explain why a unit test is not enough. ? | | S B | | |
| 7b | I can write an LLM-as-judge with a rubric I wrote, measure its agreement with the labels, and explain where it disagrees and why. ? | | S B | | |
| 8 | I can explain prompt injection and how a tool-using agent is sandboxed and permissioned, build an injection test that breaks an unsafe agent, and the fix that stops it. ? | | S B | | |
| 9 | I can trace an agent run end to end (a span per step; tokens and cost per span), inject a known fault, and find it from the trace alone. ? | | S B | | |
| 10 | Given a stated p95 latency and cost budget, I can choose model, cache and routing for one feature, build it, and show it meets the budget without dropping below the eval harness's score — and explain the trade-offs I made and the ones I rejected. ? | | S B | | |
| 11 | I can pass the course's capstone benchmark with an agent I built, and separately defend each design choice cold. ? | | S B G | | |

Lines 2, 4, 5 and 9 are where the backend evidence *should* transfer — that is a hypothesis the blank-page pass tests, not a result. Lines 3, 6, 7 are the new field proper. **Line 1 is the gate for every other `B` proof**: the field's tooling is Python and the evidence is TypeScript. If the pass marks it `B` or `C`, the Python practice that earns the gate is the exception to the gate — Exercism's Python track (README Setup step 3), starting smaller than line 1 says: one function with one test, from a blank file, then grow it. No other build line starts until line 1's own `B` proof exists (a cold rebuild with the tests green — not just a filled page). The `S` proofs on lines 3, 8 and 10 don't need Python and can run meanwhile.

**When you touch this file:** end of every session — tick what you proved, add `?` lines for anything that came up. Weekly review — collect the `?` lines, the undone lines, the ones you now think were a bad idea; decide then, not mid-week. On 2026-10-28 — rewrite the list against two weeks of error-log rows.
