# Three-Horizon Roadmap & Board Pitch

## Roadmap

### Horizon 1 — Now (0-3 months)
*Quick wins. Ship with existing capabilities.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Launch AI Profile Generation Copilot (bundled, all instructors) — generate bio, headline, trust highlights, price and schedule suggestions based on instructor inputs and simulated Instagram analysis | Browse-to-booking conversion rate (target: 8% → 15%) | H |
| Activate Correction Loop — add explicit feedback field and manual edit capability to AI-generated profiles; capture all edits as training signal | Correction capture rate (% of generated profiles with instructor feedback or edits recorded) | H |
| Deploy Confidence UX — tiered profile display (single version >90%, two versions 70–90%, human review queue <70%) | HITL rate (target: <20% of generated profiles requiring human review) | H |
| Launch Golden Dataset v1 — 10 test cases (4 adversarial) with automated regression on every prompt/model change | Eval regression rate (target: 0 regressions ship undetected) | M |

### Horizon 2 — Next (3-9 months)
*Bets. Requires new capabilities or integrations.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Launch Premium Plan ($19/month) — reduced commission (8%) + Scheduling Agent with monthly action cap; target high-volume instructors (20+ classes/month) | Premium conversion rate among high-volume instructors; off-platform leakage rate (target: measurable reduction vs. baseline) | M |
| Build Preference Loop — capture student booking, abandonment, and rebooking behavior; surface personalized instructor recommendations on home screen | Student rebooking rate; browse-to-booking conversion for returning students | M |
| Expand Golden Dataset to 150 cases — cover all sport verticals (surf, skate, yoga, kitesurf, windsurf) and edge case categories identified in M4 | Hallucination rate (target: 0% fabricated credentials); drift velocity (target: <5% quality degradation month-over-month) | M |
| Close the AI output → student behavior silo — connect profile generation outputs to booking conversion data; begin measuring which AI-generated profile elements drive conversion | Confidence distribution (% high vs. low confidence outputs); inference ROI (revenue per $ of inference spend) | M |

### Horizon 3 — Bet (9-18 months)
*Moonshots. High uncertainty, high potential.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Cross-Domain Transfer — use conversion patterns from high-performing sport verticals to inform profile generation in adjacent sports; AI gets smarter across all sports simultaneously | Cross-sport conversion lift (% improvement in browse-to-booking for AI-guided profiles vs. manual profiles, per sport) | L |
| Network Intelligence — each new student review and booking improves matching recommendations for all users; platform gets smarter with every transaction | Network-driven conversion lift; time-to-first-booking for new instructors (target: reduce from 52 days baseline) | L |
| Scheduling Agent v2 — expand beyond action cap; add conflict resolution, dynamic pricing suggestions based on demand patterns, and proactive availability optimization | Premium instructor retention rate; scheduling agent HITL rate (target: <5% of agent actions requiring human intervention) | L |

---

## Board Pitch

**Thesis (1 sentence):**
WaveUp is building the trust infrastructure for peer-to-peer sport instruction in Europe — and AI is the mechanism that solves the cold-start problem keeping 61% of instructors from their first booking.

**The case:**

1. Why now:
The peer-to-peer instruction market in Europe is fragmented, with no dominant platform. Airbnb Experiences covers tourists but not local, recurring students. Instagram has the instructors but no transaction safety. The window to establish trust infrastructure before either platform moves is open now — and AI-generated, conversion-optimized profiles are the fastest path to closing it.

2. What's defensible:
The moat is not the AI model — it's the proprietary conversion data that accumulates with every booking, edit, and abandonment on the platform. As the correction and preference loops compound, WaveUp's profile generation gets smarter in ways no generic model or competitor without transaction history can replicate. The abstraction layer (Kill Switch, M2) ensures no single AI vendor dependency.

3. The economics:
Free plan: 15% commission, near-zero AI COGS ($0.009/user/month for profile generation). Premium plan: $19/month + 8% commission, designed to retain high-volume instructors with the highest off-platform leakage risk. Gross margin stays above 99% even under a 3x inference cost stress test. The scheduling agent (Premium Killer feature) adds ~$2–4/month in inference cost against $19 + commission revenue — margin remains healthy.

**The risks:**

1. Trust / failure modes:
AI hallucinates or publishes unverified credentials → student books based on false information → safety incident and legal liability (Air Canada precedent). Mitigation: golden dataset with 0% hallucination target, confidence UX with human review queue, and explicit autonomy boundaries (AI never publishes without instructor approval).

2. Scale / governance:
Scheduling agent makes autonomous actions (booking, cancellation) that the company is legally responsible for. Mitigation: strict autonomy boundaries (draft ≠ send, read ≠ write), weekly human audit cadence, GDPR and EU AI Act compliance baked in from day one, not retrofitted.

3. Competitive:
Airbnb Experiences could ship instructor booking in weeks (50% value at risk in tourist segment). Instagram could add a booking button and capture 70% of value long-term. Defense: institutional trust (ID verification, background checks, satisfaction guarantee) is what neither platform offers — and it is specifically what the safety-conscious student segment (women booking solo, beginners in physical activities) needs before booking a stranger.

**The ask:**
3 months · 1 engineer + 1 PM (existing team) · Focus: ship H1 initiatives, activate correction loop, reach 150-case golden dataset. Success metric: browse-to-booking conversion moves from 8% toward 15% within 90 days. Kill criteria: if conversion does not improve within 3 months of AI profile launch, pivot to demand-side intervention (student matching AI) before investing in H2.

---

## M1 Baseline vs. Now

**M1 baseline:**
WaveUp bets that enriching instructor profiles with verification badges, credentials, and trust signals will increase browse-to-booking conversion from 8% to 15% — because 68% of students bounce from profiles with only a name and photo.

**Now:**
WaveUp is building a compounding AI trust layer for peer-to-peer sport instruction across Europe. The profile generation copilot solves the cold-start problem at near-zero marginal cost; the scheduling agent retains high-volume instructors who would otherwise leak transactions off-platform; and the data flywheel — corrections, preferences, and booking outcomes — creates a proprietary moat that compounds with every transaction. The economics hold under 3x stress. The governance is designed to EU AI Act standards from day one. The kill criteria are explicit at every horizon.
