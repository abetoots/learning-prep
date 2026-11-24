# ai-engineer-prep — multi-model review

Panel: Claude Fable 5.1 (lead, with three deep-research workers) · GPT-5.2/Codex · Gemini via Antigravity. Date: 2026-10-14. First instance built from `~/learning-system/template/` (framework commit `460eafa`).

Fixed by the owner before the panel: goal = transition from senior backend to an AI role; target performance = teach-it-cold plus blank-file build; stop condition = the competency list; no deadline; syllabus source proposed = roadmap.sh, with permission to push back. Open: which AI role.

## Executive summary

**Role: Senior AI Engineer — LLM application / agentic systems.** All three legs, researching independently, landed on the same role; the only split was whether AI application platform / LLMOps should be a visible fallback, and that split is recorded, not flattened. **Syllabus: Hugging Face Agents Course as the graded spine; roadmap.sh fails the framework's answer-key rule and is demoted to a monthly blind-spot map.** The package took three content rounds and two readability rounds to sign off; the defect that cost the most was the one the framework warns about by name — the answer key must exist *before* volume, and the first draft named a key that graded four of thirteen lines.

## Stage 1 — Research (parallel, independent)

Each leg ran its own web research (assume-parity). Lead: three `deep-research` workers (role landscape; backend-to-AI transition evidence; syllabus sources), ~35 sources, full-page fetches. Codex: 12 lookups, 8 opens, 3 failed (AI Index 2026 and PwC 2026 PDFs, DeepLearning.AI 403) — disclosed. Antigravity: opened roadmap.sh and its projects pages, the HF course, the *AI Engineering* book README; hiring-loop and "3.2 roles per applicant" claims carried no URL and were **not counted** (`stale-context` partial).

### Consensus findings

1. **"AI engineer" in 2025–2026 primary sources means LLM-application engineer, not ML engineer.** swyx (who coined it; RedMonk interview 2025-07-23): the ML engineer's work ends at inference, the AI engineer's starts there. Huyen/Orosz (*AI Engineering* excerpt, Pragmatic Engineer 2025-05-20): "software engineering with AI models thrown in the stack"; ML knowledge "no longer a must-have". Job-board usage lags — some "AI Engineer" postings still prefer ML degrees. Anthropic's careers page lists Applied AI as a hiring category distinct from research (~53 open roles vs 66 research at capture).
2. **Demand magnitude is unverified.** The Stanford AI Index 2026 and PwC 2026 PDFs failed to fetch for two legs; Lightcast-via-AI-Index figures (agentic-AI postings 0.06% → 0.23% of US postings, 2024→2025, ~90k) arrived through secondary summaries only. The recommendation rests on candidate fit, not a market ranking.
3. **Candidate fit.** The evidence file's demonstrated strengths — idempotent dispatch, optimistic CAS, crash-safe recovery, tenancy as an invariant, OpenTelemetry — are the production failure modes of LLM applications. Its stated gaps — big-infra, Kubernetes, multi-region, ML — are the loops of inference/platform engineering and ML engineering.
4. **roadmap.sh fails §3.4** (all three legs opened it): topic nodes with external links; a projects page with one project idea and no reference solution; a linked solution using a deprecated 2023 client API. A map, not a syllabus.
5. **Syllabus comparison** (lead worker, primary pages): HF Agents Course — free, graded unit quiz (≥80% for the certificate), capstone agent scored on a benchmark; thin on retrieval quality, serving, observability. HF LLM Course — explicitly no certification. `anthropics/courses` — good API-graded exercises, **archived read-only 2026-09-15** (Antigravity confirmed via GitHub API after the lead's worker found it; Antigravity's own round-1 answer had recommended it as a primary spine). Chip Huyen, *AI Engineering* (2025) — "not a tutorial book"; architecture reference, no exercises. fast.ai — frozen at the 2022 edition. Full Stack Deep Learning / LLM Bootcamp — 2022/2023. Maven evals cohort — human-graded, $1,995–$5,000, cohort-scheduled.
6. **Python is the field's language; the candidate's evidence is TypeScript** (Antigravity, HIGH). Handled as a gated line decided by a cold test, not by estimate.

### Debated

