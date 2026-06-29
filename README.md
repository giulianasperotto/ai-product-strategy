# WaveUp AI Product Strategy
> A living strategy built across 6 sessions. Each module adds one component. By Module 6, this repo IS your strategy — version-controlled, board-ready, portable.

---

## Strategy at a Glance

| Component | Module | Status | Key Artifact |
|-----------|--------|--------|-------------|
| **The Bet** | M1 | [x] | `01-the-bet/` |
| **The Moat** | M2 | [x] | `02-the-moat/` |
| **The Margin** | M3 | [x] | `03-the-margin/` |
| **The Contract** | M4 | [x] | `04-the-contract/` |
| **The Guardrails** | M5 | [x] | `05-the-guardrails/` |
| **The Pitch** | M6 | [x] | `06-the-pitch/` |

---

## The Bet (M1)
**What we're building, for whom, why now.**

- **Product:** WaveUp — peer-to-peer marketplace connecting students with surf, skate, yoga, kitesurf, and windsurf instructors across Europe. Two AI features: Profile Generation Copilot (free, all instructors) and Scheduling Agent (Premium, $19/month + 8% commission).
- **AI Value Archetype:** Copilot (Profile Generation) + Orchestrator (Scheduling Agent)
- **Vulnerability Scores:** Moat 2/5 · Data 4/5 · Platform 1/5
- **Top Risk:** Students and instructors closing transactions off-platform, preventing the data flywheel from spinning before it gains momentum.
- **Confidence:** Medium
- **Prototype:** [waveupro.lovable.app](https://waveupro.lovable.app)
- **Kill Criteria:** If browse-to-booking conversion for AI-generated profiles does not increase from 8% toward 15% within 3 months, the profile enrichment hypothesis is invalidated. If Premium adoption among high-volume instructors does not reach 20% within 6 months, the retention hypothesis is invalidated.

→ Details: [`01-the-bet/`](01-the-bet/)

---

## The Moat (M2)
**Why this won't get copied in 6 months.**

- **Data Flywheel Score:** 11/20
- **Weakest Loop:** Domain Context (2/5) — cross-sport transfer is unproven; fix is to build strong conversion pattern recognition per sport vertical before attempting cross-domain transfer.
- **Competitive Position:** Strong on data accumulation (4/5), weak on switching cost (2/5), highly exposed to platform encroachment (1/5). Airbnb Experiences threatens tourist segment (50% value at risk, weeks away). Instagram threatens social trust layer (70% value at risk, long-term). Urban Sports Club threatens local recurring segment (30% value at risk, months away).
- **Encroachment Defense:** Institutional trust (ID verification, background checks, satisfaction guarantee) is what no attacker currently offers — specifically relevant for safety-conscious students booking physical activities with strangers. Premium scheduling agent increases switching cost for high-volume instructors.
- **Vendor Portability:** Partial

→ Details: [`02-the-moat/`](02-the-moat/)

---

## The Margin (M3)
**Will this make money or bleed it?**

- **Gross Margin (current):** 99.97% — profile generation AI COGS is $0.009/user/month against $32/month average commission revenue.
- **Gross Margin (AI-adjusted):** 99.7% under 3x stress test (both cost-per-request and volume tripling simultaneously). Premium plan margin remains healthy: $2–4/month scheduling agent COGS against $19 flat fee + 8% commission revenue.
- **Pricing Model:** Hybrid — 15% commission (Free plan, all instructors) + $19/month flat fee with 8% commission (Premium plan, high-volume instructors with scheduling agent access).
- **Cascading Strategy:** Small-tier model for profile generation (100% of volume). Mid-tier model for scheduling agent complex actions (estimated 20% of agent volume); Small-tier for simple agent actions (80%).
- **Break-even at:** Profile generation breaks even immediately (COGS negligible). Premium plan breaks even at first transaction — flat fee + reduced commission exceeds scheduling agent inference cost from month one.

→ Details: [`03-the-margin/`](03-the-margin/)

---

## The Contract (M4)
**Why users will trust a probabilistic system.**

- **Reliability Target:** 0% hallucination rate (no fabricated credentials), ≥90% golden dataset accuracy, ≤3s latency at p95, <5% quality drift month-over-month.
- **Golden Dataset:** 10 rows, 4 adversarial (prompt injection, extreme credential claim, offensive content, insufficient inputs). Target: 150 rows at v1 ship.
- **Confidence UX:** Tiered confidence + human-in-loop trigger. Single profile output at >90% confidence. Two profile options at 70–90%. Human review queue + instructor notification below 70%. AI reasoning visible at all confidence levels.
- **HITL Architecture:** Flags trigger on confidence <70%, extreme credential claims, prompt injection, offensive content, contradictory data, student complaints. Weekly human review cadence. Target: HITL rate from ~20% at launch to <5% within 6 months as correction loop compounds.
- **Failure Mode Coverage:** Hallucination (fabricated credentials), prompt injection, off-platform leakage signal, scheduling agent autonomy breach, model drift.

→ Details: [`04-the-contract/`](04-the-contract/)

---

## The Guardrails (M5)
**What breaks when this scales — and what compounds.**

- **Compounding System:** Three loops planned, none active yet (prototype stage). Correction loop (3/5): profile edits + scheduling agent overrides feed future training signal. Preference loop (3/5): student booking behavior personalizes discovery; agent learns instructor operational preferences. Network loop (3/5): reviews create direct network effect; scheduling agent accumulates supply-side pattern data. Critical silo: AI outputs not yet connected to student booking outcomes — closing this loop is the H1 priority.
- **Governance Posture:** Tiered autonomy. Profile copilot generates but never publishes without instructor approval. Scheduling agent sends pre-approved messages autonomously; booking, cancellation, and rescheduling require human initiation. Weekly human audit cadence.
- **Shadow AI Status:** 5 tools found, 3 build candidates (ChatGPT for bio writing → absorbed by profile copilot; Google Calendar → absorbed by scheduling agent; WhatsApp for booking communication → native messaging reduces leakage risk). 2 deprioritized (Instagram evaluation → deepen existing integration; Google Maps reviews → not strategic).
- **Agent Boundaries:** Profile copilot: generate, never publish. Scheduling agent: send pre-approved messages autonomously; all booking actions require human confirmation.
- **Regulatory Exposure:** GDPR (personal data across Europe) + EU AI Act Limited risk tier (transparency obligations — users informed of AI-generated content; no heavy audit requirements at current stage).

→ Details: [`05-the-guardrails/`](05-the-guardrails/)

---

## The Pitch (M6)
**How you get this funded, shipped, and adopted.**

- **Horizon 1 (Now — 0–3 months):** Ship AI Profile Generation Copilot (bundled, all instructors). Activate correction loop. Deploy confidence UX with HITL queue. Launch golden dataset v1 with automated regression.
- **Horizon 2 (Next — 3–9 months):** Launch Premium Plan ($19/month + 8% commission + scheduling agent). Build preference loop (student behavior personalization). Expand golden dataset to 150 cases. Close AI output → booking conversion data silo.
- **Horizon 3 (Bet — 9–18 months):** Cross-domain transfer (conversion patterns across sport verticals). Network intelligence (platform-wide matching improvements). Scheduling agent v2 (dynamic pricing, demand-based availability optimization).
- **Board Narrative:** WaveUp is building the trust infrastructure for peer-to-peer sport instruction in Europe — and AI is the mechanism that solves the cold-start problem keeping 61% of instructors from their first booking.
- **Key Metric:** Browse-to-booking conversion rate (baseline: 8%, target: 15% within 3 months of AI profile launch).

→ Details: [`06-the-pitch/`](06-the-pitch/)
