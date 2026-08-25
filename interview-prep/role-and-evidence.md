# Target Role & Evidence Calibration

## The role to aim for

**Senior Software Engineer — Backend / Product Platform** (interchangeably titled *Senior Backend Engineer*, *Senior Full-Stack Engineer (backend-leaning)*, or *Senior Product Engineer* depending on company). At smaller companies (< ~50 engineers) the same evidence supports **founding/lead backend engineer** framing, where end-to-end ownership counts more than org-scale influence.

**Not (yet) the role:** Staff/Principal Engineer at a mid-size or large company, or infrastructure/SRE specialist. See "What's missing for Staff" below — claiming it without that evidence invites a leveling down-round in the interview loop.

## Why this claim is credible (demonstrated evidence)

Each row is a claim you can defend in an interview, with the artifact that proves it.

**Ownership tag column (added 2026-08-01):** self-tag only — never inferred by an AI from the ADR or the code, because whether you knew a design before it was proposed is a fact only you hold. Format: `PE=<prior exposure> · ORIG=<origination> · COLD=<current cold ability> · CLAIM=<claim strength>` (full legend in `question-bank.md`). Leave a row blank until you've run the item through the Week 1 ownership cold-gate. **Rule:** once a row's `CLAIM` is anything other than `designed`, rewrite that row's claim verb to match (e.g. "Designs for..." → "Can defend the design of..." or "Evaluated and approved...") — don't rewrite speculatively before you actually know the tag.

| Claim | Evidence in websand-v4 | Ownership tag |
|---|---|---|
| Designs for at-least-once delivery: transactional outbox, broker-level idempotency (`jobId = _id`), durable dispatch claims, resume-only-on-`sent` | `docs/adr/0016-idempotency-durable-dispatch-queue-work.md`; `apps/server/src/services/queue/client.mts`; `services/queue/workers/process-engine-email.mts` | *self-tag* |
| Prevents lost updates under concurrent writes with optimistic-version CAS + bounded retry, and knows when operators (`$inc` of a delta) are the right tool instead | `docs/adr/0013-optimistic-cas-core-mutable-documents.md`; `services/profiles/index.mts`; `docs/guidelines/profiles-write-ownership.md` | *self-tag* |
| Builds crash-safe long-running work: state-machine sends with CAS claims, `sendAttemptId` fencing, accepted-batch-only checkpoints, recipient-level retry | `services/campaigns/README.md`; `send-batch-loop.mts`; `status-transitions.mts` | *self-tag* |
| Chooses recovery philosophy deliberately: sweepers that *surface* ambiguity instead of auto-resending, because under-send beats double-charge | `services/engines/recover-stalled-dispatches.mts`; `services/campaigns/recover-stalled-sending.mts`; reconcile CLI | *self-tag* |
| Scales reads against a 150–200M-doc event log with idempotent pre-aggregated counters (CQRS-ish two-layer model) instead of `$facet` scans | `docs/adr/0008-campaign-metrics-pre-aggregation.md`; `services/campaigns/metrics.mts` | *self-tag* |
| Replaced an implicit-ordering event-emitter "distributed monolith" with an explicit orchestration-vs-pub/sub decision framework | `docs/adr/0009-orchestration-vs-pubsub.md`; `services/profiles/apply-event-to-profile.mts` | *self-tag* |
| Enforces multi-tenancy as a code invariant (every query carries `accountId`, including CAS filters and claim keys) and code-backed RBAC (role→permission sets + `permissionProcedure` across ~28 routers) | `packages/shared/schema/rbac.mts`; `docs/operations/security.md` | *self-tag* |
| Tests invariants, not lines: real-mongod integration tests pinning CAS semantics, duplicate-claim races, checkpoint-resume, E11000 dedup paths | `version-cas.integration.test.mts`; `process-engine-email.integration.test.mts`; 80/95/90 coverage gates | *self-tag* |
| Operates what they build: ~1300-line runbook with alert playbooks, stuck-campaign recovery, queue-backlog triage, emergency procedures; OTel metrics/traces | `docs/operations/runbook.md`; `docs/adr/0017-opentelemetry-observability.md` | *self-tag* |
| Writes decision records and is honest about divergence between the ideal and the shipped (thrown typed errors vs the Reader/Result ideal; `T2W-IDEM-1` residual) | 20 ADRs in `docs/adr/`; `docs/future/tier2-warn-infra-backlog.md` | *self-tag* |
| Full-stack capable: React 19 + tRPC v11 end-to-end typesafety, TanStack Query, feature-flag bridge (OpenFeature/Unleash), Playwright E2E + VRT + a11y | `apps/client`; `docs/adr/0002`, `0019` | *self-tag* |