| Item | Positions | Lead's verdict |
|---|---|---|
| AI platform / LLMOps | Lead's transition worker: the most direct distributed-systems fit on paper (K8s, observability, CI transfer; no PyTorch). Codex: keep *application* platform visible as a fallback — the evidence excludes big-infra, not app-platform. Antigravity: no fallback; it's the candidate's weakest front. | Rejected as target on the evidence file's own line 31. Named once as the *adjacent* role (gateways, tenancy, quotas, workflow reliability, tracing — same competency list). After the readability gate it lives in the CHANGELOG, not on README's Day 0 path. |
| Anthropic `courses` as spine | Antigravity round 1: yes. Lead worker: archived 2026-09-15. | Exercises usable; not a maintained key. |

## Stage 2 — Content sign-off (three rounds)

| Round | Codex | Antigravity | What changed |
|---|---|---|---|
| 1 | NO-GO: Plan block has pointers ("all ten, in order"); key doesn't grade lines 6/7/9/10 (opened the course: capstone grades GAIA answers at a 30% threshold); "pick a proof" lets a quiz finish a three-part performance; Python gate too broad; routing stated as fact | NO-GO: same key defect (#7 "Get it graded" impossible); #6 too big; Plan miscount; Monday's item left open; Q5 said "no" while four lines transfer from a partly-agentic repo; CHANGELOG links a file that didn't exist yet | Per-line key table (grader / measurement / parked); proof = S·B·G, all required; 6, 7, 10 split; 3 and 8 gained a build; Plan fully compiled; Q5 corrected; Python gate narrowed to build proofs |
| 2 | NO-GO: "measured" ≠ "competent" without a bar written before the attempt; reviewer trigger relies on self-detection; 10a (S-only) can't satisfy a three-proof stop condition; key fragments for 2 and 5 | **GO** — adjacent-role sentence accepted; falsifier: trivial 20-question sets fake competence | Bar column with baselines to beat (keyword search for 6b, always-pass for 7b); 10's quality floor = 7a's harness; 10a folded into 10; design quality declared outside "done"; test-set composition rule; keys for 2 and 5 completed |
| 3 | should-fix only: stream-vs-non-stream compares stochastic outputs; 7b's imbalance margin unattainable; 5 needs per-effect-ID identity incl. kill-after-effect-before-checkpoint | GO holds; falsifier: test-authoring tax in unfamiliar Python | Fixed fixture delivered both ways; balanced 7b set, precision and recall reported; 5 checks every effect by ID |
| 4 | **GO** | — | — |

## Stage 3 — Readability gate (every leg ran `reviewing-readability`)

Floor reader: a senior backend engineer, TypeScript and distributed systems, who has never read LEARNING-SYSTEM.md and never built an LLM feature, running Monday's first session from README alone in one pass. Baseline on README before rewrite: FK 10.8, p90 35 words, ~5 terms undefined at first use.

Round 1 — both legs FAIL on all four criteria, same quit point: the B/C Python branch named no worked-example source ("the reader is stranded on step one"). Same contradictions: Setup enrolled in the course before the Python gate; Setup passed all lines while Monday passed one. Density: the Reference-answer field (89 words) and the core-loop line (90 words). Lead's own pass agreed on the quit point. Fix: Day 0 = the pass on all 13 lines in one sitting; Monday = the branch Day 0 chose; Exercism's Python track named (verified live: free, concept lessons, test suite per exercise); Route defined inline; vertical lists for the loop and blocks; two examples instead of twelve.

Round 2 — Antigravity PASS ×4, one cut (the adjacent-role sentence; taken). Codex PASS ×3, one consistency blocker: "meeting the bar completes B" would let assisted code earn a blind-rebuild proof — fixed with its own sentence. README after: FK 9.8, p90 35 (no regression).

## Falsifiers carried into the first month

1. A representative sample of target-market postings requires model-training experience (Codex, role).
2. The 20-question labelled sets pass trivially and fake competence on retrieval and judge quality (Antigravity; answered by the composition rule, not eliminated).
3. The test-authoring tax — labelled sets, baselines, three breakages — in unfamiliar Python stalls the learner before the agent loops (Antigravity).
4. The feedback source can grade but cannot *order* — "feedback source sets the order" overfits the course case (Codex, carried from the template review).

## Ledger note

No `bare-GO` in any round. One `stale-context` partial (Antigravity round 1: archived repo recommended; undisclosed-provenance hiring claims). Codex disclosed three failed fetches unprompted. The lead's parallel research caught the archived repo; the legs caught the answer-key gap the lead had hand-waved. Both directions, as intended.
