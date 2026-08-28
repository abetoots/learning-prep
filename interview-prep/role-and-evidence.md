# Target Role & Evidence Calibration

## The role to aim for

**Senior Software Engineer — Backend / Product Platform** (interchangeably titled *Senior Backend Engineer*, *Senior Full-Stack Engineer (backend-leaning)*, or *Senior Product Engineer* depending on company). At smaller companies (< ~50 engineers) the same evidence supports **founding/lead backend engineer** framing, where end-to-end ownership counts more than org-scale influence.

**Not (yet) the role:** Staff/Principal Engineer at a mid-size or large company, or infrastructure/SRE specialist. See "What's missing for Staff" below — claiming it without that evidence invites a leveling down-round in the interview loop.

## Why this claim is credible (demonstrated evidence)

Each row is a claim you can defend in an interview, with the artifact that proves it.

**The claim verb has to survive a cold attempt.** The repo was built partly with agentic coding, so some of these designs were AI-proposed and only approved. When the Week 1 cold-gate in `study-plan.md` — or a first cold pass on the matching question-bank item — shows you can't defend a row from a blank page, rewrite its verb: "Designs for…" → "Can defend the design of…" or "Evaluated and approved…". Don't rewrite before you know. Only you can judge this; no AI or git history can.

| Claim | Evidence in websand-v4 |
|---|---|
| Designs for at-least-once delivery: transactional outbox, broker-level idempotency (`jobId = _id`), durable dispatch claims, resume-only-on-`sent` | `docs/adr/0016-idempotency-durable-dispatch-queue-work.md`; `apps/server/src/services/queue/client.mts`; `services/queue/workers/process-engine-email.mts` |
| Prevents lost updates under concurrent writes with optimistic-version CAS + bounded retry, and knows when operators (`$inc` of a delta) are the right tool instead | `docs/adr/0013-optimistic-cas-core-mutable-documents.md`; `services/profiles/index.mts`; `docs/guidelines/profiles-write-ownership.md` |
| Builds crash-safe long-running work: state-machine sends with CAS claims, `sendAttemptId` fencing, accepted-batch-only checkpoints, recipient-level retry | `services/campaigns/README.md`; `send-batch-loop.mts`; `status-transitions.mts` |
| Chooses recovery philosophy deliberately: sweepers that *surface* ambiguity instead of auto-resending, because under-send beats double-charge | `services/engines/recover-stalled-dispatches.mts`; `services/campaigns/recover-stalled-sending.mts`; reconcile CLI |
| Scales reads against a 150–200M-doc event log with idempotent pre-aggregated counters (CQRS-ish two-layer model) instead of `$facet` scans | `docs/adr/0008-campaign-metrics-pre-aggregation.md`; `services/campaigns/metrics.mts` |
| Replaced an implicit-ordering event-emitter "distributed monolith" with an explicit orchestration-vs-pub/sub decision framework | `docs/adr/0009-orchestration-vs-pubsub.md`; `services/profiles/apply-event-to-profile.mts` |
| Enforces multi-tenancy as a code invariant (every query carries `accountId`, including CAS filters and claim keys) and code-backed RBAC (role→permission sets + `permissionProcedure` across ~28 routers) | `packages/shared/schema/rbac.mts`; `docs/operations/security.md` |
| Tests invariants, not lines: real-mongod integration tests pinning CAS semantics, duplicate-claim races, checkpoint-resume, E11000 dedup paths | `version-cas.integration.test.mts`; `process-engine-email.integration.test.mts`; 80/95/90 coverage gates |
| Operates what they build: ~1300-line runbook with alert playbooks, stuck-campaign recovery, queue-backlog triage, emergency procedures; OTel metrics/traces | `docs/operations/runbook.md`; `docs/adr/0017-opentelemetry-observability.md` |
| Writes decision records and is honest about divergence between the ideal and the shipped (thrown typed errors vs the Reader/Result ideal; `T2W-IDEM-1` residual) | 22 ADRs in `docs/adr/`; `docs/future/tier2-warn-infra-backlog.md` |
| Full-stack capable: React 19 + tRPC v11 end-to-end typesafety, TanStack Query, feature-flag bridge (OpenFeature/Unleash), Playwright E2E + VRT + a11y | `apps/client`; `docs/adr/0002`, `0019` |

