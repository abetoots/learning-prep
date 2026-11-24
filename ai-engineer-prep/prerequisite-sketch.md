# What has to be true first

Two jobs. The first is a hard blocker — do it before you study anything, because in a new field you cannot yet tell a good answer from a confident wrong one, and something outside your head has to.

## 1. The answer-key contract

| | |
|---|---|
| **What tells me I'm wrong** | per line — the table below. Nothing gets practised at volume until its row names a key |
| **How often it looks** | every graded unit as I reach it; every measurement the moment the build runs |
| **I bring** | the attempt first. Never a blank page and a question |
| **I also bring** | what I tried and what I think is wrong |
| **I write down** | why I was wrong — in `error-log.md`, not in my head |
| **Who reads the error log, AI column included** | me, at the weekly review; the monthly AI-off problem is the check that I'm reading it honestly |

**The key, line by line.** Two kinds: a **grader** (the course scores it) and a **measurement** (the world scores it — a number you can't argue with). **The bar is written here before the attempt, never after.** Numbers are provisional until the 2026-10-28 revision. Where a row also says *beats the baseline*, the baseline is the dumb version you build first, and **both** must hold — the number keeps the bar honest, the comparison keeps the test honest. A trivially easy test set makes any bar meaningless, so the 20-question sets must include at least five questions whose answer spans two chunks and five whose wording shares no words with the source passage.

| Line | Key | Bar |
|---|---|---|
| 1 Python | pytest passes; the program runs (on the B/C branch, Exercism's own test suite per exercise) | all tests green on the blank-file rebuild |
| 2 API call | schema validation over 20 live runs, streamed and non-streamed each; one fixed response fixture delivered both ways; an injected timeout | 20/20 valid each way; the fixture reassembles byte-identical from the stream; the timeout terminates the call and the retry fires — two live calls are *not* expected to match |
| 3 tokens/context | the counter matches the provider's tokenizer; the overflow is reproduced on purpose | exact match on 10 strings; the overflow error is caught and named |
| 4 tool calling | course unit quiz; an invalid argument is rejected before dispatch | quiz ≥80%; the bad call never reaches the tool |
| 5 agent loop | course unit quiz; kill at step n and resume — including a kill *after* an external effect succeeded but *before* its checkpoint was written | quiz ≥80%; same final result as an uninterrupted run; every side effect, by ID, exactly once |
| 6a chunk/embed/index | known-passage lookup for every chunk | every chunk retrievable by its own text |
| 6b retrieve/rerank | recall@5 on the labelled set, against a keyword-search baseline you build first | recall@5 ≥ 0.8 **and** beats the baseline; reranking must not lower it |
| 7a eval harness | the regression check on a deliberately broken prompt vs the good one | fails on the broken, passes on the good, across 3 different breakages |
| 7b LLM-as-judge | agreement with 7a's labels on a **balanced** set (10 pass, 10 fail), against an always-pass judge | agreement ≥ 0.8 — always-pass scores 0.5 on a balanced set, so the bar already beats it; report precision and recall separately so a judge that only catches one class is visible |
| 8 injection | the injection test against the unsafe agent, then the fix | breaks it; the fix makes the same test pass; the fix doesn't break 4's valid calls |
| 9 tracing | an injected fault located from the trace alone | the right step named, 3 of 3 distinct faults, without reading the code |
| 10 serving under budget | p95 latency and cost per request against the stated budget, **with 7a's harness as the quality floor** | meets both numbers *and* 7a's regression check still passes at the same score — a cheaper model that fails the eval doesn't count |
| 11 capstone | the course's benchmark | the course's passing score; the cold defence is `S`, separately |

**What is outside "done", on purpose:** *is the design any good* — the chunking strategy, the rubric, the serving choice beyond "meets the budget and the eval". Nothing here can grade that, and "it runs" is a weak signal for it. So no line claims it. Meeting the bar **on a cold rebuild** completes a line's `B` proof — a bar passed on assisted code completes nothing; the line is done when `S`, `B` and (where it has one) `G` all exist. Design judgment is what a reviewer adds later, and the trigger for finding one is a line whose bar is met while the weekly teach-it-cold keeps finding holes. Options then — a peer who does this work, or a paid human-graded cohort — chosen then, not bought on day one.

**Reference text, not a key:** Chip Huyen, *AI Engineering* (2025) — the map for lines 6, 7, 10. It explains; it does not grade.

**AI is not the answer key, and this field makes that harder, not easier.** Anything an AI says about AI engineering is the thing you are least able to check. Attempt first; ask it to critique the attempt; verify against the provider's docs and the course before believing it.

## 2. What must be true first

Stop at two levels. Studying prerequisites forever and skipping them are equally fatal. `Have it?` is filled by the blank-page pass, not by estimate.

**Database: prerequisites**

| Competency | Must be true first | And before that | Have it? | Where I learn it |
|---|---|---|---|---|
| 5 agent loop | 4 tool calling; 2 API call with structured output | 1 Python incl. async | pass decides | course units 1–2 |
| 7a eval harness | 2 structured output (to score it); what precision/recall mean | 1 Python | pass decides | course eval unit; Huyen, evaluation chapter |
| 6b retrieve/rerank | 6a index; embeddings and cosine similarity from first principles | 1 Python | pass decides | course agentic-RAG unit; Huyen, RAG chapter |

## 3. This week's targets

The course's unit order sets the sequence for `C` items. `A` items don't need a sequence — test them and move on. Carry-over is normal.

**Database: weekly-targets**

| Week of | This week I'm working on | Where I learn it |
|---|---|---|
| | | |
