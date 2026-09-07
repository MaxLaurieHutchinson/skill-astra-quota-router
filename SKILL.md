---
name: astra-quota-router
description: Preserve scarce Astra/Codex frontier-model quota by routing work according to decision risk. Keep architecture, high-blast-radius judgement, security/concurrency/consistency reasoning, unresolved hard diagnosis, and final acceptance with Astra; delegate bounded investigation, routine implementation, tests, benchmarks, documentation, and mechanical work to the cheapest capable model such as Luna, Sol, or Terra. Use when conserving Astra, avoiding Codex quota exhaustion, splitting work across model tiers, orchestrating subagents, creating bounded work packs, or running a plan-build-evidence-review loop.
---

# Astra Quota Router

Use frontier capacity as a scarce engineering resource.

Core rule:

> Keep architecture and acceptance expensive. Make bounded execution cheap.

Read `references/source-notes.md` only when provenance matters.
Read `references/work-pack-template.md` when creating delegated work packs.

## 1. Choose the operating mode

### Frontier-root mode

Use by default when Astra can remain the parent/root model.

Keep Astra responsible for:
- architecture and system boundaries;
- cross-cutting invariants;
- consequential trade-offs;
- final acceptance over concrete evidence.

Delegate bounded execution to cheaper workers.

### Frontier-gated mode

Use when the user explicitly wants to preserve a very small remaining frontier budget.

Let a cheaper capable orchestrator coordinate ordinary work. Call Astra only for:
- architecture freeze points;
- high-risk decisions;
- unresolved conflicting evidence;
- security, concurrency, consistency, ordering, or trust-boundary uncertainty;
- final acceptance when the change is consequential.

If the runtime cannot invoke another model directly, create hand-off prompts/work packs instead of pretending delegation occurred.

## 2. Classify work by decision risk

### Tier 0 — deterministic tooling first

Use local/deterministic tools before any model when they can answer the question reliably:
- grep/search;
- tests;
- build/type/lint commands;
- formatters;
- static analysis;
- benchmarks;
- diff inspection;
- schema/introspection tools.

Do not spend model quota rediscovering facts a deterministic command can return.

### Tier 1 — cheapest capable worker

Default routine bounded work here:
- named repository reconnaissance;
- locating files/symbols/call paths;
- routine implementation;
- focused refactors;
- test creation;
- benchmark execution;
- lint/type/build fixes;
- documentation;
- repetitive edits;
- data gathering;
- mechanical validation.

Use Luna or the runtime's cheapest capable coding/reasoning tier when available.

### Tier 2 — intermediate reasoning tier

Use Sol/Terra or equivalent when:
- Tier 1 returns incomplete or contradictory evidence;
- implementation spans several coupled components;
- broader synthesis is needed but architecture is already frozen;
- an independent review is valuable before frontier acceptance;
- the worker needs more reasoning depth but the decision is not frontier-critical.

Do not escalate merely because the first cheaper attempt was imperfect.

### Tier 3 — Astra / frontier judgement

Reserve for decisions where a wrong answer can create broad rework or hidden risk:
- architecture and system boundaries;
- cross-cutting invariants;
- distributed state, ordering, consistency, cache invalidation, or concurrency;
- security and trust boundaries;
- high-blast-radius migration strategy;
- ambiguous root-cause diagnosis after cheaper investigation stalls;
- trade-offs spanning multiple subsystems;
- consequential acceptance criteria;
- final review of material diffs/evidence.

Astra should normally decide **what must be true** and **what evidence proves it**, not perform every mechanical step.

## 3. Create bounded work packs

Never delegate a vague instruction such as `implement the feature`.

Every work pack must define:
- one concrete goal;
- explicit scope;
- invariants/constraints;
- required evidence;
- stop/escalation conditions;
- return format.

Keep independent packs separate.

For parallel writes:
- prefer isolated worktrees;
- assign an explicit merge owner;
- avoid concurrent edits to the same files unless the environment can reconcile them safely.

## 4. Require an evidence return contract