## Where sophistication is concentrated (say this out loud)

Reliability, data consistency, multi-tenancy, queue-backed work, and operations. **Not**: frontend craft as a differentiator, big-infra (Kubernetes, service meshes, multi-region), or ML. Interview positioning should lead with the distributed-systems correctness story and treat full-stack as range, not the headline.

## AI collaboration evidence

2026 senior loops probe this directly — AI-permitted coding rounds, take-homes that ask how you used AI, and PR-review-of-AI-generated-code rounds. These are **additive to** the traditional rounds, not replacements for them. The signal an interviewer is looking for is a *boundary*: someone who can say what they delegate, what they verify, and what they never outsource. Candidates who over-rely can't produce that boundary, and candidates who abstain can't either.

| Claim | Evidence |
|---|---|
| Uses AI for critique and adversarial review rather than answer generation | This prep package and `~/learning-system/LEARNING-SYSTEM.md` were both produced through multi-model adversarial review (Codex / Gemini / Claude), with a recorded changelog showing what each model *changed* — including where the orchestrating model was wrong |
| Catches confident-wrong AI output | *(fill in: one concrete case where a model asserted something false and you caught it — what the claim was, how you noticed, what it would have cost.)* **This is the highest-value row here; it is the one an over-reliant candidate cannot produce.** |
| Reviews AI-generated code against invariants, not just behaviour | *(fill in: a PR-style review where you checked tenancy, idempotency, or failure modes rather than whether it ran.)* |
| Has an explicit delegation boundary | Delegates: scaffolding, test generation, refactors, doc drafts, unfamiliar-API lookup. Verifies: anything touching money, tenancy, or retry semantics. Never outsources: the correctness argument, or the decision recorded in an ADR |
| Knows where AI degrades their own ability, and measures it | Attempt-first policy; error log carries the confidence-before column; the same discipline is applied to how the prep itself is run |

Fill the two blank rows only with a real remembered case, or leave them blank. An invented example is worse than an honest gap — and the `caught` value in `error-log.md`'s AI column exists to capture the first real one the day it happens.

**Framing in the loop:** lead with the boundary, not the tooling. "Here's what I hand off and here's what I refuse to hand off, and here's a time the model was confidently wrong and what it would have cost" is a senior answer. A list of tools you use is not.

## What's missing for Staff (the honest gap list)

If an interviewer probes "why not Staff?", or you're tempted to aim there:

1. **Cross-team influence.** Every artifact here is single-team (arguably single-person). Staff evidence is changing how *other* teams work — RFCs adopted org-wide, mentoring lineage, contested technical decisions brokered across orgs. Multi-model AI review is senior AI-fluency evidence (table above), not org influence — two different claims.
2. **Horizontal scale ownership.** One unsharded MongoDB cluster; pre-aggregation is a read-scaling mitigation, not a sharding/partitioning strategy. No capacity model, no load-shedding design, no multi-region story.
3. **No dedicated caching tier** beyond in-process `lru-cache` and Redis rate limiting — cache invalidation at scale is untested territory.
4. **No formal SLO/error-budget practice.** There are alerts and playbooks, but no SLOs, burn-rate alerts, or budget-driven prioritization.
5. **Idempotency asymmetry acknowledged but unresolved:** the campaign path carries a lighter variant than the engine path (`T2W-IDEM-1`) — fine to discuss, but "we shipped the full model everywhere" isn't claimable.

Frame these as *known next frontiers* ("here's exactly what I'd need to demonstrate for Staff, and here's my plan"), which itself reads as senior judgment.

## Positioning one-liner

> "I built and operate a multi-tenant email-marketing platform end to end — the interesting part is the correctness engineering: transactional outbox and idempotent dispatch so retries never double-charge, optimistic CAS so concurrent ingestion never loses updates, and pre-aggregation so reporting stays O(1) against a 200M-row event log. I write ADRs for the decisions and a runbook for the failures."
