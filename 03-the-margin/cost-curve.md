# Cost Curve & Pricing Strategy

## Cost Model

| Cost Category | Per-User/Month | Notes |
|--------------|----------------|-------|
| Inference (primary model) | $0.009 | Profile generation only — Simple complexity, Small-tier model (e.g. Gemini Flash, Claude Haiku). 3 requests/month average. |
| Inference (cascading/triage) | N/A | Not applicable — single AI feature, no triage/frontier split yet |
| Infrastructure | Negligible | Lightweight feature, no dedicated infra beyond existing app backend |
| Data/storage | Negligible | Text-only outputs (bio, headline, highlights); no media storage for AI outputs |
| Human-in-the-loop | $0 | No human review step in current flow; regenerate/edit/feedback are self-serve |
| **Total AI COGS** | **$0.009** | |

## Cascading Strategy
<!-- Cheap model → frontier model routing logic -->
**Triage model:** Not applicable yet — WaveUp has a single AI feature (profile generation), classified as Simple complexity, fully served by a Small-tier model.

**Frontier model:** Not applicable yet — no task today requires frontier-level reasoning. Would become relevant if the scheduling agent (under consideration as a premium add-on) is built, since it likely requires more complex, multi-step reasoning.

**Routing rule:** N/A — revisit once a second, more complex AI feature exists.

**Expected cascade ratio:** N/A

## Pricing Model
**Current pricing:** None — prototype stage, no live transactions.

**Proposed AI pricing:** Hybrid model. All instructors pay commission on bookings; a premium subscription tier unlocks a reduced commission rate plus access to a scheduling agent (capped usage, overage billed separately).

- Free plan: 15% commission per booking, AI profile generation included, no scheduling agent
- Premium plan ($19/month flat fee): 8% commission per booking, AI profile generation included, scheduling agent included with monthly action cap

**Model:** hybrid (commission + flat subscription fee)

## Stress Tests

| Scenario | Impact on Margin | Response |
|----------|-----------------|----------|
| Inference costs 3x | Minimal — blended cost per user rises from $0.009 to $0.081/month. Revenue is commission-based, not AI-usage-based, so gross margin stays above 99%. | No action needed at current scale; monitor if AI feature set expands to heavier tasks (e.g. scheduling agent). |
| Heaviest segment doubles | If high-volume (Premium) instructors double, scheduling agent usage doubles — the only cost-sensitive feature. Commission revenue also doubles, offsetting most of the cost increase. | Enforce the monthly action cap on the scheduling agent and bill overage to protect margin on the heaviest users. |
| Model provider raises prices 50% | Profile generation cost rises from $0.009 to ~$0.0135/user/month — still negligible against $32–$150/month in commission revenue. | Switch providers behind the abstraction layer (see Kill Switch, Module 2) if the increase persists or extends to future features. |

## Board One-Pager
<!-- Before/After: Old SaaS revenue vs. AI usage revenue for your product -->
**Before (traditional SaaS):**
A flat-commission marketplace (15% per booking) with no AI differentiation. Revenue scales only with transaction volume; instructor profiles are static and manually filled, contributing to the 8% browse-to-booking conversion rate and 61% zero-review instructor rate identified in the Module 1 diagnostic.

**After (AI-enabled):**
AI profile generation is bundled into the base plan (Filler) to lift conversion at near-zero cost (<$0.01/user/month). A premium tier introduces a reduced commission rate (8%) plus a paid scheduling agent (Killer), creating a retention lever for high-volume instructors who have the strongest incentive to leak transactions off-platform.

**Net margin shift:**
Gross margin remains above 99% even under a pessimistic 3x stress test, because AI costs are immaterial relative to commission revenue. The real margin risk isn't inference cost — it's off-platform leakage, which the premium tier is designed to mitigate by making it cheaper to stay on WaveUp than to transact outside it.
