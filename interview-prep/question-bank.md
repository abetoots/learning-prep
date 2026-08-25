# Question Bank — Conceptual Interview Prep Grounded in websand-v4

~66 questions in 8 interview categories. Tags: **[DYD]** defend-your-design · **[WBI]** what-breaks-if · **[ALT]** alternative-design-and-why-rejected (12 total). Each question lists its grounding artifact (or *transferable* if no repo knowledge is needed to answer) and **answer-key pointers** — what a strong answer must mention, not a script.

**How to use:** answer out loud, 2–4 minutes each, as if a senior interviewer asked. The repo grounding is where you *learned* the concept; the answer should work at any company. Questions marked ⚑ are repo-narrative questions (fine for "tell me about your system" segments, not transferable).

## Ownership diagnostic (added 2026-08-01)

The repo was built partly via agentic coding, so `[DYD]` isn't automatically true for every item — some designs were AI-proposed and only approved. Tag an item **the first time you attempt it**, cold, before checking the pointers. Never fill this in from memory of "did I know this six months ago" — that's unreliable (fluency illusion); tag `Current cold ability` from what you can produce *right now*.

```
Ownership diagnostic: PE=<prior exposure> · ORIG=<origination> · COLD=<current cold ability> · CLAIM=<claim strength> · ROUTE=<derived from COLD>
```

- **PE** (prior exposure): `knew` · `partial` · `new` · `unsure`
- **ORIG** (origination): `user-derived` · `AI-proposed` · `jointly-shaped` · `contested` · `unsure`
- **COLD** (current cold ability) — **this is the only axis that routes you**: `defends` (≥70% of the pointers, unaided, names the invariant/failure mode, gives one rejected alternative when relevant) → Track A, answer normally. `recognizes` (partial, no real reconstruction) → B-lite re-encoding first (see `study-plan.md` Week 1). `blank` → B-full re-encoding first.
- **CLAIM** (interview-claim strength): `designed` · `evaluated-and-approved` · `adopted-with-caveat` · `learned-afterward`. **If CLAIM ≠ `designed`, relabel the question's tag**: `[DYD]` → `[EVAL]` (if you can defend a decision you evaluated and approved) or `[ADOPT]` (if you're defending something you accepted with a caveat). Answer as "the decision I evaluated/accepted," not "my original design" — the interview is testing judgment, not literal authorship, but the *wording* still has to be true.

Template, not a real tag (fill your own before using it):

> **Ownership diagnostic:** PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

---

## 1. System Design

