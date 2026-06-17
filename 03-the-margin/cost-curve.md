# Cost Curve & Pricing Strategy

## Cost Model

| Cost Category | Per-User/Month | Notes |
|--------------|----------------|-------|
| Inference (primary model) | $0.009 | Profile generation — Simple complexity, Small-tier model (e.g. Gemini Flash, Claude Haiku). 3 requests/month average, applies to all instructors. |
| Inference (cascading/triage) | $0 (Free) / ~$2–4 (Premium) | Scheduling agent — Medium/Complex task (multi-step: read calendar, draft message, confirm action), Mid-tier model. Only active for Premium instructors, capped usage per month. |
| Infrastructure | Negligible | Lightweight features, no dedicated infra beyond existing app backend |
| Data/storage | Negligible | Text-only AI outputs; no media storage for AI-generated content |
| Human-in-the-loop | $0 | No human review step in current flow; regenerate/edit/feedback are self-serve |
| **Total AI COGS** | **$0.009 (Free) / ~$2–4 (Premium)** | Blended cost depends on plan — Free instructors only use profile generation; Premium instructors add scheduling agent cost |

## Cascading Strategy
<!-- Cheap model → frontier model routing logic -->
**Triage model:** Small-tier model (e.g. Gemini Flash, Claude Haiku) — handles profile generation for all instructors, and simple scheduling agent actions (e.g. confirming a fixed time slot) for Premium instructors.

**Frontier/Mid model:** Mid-tier model — handles scheduling agent tasks requiring more context or judgment (e.g. drafting a personalized message to a student, handling a rescheduling conflict).

**Routing rule:** Profile generation always routes to the Small-tier model. Scheduling agent actions route to Small-tier for templated/simple actions; escalate to Mid-tier when the action requires reading conversation context or resolving a conflict.

**Expected cascade ratio:** ~80% Small-tier / 20% Mid-tier for scheduling agent actions — most actions (confirmations, reminders) are simple; a minority (conflict resolution, custom messages) need more reasoning.

## Pricing Model
**Current pricing:** None — prototype stage, no live transactions.

**Proposed AI pricing:** Hybrid model. All instructors pay commission on bookings; a premium subscription tier unlocks a reduced commission rate plus access to the scheduling agent (capped usage, overage billed separately).

- Free plan: 15% commission per booking, AI profile generation included, no scheduling agent
- Premium plan ($19/month flat fee): 8% commission per booking, AI profile generation included, scheduling agent included with monthly action cap

**Model:** hybrid (commission + flat subscription fee)

## Stress Tests

| Scenario | Impact on Margin | Response |
|----------|-----------------|----------|
| Inference costs 3x | Free plan: negligible, COGS rises from $0.009 to $0.081/month. Premium plan: more material, scheduling agent COGS could rise from ~$3 to ~$9/month — still well below the $19 flat fee plus commission revenue. | Monitor Premium plan margin closely since it carries the cascading cost; Free plan has no exposure to worry about. |
| Heaviest segment doubles | If Premium instructor count doubles, scheduling agent costs double in aggregate. Commission and subscription revenue also double, largely offsetting the cost increase. | Enforce the monthly action cap and bill overage on the scheduling agent to prevent the heaviest users from eroding Premium margin. |
| Model provider raises prices 50% | Free plan: cost rises from $0.009 to ~$0.0135/month, immaterial. Premium plan: scheduling agent cost could rise from ~$3 to ~$4.50/month, still small relative to $19 + commission revenue. | Switch providers behind the abstraction layer (see Kill Switch, Module 2) if the increase persists. |

## Board One-Pager
<!-- Before/After: Old SaaS revenue vs. AI usage revenue for your product -->
**Before (traditional SaaS):**
A flat-commission marketplace (15% per booking) with no AI differentiation. Revenue scales only with transaction volume; instructor profiles are static and manually filled, contributing to the 8% browse-to-booking conversion rate and 61% zero-review instructor rate identified in the Module 1 diagnostic.

**After (AI-enabled):**
Two AI features now shape the business: profile generation (Filler), bundled free for all instructors to lift conversion at near-zero cost; and a scheduling agent (Killer), sold as a Premium add-on with a reduced commission rate, creating a retention lever for high-volume instructors who have the strongest incentive to leak transactions off-platform.

**Net margin shift:**
Free plan margin remains above 99% even under stress, since profile generation cost is immaterial. Premium plan margin is more sensitive to inference cost because the scheduling agent is a heavier, multi-step task — but it remains healthy because the $19 flat fee and commission revenue comfortably cover even a 3x cost increase. The real margin risk isn't inference cost on either plan — it's off-platform leakage, which the Premium tier is designed to mitigate.
