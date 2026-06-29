# Three-Axis Vulnerability Diagnostic

## Product
**Product:** WaveUp — peer-to-peer marketplace connecting students with surf, skate, yoga, kitesurf, and windsurf instructors across Europe. Two AI features: Profile Generation Copilot (all instructors, free) and Scheduling Agent (Premium instructors, $19/month + reduced 8% commission).
**Your Role:** Product Manager

---

## Scores

### Contextual Moat — 2/5
*Workflow depth × switching cost. Would users leave in a weekend if a competitor showed up?*

**Score rationale:**
Strong at discovery, weak at retention for casual users. However, the Premium Scheduling Agent increases switching cost for high-volume instructors — moving calendar management, automated messaging, and booking flow to a competitor requires rebuilding an operational workflow, not just a profile. Moat score remains 2/5 at current stage because the scheduling agent is not yet built; this score should be revisited at H2 launch if Premium retention data confirms higher switching cost.

**Named attacker (from partner challenge):**
Airbnb Experiences

---

### Data Advantage — 4/5
*Proprietary signal that compounds with usage. What do you see that OpenAI doesn't?*

**Score rationale:**
Niche transactional data that compounds over time — conversion patterns, instructor profile attributes that drive bookings, post-class feedback, and scheduling behavior (cancellations, remarcations, no-shows). The scheduling agent adds a new data layer: which availability patterns correlate with higher booking rates, and which instructor response behaviors reduce cancellations. Not available at this specificity anywhere else.

**Named attacker (from partner challenge):**
ClassPass

---

### Platform Exposure — 1/5
*Encroachment risk × pivot speed. If Apple/Google/OpenAI ships your hero feature native — then what?*

**Score rationale:**
High encroachment risk on two fronts. Airbnb Experiences threatens the discovery wedge for tourists. Instagram threatens the social trust layer. The scheduling agent adds a third exposure vector: Google Calendar or WhatsApp Business could add AI-powered booking and messaging flows for service providers, directly replicating the Premium feature at zero marginal cost to the attacker.

**Named attacker (from partner challenge):**
Instagram

---

## Top Vulnerability
Students and instructors closing transactions off-platform, preventing the data flywheel from spinning before it gains momentum. The scheduling agent mitigates this risk for Premium instructors by making it cheaper and easier to stay on WaveUp than to transact outside it — but this defense only works if Premium adoption reaches critical mass before a platform attacker moves.