Do not accept a prose summary as proof of completion.

Require the worker to return, when applicable:
- exact files changed;
- diff/patch summary tied to those files;
- commands run;
- tests and pass/fail results;
- build/type/lint results;
- benchmark method and result;
- screenshots/runtime evidence for UI behaviour;
- assumptions introduced;
- unresolved failures;
- scope deviations.

If agreed evidence is missing, classify the work pack as incomplete.

## 5. Preserve context deliberately

Treat context as quota-bearing infrastructure.

- Read broad source material once when possible.
- Convert discovery into durable artefacts such as architecture notes, requirement maps, scoped file lists, work packs, or claim ledgers.
- Reuse those artefacts instead of repeatedly reloading raw history.
- Give each worker only the context required for its pack.
- Return compressed evidence, not a transcript of worker reasoning.
- Start fresh worker contexts for independent tasks when stale history adds noise.
- Reload raw sources only when a decision or claim fails traceability.

Do not compress away invariants, acceptance criteria, or evidence required for final review.

## 6. Escalate on evidence, not prestige

Escalate one tier when one or more are true:
- evidence conflicts and the worker cannot reconcile it;
- the task unexpectedly crosses important system boundaries;
- a security/concurrency/integrity invariant becomes uncertain;
- repeated attempts fail the same acceptance criterion;
- the worker proposes an architectural change outside its authority;
- the evidence is insufficient to determine correctness.

Do not escalate merely because:
- the task is large but decomposable;
- the cheaper worker made one correctable mistake;
- Astra is available;
- the user asked for `best model` without a risk reason.

## 7. Run frontier acceptance over evidence

For a material change, have Astra/frontier review only the information needed for the decision:

1. Restate the invariant/acceptance criteria.
2. Inspect the actual diff and verification evidence.
3. Check cross-cutting consequences the worker may have missed.
4. Check whether tests/benchmarks actually prove the intended behaviour.
5. Identify unsupported assumptions.
6. Return one verdict:
   - `ACCEPT`
   - `REVISE`
   - `ESCALATE`

For `REVISE`, create a new bounded work pack instead of taking over routine implementation.

## 8. Respect explicit quota constraints

When the user supplies a remaining quota or reserve target:
- record it in the routing plan;
- prefer frontier-gated mode as the reserve becomes more important;
- reduce repeated frontier passes;
- combine related frontier decisions into one checkpoint when safe;
- do not invent exact token/quota conversion rates;
- do not promise a percentage saving.

Model prices, quotas, availability, and effort settings can change. Route by risk and evidence rather than fixed multipliers.

## 9. Common failure modes

### Astra does everything
A single prompt asks Astra to discover, design, implement, test, benchmark, and review.

Correct by separating architecture/acceptance from bounded execution.

### Delegation without boundaries
A worker gets the whole repository and no evidence contract.

Correct by defining goal, scope, constraints, evidence, and stop conditions.

### Summary-only acceptance
The frontier model accepts the worker's narrative without inspecting changed code or verification output.

Correct by requiring real evidence.

### Premature escalation
Routine execution jumps to Astra after one imperfect cheaper attempt.

Correct by refining the pack or moving only one tier up.

### Re-reading everything
Every pass reloads the same repository and conversation.

Correct by persisting durable intermediate artefacts.

### Parallel edit collisions
Several workers modify the same files concurrently.

Correct by using worktrees or serialising dependent writes.

### Fake delegation
The model writes work packs and then executes every pack itself while claiming quota routing.

Correct by either use real delegation or return the work packs for another model/session to execute.

## 10. Output contract

For a substantial task, produce:

### Routing decision
- operating mode;
- what stays with Astra/frontier;
- what goes to Tier 0/1/2;
- why.

### Work packs
One per independent delegated outcome.

### Evidence contract
What each worker must return.

### Escalation conditions
What would justify a higher tier.

### Acceptance pass
Final frontier judgement over evidence.

For a trivial task that does not need Astra, say so and route it entirely to a cheaper tier.
