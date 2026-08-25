# Repo-Derived Prep vs Public Question Banks

All external contents below were **verified against live pages on 2026-07-08** (not reconstructed from memory). Sources, cost, and what each drills:

| # | Source | URL | Cost | Signal drilled |
|---|---|---|---|---|
| 1 | System Design Primer | github.com/donnemartin/system-design-primer | Free | SD vocabulary/component taxonomy; 8 worked questions |
| 2 | Hello Interview | hellointerview.com/learn/system-design/in-a-hurry/problem-breakdowns | Freemium | Delivery mechanics + per-level expectations; 30 breakdowns (4 easy/15 medium/11 hard) |
| 3 | ByteByteGo (Alex Xu) | bytebytego.com/courses/system-design-interview | **Paid/curated** | Canonical worked solutions (25 design problems + 3 framework chapters) |
| 4 | Tech Interview Handbook | techinterviewhandbook.org | Free | Algorithms triage (18 topics, priority-ranked) + ~30 behavioral questions |
| 5 | NeetCode 150 / Blind 75 | neetcode.io/practice/practice/neetcode150 | Free lists; Pro paid | Algorithm pattern drilling, 18 categories, 150 problems |
| 6 | HackerRank Interview Prep Kit | hackerrank.com/interview/interview-preparation-kit | Free | OA-style fundamentals, with per-topic "% of companies test this" |
| 7 | interviewing.io SD guide | interviewing.io/guides/system-design-interview | Free guide | Interviewer-side rubric: green/red flags, senior-drives expectation |
| 8 | StaffEng archetypes | staffeng.com/guides/staff-archetypes | Free | Role calibration: staff = role + behaviors + impact + org recognition |

The cross-bank canon (appears in ≥2 verified banks): **URL shortener, rate limiter, news feed, chat, web crawler, key-value store/distributed cache, notification system, payment system, YouTube, Ticketmaster**, plus consistent hashing as a concept.

---

## Comparison: repo-derived themes vs the banks

**Covered** = the banks teach it well. **Missing from banks** = your repo prep is the stronger (sometimes only) source. **Better drilled elsewhere** = don't use the repo for this; use the named bank.

