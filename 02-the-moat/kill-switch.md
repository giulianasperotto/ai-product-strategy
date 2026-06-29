# Kill Switch Audit

## Vendor Dependency Assessment

| Dimension | Current State | Risk Level | 48-Hour Action |
|-----------|--------------|------------|---------------|
| **Provider** | Undecided — evaluating Gemini Flash, Claude Sonnet, and GPT-5.4 mini. Profile generation requires short creative text (simple, low cost). Scheduling agent requires multi-step reasoning and action chaining (medium complexity, higher cost). Two features may route to different provider tiers. | M | Select one provider per feature tier for MVP: Small-tier model for profile generation, Mid-tier model for scheduling agent. Run cost-per-generation benchmarks before committing. |
| **Abstraction** | Architectural decision made: use an abstraction layer (e.g. Vercel AI SDK) — no direct provider API calls in product code. Applies to both profile generation and scheduling agent. | L | Confirm SDK supports multi-model routing (profile generation → Small tier, scheduling agent → Mid tier) without provider-specific code changes. |
| **Routing** | Partially applicable — two AI features with different complexity profiles now exist. Profile generation routes to Small-tier model; scheduling agent routes to Mid-tier model with Small-tier triage for simple actions (confirmations, reminders). | M | Define routing rules: which scheduling agent actions go to Small-tier vs. Mid-tier. Document the cascade ratio (estimated 80% Small / 20% Mid for scheduling agent actions). |
| **Eval** | Golden dataset v1 exists (10 cases, 4 adversarial) for profile generation. No eval process yet for scheduling agent outputs (message quality, action accuracy, conflict resolution). | H | Extend golden dataset to cover scheduling agent: define 5 test cases for agent actions (booking confirmation, cancellation, rescheduling conflict) with expected outputs and judge type. |

## Portability Score
Partial — abstraction layer planned from day one and golden dataset v1 exists for profile generation. Two gaps remain: routing rules for the scheduling agent's cascade strategy are not yet defined, and the eval harness does not yet cover scheduling agent outputs. Provider swap for profile generation is low-risk; scheduling agent swap carries higher risk until eval coverage is extended.

## If [primary vendor] doubles pricing tomorrow:
Switch profile generation to a cheaper Small-tier provider behind the abstraction layer — configuration change, not a rewrite. For the scheduling agent, evaluate whether the Mid-tier task can be partially absorbed by the Small-tier model for simple actions (reducing cost), with Mid-tier reserved only for complex reasoning tasks (conflict resolution, custom messages). Cascade ratio adjustment is a routing config change, not a code change.

## If [primary vendor] ships a competing product:
This is a strategic risk, not a technical one. The response isn't swapping providers — it's accelerating what WaveUp owns and the AI vendor doesn't: proprietary conversion data tied to real bookings, scheduling patterns from Premium instructor behavior, and the institutional trust layer (ID verification, satisfaction guarantee) that no AI vendor can replicate by shipping a competing feature. The abstraction layer ensures the underlying model is interchangeable; the data and trust infrastructure is not.