## Where sophistication is concentrated (say this out loud)

Reliability, data consistency, multi-tenancy, queue-backed work, and operations. **Not**: frontend craft as a differentiator, big-infra (Kubernetes, service meshes, multi-region), or ML. Interview positioning should lead with the distributed-systems correctness story and treat full-stack as range, not the headline.

## AI collaboration evidence (added 2026-07-22)

2026 senior loops probe this directly — AI-permitted coding rounds, take-homes that ask how you used AI, and PR-review-of-AI-generated-code rounds. These are **additive to** the traditional rounds, not replacements for them. The signal an interviewer is looking for is a *boundary*: someone who can say what they delegate, what they verify, and what they never outsource. Candidates who over-rely can't produce that boundary, and candidates who abstain can't either.

| Claim | Evidence |
|---|---|
| Uses AI for critique and adversarial review rather than answer generation | This prep package and `~/learning-system/LEARNING-SYSTEM.md` were both produced through multi-model adversarial review (Codex / Gemini / Claude), with a recorded sign-off table showing what each leg *changed* — including where the lead was wrong |
| Catches confident-wrong AI output | *(fill in: one concrete case where a model asserted something false and you caught it — what the claim was, how you noticed, what it would have cost.)* **This is the highest-value row here; it is the one an over-reliant candidate cannot produce.** |
| Reviews AI-generated code against invariants, not just behaviour | *(fill in: a PR-style review where you checked tenancy, idempotency, or failure modes rather than whether it ran.)* |
| Has an explicit delegation boundary | Delegates: scaffolding, test generation, refactors, doc drafts, unfamiliar-API lookup. Verifies: anything touching money, tenancy, or retry semantics. Never outsources: the correctness argument, or the decision recorded in an ADR |
| Knows where AI degrades their own ability, and measures it | Attempt-first policy; error log carries the confidence-before column; the same discipline is applied to how the prep itself is run |

**Note on the two unfilled rows above (added 2026-08-01):** the ownership-gap work that produced the tag column in the evidence table above is directly relevant here, but don't shortcut it — fill "catches confident-wrong AI output" and "reviews AI-generated code against invariants" only with a real remembered case, or leave them unclaimed. A row filled with a plausible-sounding but invented example is worse than an honest blank, and is exactly the failure mode this whole package exists to avoid.

**Framing in the loop:** lead with the boundary, not the tooling. "Here's what I hand off and here's what I refuse to hand off, and here's a time the model was confidently wrong and what it would have cost" is a senior answer. A list of tools you use is not.

## What's missing for Staff (the honest gap list)

If an interviewer probes "why not Staff?", or you're tempted to aim there:

1. **Cross-team influence.** Every artifact here is single-team (arguably single-person). Staff evidence is changing how *other* teams work — RFCs adopted org-wide, mentoring lineage, contested technical decisions brokered across orgs. Multi-model AI review is interesting but is not a substitute for human org influence — *that remains true for the Staff claim specifically. It is separately usable as senior AI-fluency evidence; see the AI collaboration table above. Two different claims, don't conflate them.*
2. **Horizontal scale ownership.** One unsharded MongoDB cluster; pre-aggregation is a read-scaling mitigation, not a sharding/partitioning strategy. No capacity model, no load-shedding design, no multi-region story.
3. **No dedicated caching tier** beyond in-process `lru-cache` and Redis rate limiting — cache invalidation at scale is untested territory.
4. **No formal SLO/error-budget practice.** There are alerts and playbooks, but no SLOs, burn-rate alerts, or budget-driven prioritization.
5. **Idempotency asymmetry acknowledged but unresolved:** the campaign path carries a lighter variant than the engine path (`T2W-IDEM-1`) — fine to discuss, but "we shipped the full model everywhere" isn't claimable.

Frame these as *known next frontiers* ("here's exactly what I'd need to demonstrate for Staff, and here's my plan"), which itself reads as senior judgment.

## Positioning one-liner

> "I built and operate a multi-tenant email-marketing platform end to end — the interesting part is the correctness engineering: transactional outbox and idempotent dispatch so retries never double-charge, optimistic CAS so concurrent ingestion never loses updates, and pre-aggregation so reporting stays O(1) against a 200M-row event log. I write ADRs for the decisions and a runbook for the failures."