| Theme (from websand-v4) | Coverage in public banks | Verdict |
|---|---|---|
| Transactional outbox, idempotent dispatch, at-least-once semantics (ADR-0016) | ByteByteGo's Distributed Message Queue & Payment System chapters touch idempotency keys; Primer's "Asynchronism" section is a paragraph-level treatment. No bank walks crash-window analysis (claim/sent-before-bookkeeping/resume gates). | **Repo is stronger.** Banks give vocabulary; your crash-window fluency is a differentiator. Cross-check terminology against ByteByteGo Payment System so you speak the canon's dialect. |
| Optimistic CAS / lost updates / write-ownership discipline (ADR-0013) | Essentially absent as an interview topic in all 8 banks (interviewing.io lists "Databases" but at the replication/indexing level). DDIA ch. 7 territory. | **Repo is stronger; supplement with DDIA**, not a question bank. |
| Queue-backed workflows, stalled jobs, sweepers, recovery philosophy | Hello Interview: Job Scheduler (Airflow) breakdown; ByteByteGo: Distributed Message Queue. Neither covers surface-vs-auto-repair recovery tradeoffs. | **Repo stronger for depth; do the Job Scheduler breakdown** to see the canonical framing interviewers expect. |
| Read-scaling by pre-aggregation over huge event logs (ADR-0008) | Directly canonical: ByteByteGo "Ad Click Event Aggregation" + "Metrics Monitoring"; Hello Interview "Ad Click Aggregator" (Hard) + "Metrics Monitoring (Datadog)" (Hard). | **Convergent — study both.** Your implementation + their walkthroughs = strongest possible answer. These two Hello Interview hards are your highest-ROI reads. |
| Multi-tenancy invariants, RBAC as code | Not present in any of the 8 banks as a drill topic (security appears only as interviewing.io's "Authentication" concept and Primer's "Security" section). | **Repo is the only source.** Expect it in senior product-company loops even though banks skip it. |
| Webhook ingestion, signature verification, event dedup (ADR-0014) | Partially: notification-system chapters (ByteByteGo ch. 11, Hello Interview practice question) cover fan-out, not verify-before-trust ingestion. | **Repo stronger**; borrow scale framing from the notification chapters. |
| Email/campaign sending at scale | Directly canonical: ByteByteGo "Distributed Email Service" (ch. 24); adjacent: Notification System. | **Convergent — read ch. 24** and reconcile it with what you actually built; interviewers who read Alex Xu will anchor on it. |
| Orchestration vs pub/sub decision frameworks (ADR-0009) | Banks assume queues/events but publish no decision framework; interviewing.io's rubric rewards "well-reasoned, qualified decisions" generically. | **Repo is stronger** — your litmus test is a portable, memorable answer shape. |
| Testing strategy, invariant pins, integration-vs-unit | No bank covers testing as an interview subject at all. | **Repo only.** Comes up in senior loops as "how do you know it's correct?" |
| Ops/runbook incident reasoning | interviewing.io covers Failover/Replication as concepts; no bank drills triage. SRE-book territory. | **Repo is stronger** for narrative; no drill bank exists. |
| **Canonical SD problems** (URL shortener, rate limiter, news feed, chat, KV store, web crawler, YouTube, Ticketmaster, payment, Top-K) | The entire cross-bank canon. Hello Interview (30 breakdowns w/ difficulty + per-level expectations), ByteByteGo (25 chapters), Primer (8 free solutions). | **Better drilled elsewhere — entirely.** Nothing in your repo produces a Ticketmaster or consistent-hashing answer. Weeks 4/6 foreign-prompt runs come from here. |
| SD component vocabulary (CAP, consistent hashing, CDN, load balancing, replication, failover, caching tiers) | Primer's 16-section index + interviewing.io's "15 Fundamental Concepts" are exactly this. | **Better drilled elsewhere.** Your single-node Mongo + no-cache-tier reality means you've never *needed* consistent hashing or cache invalidation at scale — that's a known gap; study it from Primer/DDIA. |
| Algorithms / DS under time pressure | NeetCode 150 (18 categories: Arrays & Hashing 9, Two Pointers 5, Sliding Window 6, Stack ~6, Binary Search 7, Linked List 11, Trees 15, Heap 7, Backtracking ~10, Tries 3, Graphs 13, Adv. Graphs 6, 1-D DP 12, 2-D DP 11, Greedy 8, Intervals 6, Math 8, Bit 7). Tech Interview Handbook priority-ranks study order (High: Array, String, Sorting/Searching, Matrix, Tree, Graph). HackerRank kit adds company-frequency calibration (Arrays 70%, Hashmaps 40%…). | **Better drilled elsewhere — entirely.** See study-plan.md routing. |
| Behavioral question canon | Tech Interview Handbook's ~30 most-common list + per-company sets. | **Better drilled elsewhere** for the *question list*; your repo supplies the *stories* (STAR skeletons, week 5). |
| Role calibration (senior vs staff) | StaffEng archetypes (Tech Lead / Architect / Solver / Right Hand; staff = role+behaviors+impact+recognition). Hello Interview publishes explicit per-level expectations; interviewing.io: seniors are expected to *drive*. | **Use the banks** — they confirm the role-and-evidence.md calibration: your evidence is Solver/Architect-shaped *execution* without the org-recognition leg, i.e., strong senior. |

## What this means (three sentences)

Your repo makes you unusual in exactly the areas the banks are thin: correctness under concurrency and retries, tenancy invariants, recovery philosophy, and operating what you built — lead with those. The banks own three territories the repo can't touch: the canonical SD problem set (interviewers calibrate on it), component vocabulary you never needed at single-node scale (consistent hashing, cache invalidation, replication topologies), and timed algorithms — route all three to the named sources per study-plan.md. Where both cover a topic (ad-click aggregation, email service, job scheduler, payment idempotency), read the bank's walkthrough anyway: it teaches you the dialect the interviewer already speaks.

## Citation hygiene

- NeetCode's Stack/Backtracking counts (6/10 vs the historically cited 7/9) were ambiguous at fetch time — treat as approximate.
- Hello Interview's catalog lives at `/learn/system-design/in-a-hurry/problem-breakdowns` (shorter path 404s).
- ByteByteGo TOC is the paid product's sidebar; marked paid/curated throughout.