**1.1 [DYD]** Design an email campaign system that sends to 500k recipients and must survive worker crashes mid-send without duplicating mail. Defend each mechanism you add.
*Grounding: campaigns README. Pointers: atomic claim (state transition scheduled→sending via CAS so two workers can't both win), attempt-id fencing on terminal writes, checkpoint after accepted batches only, resume from checkpoint, failed-recipient store for partial retry; name the failure each mechanism kills.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**1.2** Reporting dashboards over an append-only event log of 200M+ rows are timing out. Walk through your options and pick one.
*Grounding: ADR-0008. Pointers: read-time aggregation degrades linearly; options = pre-aggregated counters on the write path, async materialized views (staleness), OLAP store (new infra), caching (staleness + invalidation); idempotent counter + dedup-state design; rebuildability from the source-of-truth log; two-phase-write drift tradeoff.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**1.3 [WBI]** In a "snapshot audience at t=0, follow up at t=wait" design, what breaks if you *don't* snapshot and instead re-evaluate the audience at t=wait?
*Grounding: campaigns README (follow_up). Pointers: audience drift → people who never got the parent get the follow-up (and vice versa); targeting correctness as an invariant; snapshot immutability; also discuss the cost of the snapshot and when re-evaluation is actually correct (e.g., suppression must still apply at t=wait).*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**1.4 [ALT]** You need unique-per-user counts (opens, clicks) in near-real-time. Compare: `$addToSet` arrays on the metric doc, a dedup collection with conditional upserts, HyperLogLog, and batch dedup jobs. Which and why?
*Grounding: ADR-0008 alternatives table. Pointers: array → 16MB doc limit; HLL → approximate, no per-user lookup for bot/attribution needs; batch → staleness; conditional upsert (`$ne`-guarded set + upsert, E11000-tolerant) = exact, idempotent, lock-free CAS.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**1.5** Design a webhook ingestion pipeline for a third-party ESP (millions of delivery/open/click events/day). Cover verification, idempotency, ordering, and backpressure.
*Transferable (grounding: ADR-0014, sendgrid-webhooks). Pointers: signature verification before trust; provider event-id dedup (partial unique index); out-of-order tolerance (event hierarchy: click implies open implies delivered); queue as buffer; poison-message handling; replay from provider vs from stored log.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**1.6** When does a queue belong in a design, and when is it the wrong tool? Give concrete failure modes queues introduce.
*Transferable (grounding: ADR-0004/0016 experience). Pointers: decoupling/retry/leveling vs added failure modes — duplicate delivery, reordering, stalled jobs, backlog as a new alert surface, broker as a dependency; "a queue converts a sync failure into an async liability you must now observe."*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**1.7 [ALT]** Event-driven architecture: when do you choose explicit orchestration (direct calls) over pub/sub? Give a litmus test and defend it against "everything should be events."
*Grounding: ADR-0009. Pointers: the decision tree — producer needs the result → direct; subscriber can fail independently + different aggregate → pub/sub; targeting-correctness test ("if this fails silently, does it change who gets targeted?"); distributed-monolith syndrome; why priority-ordered listeners are orchestration in disguise; rejected alternatives (documented ordering, DB state machine, all-pub/sub-with-retries, saga).*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**1.8 [DYD] ⚑** Present websand-v4's architecture in 5 minutes as a whiteboard system-design answer: tenants, ingestion, profile state, segmentation, sends, webhooks, metrics. Defend the two decisions an interviewer is most likely to attack (single Mongo, no cache tier).
*Grounding: whole repo. Pointers: know your numbers (events volume, batch size 50, dedup index names); concede the scaling ceiling honestly and describe the sharding/cache path you'd take.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

---

## 2. Backend / Concurrency

**2.1** What is a lost update? Give the three standard remedies and the tradeoffs between them.
*Transferable (grounding: ADR-0013). Pointers: read-modify-write race; remedies = pessimistic locking (lock service, serialized throughput, new failure domain), optimistic CAS (version match + retry, latency under contention), atomic operators (`$inc`) when the mutation doesn't depend on prior state; when each wins.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**2.2 [WBI]** In an optimistic-CAS loop, what breaks if a side effect (e.g., recording a transaction) fires *inside* the compute step instead of after the CAS write wins?
*Grounding: ADR-0013, profiles README. Pointers: losing attempts replay → side effect fires multiple times; compute must stay pure so retry = recompute; defer side effects to the winning attempt; connect to idempotency of the deferred effect itself.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**2.3** Why is incrementing a money field with `$set: {total: computedValue}` dangerous, and when is `$inc` of a delta not enough either?
*Grounding: profiles README (LTV). Pointers: absolute set from stale read clobbers concurrent increments; `$inc` is atomic but insufficient when the new value depends on prior state across fields (that's what CAS is for); finite-guard on deltas (NaN poisoning from bad upstream data).*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**2.4 [WBI]** A worker computes a profile's next automation step as `currentOrder + 1` and writes it with `$inc`. What breaks under a duplicate retry, and what's the fix?
*Grounding: engines README. Pointers: two increments → step skipped (order+2); fix = write the absolute value computed from the claimed step + idempotency guard (already-success short-circuit); general principle: retries make relative updates dangerous.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**2.5 [DYD]** Defend "consolidate all state mutations for an aggregate into one explicit function" against "small subscribers are more modular."
*Grounding: ADR-0009 consequences. Pointers: deterministic order, single transaction boundary, testable as a pure function; cost = large function, compile-time coupling; the coupling existed anyway, hidden behind emitter priorities; aggregate boundary = ownership boundary.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**2.6** How do you make a "claim" atomic in a document store with no distributed lock manager? Two patterns.
*Grounding: engines/campaigns READMEs. Pointers: (a) upsert with `$setOnInsert` on a unique key — exactly one inserter wins, loser gets E11000 and takes the resume path; (b) `findOneAndUpdate` with a status-filter CAS (scheduled→sending) — loser matches nothing; both are single-document atomicity, no lock service.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**2.7** What's a convoy/hot-document problem under optimistic concurrency, and what would you do if one profile received 1000 concurrent events?
*Transferable (grounding: ADR-0013 negatives). Pointers: CAS retries thrash, bounded retry exhausts → errors; mitigations = per-key serialization (queue partitioning by profile id), operator-only mutations where possible, batching/coalescing events, escalate to pessimistic lock for pathological keys.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**2.8 [ALT]** For in-process cross-domain reactions (e.g., "after event insert, update engine bookkeeping"), compare: ordered event emitters with priorities, unordered pub/sub with idempotent handlers, and direct calls. Why did ordered emitters lose?
*Grounding: ADR-0009. Pointers: implicit ordering = correctness by convention, silently breakable by a new listener; cancel/mutate hooks make it orchestration; direct calls for same-aggregate atomic needs, pub/sub only for independently-retryable different-aggregate reactions.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**2.9 [DYD]** Your architecture docs prescribe functional-core services returning `Result<T,E>` via a Reader monad, but much of what shipped throws typed errors classified once at the job boundary. Defend the shipped reality, say where it hurts, and give the trigger that would justify migrating.
*Grounding: ADR-0003/0007, patterns-backend "as actually shipped" section. Pointers: thrown-typed-errors + boundary classification is pragmatic (less ceremony, one retry-semantics seam); costs = error paths invisible in signatures, harder composition/partial-failure typing, tests must assert on throws; migrate when a domain's error handling gets branchy enough that callers keep catching-and-inspecting; the meta-lesson — document the divergence instead of pretending the ideal shipped.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

---

## 3. Database / Data Modeling

**3.1** When do you enforce uniqueness with a partial unique index vs a full unique index vs application-level preflight checks? Why might you need both a preflight *and* the index?
*Grounding: profiles README dedup. Pointers: partial = uniqueness only where the field exists (sparse event ids); preflight gives clean early return + avoids exception-driven flow, but the index is the only true guard under concurrency; map E11000 to an ok-no-op; race window between preflight and insert.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**3.2 [WBI]** What breaks if you model "has user X done action Y for campaign Z" as an array of user ids on the campaign document?
*Grounding: ADR-0008 alternatives. Pointers: unbounded array → 16MB document limit, index bloat on array fields, write contention on one hot doc; fix = one dedup doc per (campaign, user) with compound `_id`, or bucketing; general unbounded-array anti-pattern.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**3.3** Design the schema for an immutable event log that serves both per-entity replay and account-wide analytics at 10⁸ rows. Which indexes, and what do you refuse to index?
*Transferable (grounding: profileEvents). Pointers: append-only, tenant-scoped compound indexes (accountId + entity + time), partial unique for dedup keys, no unfiltered scans/counts, hint() on hot paths, TTL/archival policy, rebuildability of derived data as the escape hatch.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**3.4 [ALT]** For weekly time-series charts (unique users per day per campaign), compare MongoDB time-series collections, a normalized fact table + rollups, cron materialized views, and inline-upserted daily counter docs. Which won and why?
*Grounding: ADR-0008. Pointers: time-series collections = append-only, can't do conditional upserts; fact+rollup doubles writes; cron = staleness; daily counter docs keyed (campaign, day) → read = indexed find of ≤7 docs; write amplification accepted consciously (4 writes/event).*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**3.5 [DYD]** Defend schema-on-write validation (Zod/JSON-Schema at the boundary) in a schemaless database against "Mongo is flexible, validate later."
*Grounding: ADR-0010, shared schemas. Pointers: SSOT schema shared client/server, versioned evolution, garbage-in costs surface at read time otherwise (NaN LTV from bad `total`); validation at edge + typed domain beats defensive checks scattered everywhere; where to be tolerant (legacy version-less docs).*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**3.6** How do you evolve a document schema on a live collection with hundreds of millions of rows (e.g., adding a `version` field)? What must the code tolerate during the transition?
*Grounding: ADR-0013 legacy handling. Pointers: tolerant reads (`{version: {$in: [0, null]}}` because a missing field ≠ 0), lazy migration on first write ($inc seeds), backfill scripts for the tail, never a blocking migration; the "matching {version: 0} exactly excludes legacy docs" bug class.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**3.7 [WBI]** Your ORM/driver does `updateOne({_id}, {$set: {...}})` for an admin edit while a CAS loop owns the same document. What breaks?
*Grounding: ADR-0013 negatives, write-ownership doc. Pointers: raw writes bypass the version fence → lost updates return; need a per-field write-ownership contract (who writes what, with which operator), enforced by review/repository helpers; version bump discipline for co-writers.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**3.8** When is a multi-document transaction in MongoDB the right call, and when do you deliberately go non-transactional?
*Grounding: outbox (ADR-0016) vs delete cascade (campaigns README). Pointers: transaction for atomic outbox row + domain write; deliberately non-transactional for unbounded deletes (cascade sized beyond txn limits) — instead order operations so a mid-failure stays retryable (delete the parent doc last); idempotent cleanup over 2PC.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

---

## 4. Distributed Systems / Reliability

**4.1** Explain the transactional outbox pattern from scratch: the problem, the mechanism, and its residual failure modes.
*Grounding: ADR-0016. Pointers: dual-write problem (DB commit vs enqueue crash window loses or orphans work); outbox row in the caller's txn, broker push after commit, push failure rolls back; residuals = push-after-commit crash needs a relay/reconciler, duplicate pushes need broker idempotency (jobId = row id).*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**4.2 [WBI]** Crash windows: a worker sends an email, then crashes *before* recording "sent." Its retry runs. Walk through what happens with (a) no claim record, (b) a claim checked for existence, (c) a claim checked for status="sent". Which is correct and what does it cost?
*Grounding: engines README resume gate. Pointers: (a) double-send; (b) existence ≠ proof of send — crashed-before-send owner means the email is silently dropped and reported sent; (c) correct: sent→resume, dispatching-not-ours→transient error/backoff, fresh→dispatch; cost = ambiguous rows need sweeper + human reconciliation; under-send bias for money-critical effects.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**4.3** "Exactly-once delivery" — what's actually achievable, and what do you build instead?
*Transferable (grounding: ADR-0016 alternatives). Pointers: brokers give at-least-once (or at-most-once); exactly-once *processing* = at-least-once delivery + idempotent effects (deterministic ids, claims, dedup keys); the effect boundary (ESP API without idempotency keys) is where guarantees end.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**4.4 [DYD]** Defend "the stalled-work sweeper only counts and alerts; a human runs the reconcile" against "automate the recovery, humans are slow."
*Grounding: engines/campaigns sweepers. Pointers: a row stuck mid-dispatch is in an *unknown* state — auto-resend converts unknown into a known-bad double-charge; asymmetric cost (under-send recoverable, double-send isn't); automation is fine for provably-safe transitions (status flip of a claim with no live job) but not ambiguous ones; gauges + operator CLIs with dry-run/apply.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**4.5 [WBI]** What breaks if a stalled-campaign sweeper flips a stuck follow-up *parent* campaign to `failed` — status only — and moves on?
*Grounding: campaigns README swept-parent; memory of the bug class. Pointers: recovery was per-object, not per-workflow — the child stays stranded (its enqueue hook never fires and every send path rejects a failed parent); dependents of a swept object need reconciliation or a health probe (stranded-children gauge); "sweeper fixed the status, orphaned the workflow" is a general class.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**4.6** Retries: how do you decide something is safe to retry? Design a classification scheme for errors in a job system.
*Grounding: error-classifier, coding rules. Pointers: transient (infra, rate limits) → retry with backoff; permanent (validation, business rule) → dead-letter/park, don't burn retries; ambiguous (timeout mid-side-effect) → the dangerous class, needs idempotency before retry is safe; classify once at the job boundary, not per call site.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**4.7** Where does backpressure come from in a queue-based pipeline and how do you handle a 10k-job backlog page?
*Grounding: runbook queue-backlog playbook. Pointers: producers outpacing consumers, poison jobs, downstream (ESP) slowness/rate limits; triage = is it one queue or all (worker down vs load), pause producers (kill switches/pausedQueues), scale consumers, drain poison, replay; why unbounded retries make backlogs worse.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**4.8 [ALT]** To prevent duplicate side effects you can: rely on broker exactly-once, use a distributed lock around the send, or use a durable claim + deterministic ids. Compare failure modes; why did the lock lose?
*Grounding: ADR-0016/0013 alternatives. Pointers: broker exactly-once unavailable/mythical at the effect boundary; lock = lease expiry during a slow send re-admits a second sender, lock service is a new failure domain, and a crashed holder still leaves ambiguity; claim is *durable evidence* (survives crashes) rather than mutual exclusion in time.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**4.9** Two-phase writes without a transaction (dedup mark, then counter increment). A crash lands between them. How do you design so this drift is acceptable?
*Grounding: ADR-0008 negatives. Pointers: order the phases so drift is detectable/one-sided; keep a rebuildable source of truth (event log) + backfill scripts as the reconciler; idempotent replay (the dedup layer absorbs re-processing); accept eventual consistency for metrics, never for money.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**4.10 ⚑** Tell the story of a correctness bug this architecture was built to kill (double-charge on engine emails, or the checkpoint-eagerly bug that skipped failed recipients). Structure it as incident → root cause → invariant → enforcement → test pin.
*Grounding: ADR-0016 A1; campaigns T1.2. Pointers: name the invariant precisely; show the test that pins it; the pattern "invariant → consequence → evidence" is your differentiator.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

---

## 5. Security / Multi-Tenancy

**5.1** How do you make tenant isolation an *invariant* rather than a convention in a shared-database SaaS?
*Grounding: profiles/campaigns READMEs, CLAUDE.md rule. Pointers: every query/write carries accountId including CAS filters, claim keys, unique indexes, and re-reads; enforced by review/lint + repository conventions; compound indexes lead with accountId; per-tenant credentials (ESP key per account, no global fallback); test it with cross-tenant integration tests.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**5.2 [WBI]** What breaks if the CAS filter is `{_id, version}` without `accountId` — given `_id`s are globally unique anyway?
*Grounding: ADR-0013. Pointers: defense-in-depth: a leaked/forged id becomes a cross-tenant write; index locality; the deeper answer — the invariant must hold *uniformly* or reviewers can't spot violations; uniform rules are cheaper than clever exceptions.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**5.3 [DYD]** Defend RBAC as code (enum roles → permission sets → procedure middleware) against RBAC as data (permissions rows in the DB, admin-editable).
*Grounding: packages/shared/schema/rbac.mts, permissionProcedure. Pointers: code = type-checked, reviewable, testable, the doc matrix can't drift from enforcement (SSOT); data = runtime flexibility, custom roles per tenant, but drift/audit complexity; hybrid path when customers demand custom roles; deny-by-default.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**5.4** Where do you verify inbound webhooks, and what does "verify before trust" mean concretely for an ESP webhook?
*Grounding: ADR-0014. Pointers: signature (ECDSA/HMAC) verification before parsing/side effects; replay protection (timestamp tolerance); why IP allowlists are weak; treat the payload as attacker-controlled until verified; per-endpoint secrets rotation.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**5.5** An authenticated tRPC/REST mutation is protected by a permission check. List the *other* authorization mistakes that still let data leak.
*Transferable. Pointers: IDOR — permission checked but object not tenant-scoped (permission says "can edit campaigns", query must say "this tenant's campaign"); mass-assignment on patch inputs; list endpoints leaking cross-tenant via missing filters; derived/aggregate endpoints; client-enforced-only gating (feature flags default-off/fail-closed as an analogue).*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**5.6 [WBI]** What breaks — legally and technically — if suppression-list updates (unsubscribe/bounce) are handled as a best-effort async subscriber instead of synchronously in the event path?
*Grounding: ADR-0009 classification (compliance-critical). Pointers: a lost unsubscribe → mail to an opted-out user → CAN-SPAM/GDPR exposure; targeting correctness test says direct call; contrast with metrics (eventual OK); compliance semantics dictate the consistency model, not architecture taste.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**5.7** How do you keep PII out of logs in a system that processes contact data, without neutering debuggability?
*Grounding: engines README (ids only), logging practice. Pointers: log ids not addresses, structured logging with allowlists, hash/tokenize when correlation is needed, redaction at the logger seam, distinct treatment of transient debug vs retained logs; test the seam.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

---

## 6. Testing / Quality

**6.1 [DYD]** Defend "integration tests against a real database engine (in-memory mongod) for concurrency invariants" against "mock the DB, it's faster."
*Grounding: version-cas / process-engine-email integration tests. Pointers: CAS filter semantics, E11000 races, and index behavior *are the subject under test* — mocks assert your assumptions back at you; unit tests for pure compute (apply-event), integration for filter/update/index semantics, both in the pyramid; cost control (no-parallelism for mongod contention).*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**6.2** What is an invariant "pin" test, and how does it differ from coverage-driven testing? Give two invariants worth pinning in any money-touching system.
*Grounding: status-transitions.test, T1.2 regression. Pointers: a test that exists to make a specific correctness property unbreakable (a failed batch is never checkpointed; a terminal write requires the attempt-id fence); regression-born; pins survive refactors because they test the property, not the implementation; coverage measures execution, not protection.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**6.3 [WBI]** What breaks if your test seam for the email provider returns success *before* building the actual provider payload?
*Grounding: send-mail test seam (MailService.prototype spy vs EMAIL_PROVIDER=mock). Pointers: the blind spot class — a mock that short-circuits upstream of the logic hides payload bugs (recipient leaks); spy at the last seam before the wire; contract tests for the provider adapter; "mock the boundary, not the middle."*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**6.4** How do you test a race condition deterministically (two workers claiming the same job)?
*Grounding: profile-engine-handler.integration.test. Pointers: real engine + controlled interleaving (fire both claims concurrently, assert exactly one upsert wins / loser gets E11000), or inject sync points; property: run N times in CI without flake; distinguish testing the *outcome invariant* (no double-advance) from timing specifics.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**6.5** Where do E2E tests earn their cost in a product like this, and where are they waste?
*Grounding: testing guidelines, Playwright/VRT/a11y configs. Pointers: earn: auth boundaries, the send-critical happy path, RBAC-gated UI; waste: exhaustive form permutations (unit/component), visual regressions (VRT snapshots instead), logic already pinned by integration tests; the testing decision tree idea; seed-user recipe for authed flows.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**6.6** Your coverage gate is 80% overall / 95% critical-path. An engineer asks why not 100%. Answer as the person who set the gate.
*Transferable. Pointers: marginal cost curve, assertion-free coverage theater, criticality tiers (money/compliance paths get 95+ and invariant pins), mutation-testing as a better signal, gates as ratchets not goals.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**6.7 [ALT]** For validating request/response contracts between your API and client, compare: shared type packages (tRPC end-to-end types), OpenAPI codegen, and consumer-driven contract tests. When does each win?
*Grounding: ADR-0002 tRPC, monorepo shared schemas. Pointers: tRPC/shared-Zod wins in a monorepo (compile-time, zero drift); OpenAPI when consumers are external/polyglot; CDC when teams deploy independently; the monorepo assumption is load-bearing — say it.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

---

## 7. Operations / Debugging

**7.1** You're paged: 5xx rate just crossed 10%. First three commands/dashboards, and the differential you're building in your head.
*Grounding: runbook alert playbook. Pointers: recent deploy? external dep (DB/Redis/ESP/auth) down? one endpoint or all? error logs by route/code; the discipline of putting external-dependency availability on the differential before anchoring on your own commits; rollback criteria and who decides.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**7.2** "Data stopped updating on the 14th" — a customer report. Describe your triage tree.
*Grounding: runbook, pausedQueues memory. Pointers: check kill switches/paused queues and feature flags FIRST (operational state before code), then queue backlogs/DLQ, then webhook delivery (provider dashboard), then ingest dedup misfires; date-bounded log/event queries; communicate scope (one tenant or all).*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**7.3 [WBI]** What breaks operationally if your queue metrics are emitted through a gauge helper that caches by metric name only (one series), while you emit per-queue values?
*Grounding: satoshibits gauge single-series memory / observability notes. Pointers: series clobbering → last-writer-wins gauge lies to you during an incident; dashboards show one queue's depth as all queues; fix = per-series instruments or one callback yielding labeled points; verify observability plumbing like product code — a wrong metric is worse than none.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**7.4** How do you trace one email through a system that spans web request → outbox row → queue job → worker → ESP webhook, hours apart?
*Grounding: ADR-0017, W3C traceparent propagation. Pointers: propagate trace context through the job payload (queues break automatic propagation), deterministic/correlated ids (queueId, emailId) as the join keys, structured logs keyed on those ids, webhook events carry provider message-id ↔ your id mapping; "the id scheme IS the observability design."*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**7.5 [DYD]** Defend shipping an operator CLI with dry-run-by-default + `--apply` for data corrections, versus an admin UI button or ad-hoc mongo shell.
*Grounding: reconcile CLI, runbook data corrections. Pointers: preview = blast-radius check; CLIs are reviewable/versioned/testable, encode the safe transition (CAS shape) so operators can't fat-finger a raw update; shell = no guardrails; UI button = invites casual use of a dangerous op; audit fields (recoveredBy).*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**7.6** A campaign is stuck in `sending` for 3 hours. Walk through diagnosis and safe recovery, including how you *avoid* making it worse.
*Grounding: runbook stuck-campaign playbook. Pointers: is the worker alive/progressing (checkpoint advancing?), is there a live queue row, progress-aware cutoffs; sweep to failed (status-only) vs the reconcile path for delivered-but-swept parents; never blind-resend without knowing what was dispatched; badge recomputation.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**7.7** What belongs in a runbook entry for an alert, and how do you keep runbooks from rotting?
*Transferable (grounding: runbook structure). Pointers: symptom → hypotheses ranked by prior → commands with expected output → decision points → escalation + comms; keep commands copy-pasteable; rot control = review dates, drills, delete-on-obsolete, link playbooks from the alert itself.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**7.8** Emergency stop: you need to halt all outbound email in production *now* without taking the API down. What does the design need to have had in place?
*Grounding: pausedQueues/kill switches, runbook emergency procedures. Pointers: layered kill switches (pause queues, per-feature sendEmails flag), workers checking pause state mid-drain (onPauseCheck between batches), fail-closed defaults, and a resume path that doesn't replay-duplicate; you can't bolt this on during the incident.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

---

## 8. Behavioral / Project Narrative

**8.1 ⚑** "Tell me about the most technically challenging thing you've built." Deliver the idempotent-dispatch story in STAR form, 3 minutes.
*Pointers: Situation = money-critical sends over at-least-once queue; Task = never zero, never twice; Action = outbox + deterministic claim + sent-before-bookkeeping + sweeper; Result = pinned by integration tests, zero double-charges; close with the residual you consciously deferred (campaign path, T2W-IDEM-1) — honesty is the senior signal.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**8.2 ⚑** "Tell me about a production incident you caused or owned." Use the tags-`$push` path-conflict outage or the OOM from materializing an audience cursor.
*Pointers: detection → user impact → root cause (mechanism, not blame) → fix → the invariant/pitfall doc + test that makes recurrence impossible; show the pitfalls section exists because of these.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**8.3 [DYD] ⚑** "Why did you write 20 ADRs for a small team? Isn't that process theater?" Defend the practice with concrete payoffs.
*Pointers: decisions with blast radius get adversarial review (multi-model), alternatives recorded so they aren't relitigated, onboarding/interview asset, honesty sections track ideal-vs-shipped divergence; concede lightweight is key — ADRs for one-way doors, not everything.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**8.4 ⚑** "Tell me about a time you chose the boring/simple solution." (Direct calls over saga/workflow infra; daily counter docs over a time-series store.)
*Pointers: ADR-0009 rejected saga as premature, ADR-0008 rejected new infra; articulate the trigger conditions that would revisit (scale, team count); YAGNI with an exit plan reads as judgment, not laziness.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**8.5 ⚑** "Describe a disagreement about technical direction and how you resolved it." Frame a multi-model review disagreement (e.g., Gemini's DB-state-machine suggestion rejected in ADR-0009) or the correctness-over-parity call on V1 regressions.
*Pointers: steelman the losing option, name the decisive criterion (over-engineering for in-process calls; previous version was already buggy), show the decision was recorded; if pressed on human collaboration, pivot to invited-review discipline honestly.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**8.6 [WBI] ⚑** "What's the weakest part of your system?" — answer without self-sabotage.
*Pointers: pick real, bounded gaps (single unsharded Mongo with a stated ceiling; campaign-path idempotency lighter than engine path; no SLOs) + the mitigation and the trigger to fix; never say "nothing"; never pick something core and unmitigated.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**8.7 ⚑** "Where do you want to grow next, and why does this role fit?" Tie the Staff-gap list to the target company honestly.
*Pointers: cross-team influence, scale beyond one node (sharding/caching), SLO practice; map each to something the company actually has; avoid "I want to learn on your dime" framing — you bring the correctness discipline, they bring the scale.*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

**8.8 ⚑** "Walk me through how you'd onboard a new engineer to your codebase in week one." (Tests communication and the docs system.)
*Pointers: 30-second mental models per service README, the decision-tree docs, runbook shadowing, first PR = extend a pinned test; what you'd fix about the onboarding (docs assume solo context).*
*Ownership diagnostic:* PE=`?` · ORIG=`?` · COLD=`?` · CLAIM=`?` · ROUTE=`?`

---

## Coverage checklist (the 12 mandatory areas)

| # | Area | Questions |
|---|---|---|
| 1 | Outbox / idempotency / retries | 4.1, 4.2, 4.3, 4.6, 4.8, 1.6, 8.1 |
| 2 | Optimistic CAS + operator discipline | 2.1, 2.2, 2.3, 2.7, 3.6, 3.7, 5.2 |
| 3 | Campaign send state machine | 1.1, 2.6, 4.10, 7.6 |
| 4 | Metrics pre-aggregation at scale | 1.2, 1.4, 3.2, 3.4, 4.9 |
| 5 | Orchestration vs pub/sub | 1.7, 2.5, 2.8, 5.6 |
| 6 | Mongo modeling: indexes, tenancy, cursors | 3.1, 3.3, 3.8, 1.8 (OOM pitfall), 3.2 |
| 7 | BullMQ/Redis: stalled jobs, concurrency, backpressure | 1.6, 4.7, 7.2, 7.8 |
| 8 | Multi-tenancy + RBAC | 5.1, 5.2, 5.3, 5.5 |
| 9 | Recovery sweepers / surface-don't-resend | 4.4, 4.5, 7.5, 7.6 |
| 10 | Testing strategy + invariant pins | 6.1–6.7 |
| 11 | Ops / runbook incident reasoning | 7.1–7.8 |
| 12 | Known gaps (sharding, cache, idempotency asymmetry, partial FP) | 1.8, 2.9, 8.6, 8.7, 8.1 (residual) |

**[ALT] count:** 1.4, 1.7, 2.8, 3.4, 3.8*, 4.8, 6.7, plus alternatives embedded in 1.2, 2.1, 4.3, 5.3, 7.5 → 12 questions require comparing rejected designs.
