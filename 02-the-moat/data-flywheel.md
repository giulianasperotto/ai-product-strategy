Aqui está o M2 revisado com o scheduling agent incorporado:
markdown# Data Flywheel Map

> Score each loop 1-5. Your weakest loop is where competitors attack first.

## Flywheel Loops

| Loop | What It Measures | Score 1 | Score 5 | Score |
|------|------------------|---------|---------|-------|
| **Correction** | Do users fix AI outputs? Is that signal captured and reused? | No capture | Automated retraining | 3/5 |
| **Preference** | Does the product learn individual / team preferences over time? | Stateless | Deep personalization | 3/5 |
| **Domain Context** | Does usage in one area improve quality in adjacent areas? | Siloed | Cross-domain transfer | 2/5 |
| **Network** | Does each new user / team make the product better for everyone? | Isolated | Strong network effects | 3/5 |

### Correction Loop - 3/5
**What you capture today:** Not implemented yet. Planned: regenerate button (exists), explicit feedback field, and manual edit capability for profile generation — all feeding a future correction dataset. Scheduling agent adds a second correction signal: instructor overrides of agent-suggested actions (e.g. rejecting a proposed reschedule) reveal where agent judgment fails.
**How it compounds:** Profile edits and feedback improve prompt design and future AI outputs. Scheduling agent overrides improve action suggestion quality over time. No automated retraining yet — signal capture is the current priority.

### Preference Loop - 3/5
**What you capture today:** Not implemented yet. Planned: capture booking, rebooking, abandonment, and cancellation events per student (demand side). Scheduling agent adds supply-side preference data: which availability patterns, response times, and communication styles correlate with higher instructor booking rates and lower cancellations.
**How it compounds:** Student-side: system learns individual patterns (sport, time, instructor type) and personalizes discovery. Instructor-side: scheduling agent learns each instructor's operational preferences (preferred slots, cancellation tolerance, message tone) and improves suggestions over time. Neither loop is active yet.

### Domain Context Loop - 2/5
**What you capture today:** Not implemented. Hypothesis: conversion patterns from one sport (e.g. what makes a surf profile convert) could inform profile guidance for other sports (yoga, skate). Scheduling agent adds a second domain context hypothesis: peak booking times and cancellation patterns in one sport could inform availability recommendations in adjacent sports.
**How it compounds:** Weak — sports have different buyer psychology and trust signals, so cross-domain transfer is not guaranteed. Score remains 2/5; cross-sport learning is a H3 bet, not a foundational priority.

### Network Loop - 3/5
**What you capture today:** Reviews create a direct network effect — one student's review benefits all future students viewing that profile. Scheduling agent adds an indirect network effect: as more Premium instructors use the agent, WaveUp accumulates scheduling pattern data that improves availability recommendations for all instructors, not just Premium ones.
**How it compounds:** Direct effect via reviews is real but limited. Scheduling agent creates a new data accumulation path — the more transactions flow through the agent, the smarter its suggestions become for the whole supply side.

**Total Flywheel Score: 11/20**

**Weakest Loop:** Domain Context (2/5)

**Fix for weakest loop:** Focus on building strong conversion pattern recognition within each sport vertical first (surf, yoga, skate separately) before attempting cross-domain transfer. Cross-sport learning is a H3 bet, not a foundational one.

---

## Encroachment Threat Assessment

### 1. Platform Encroachment
**Attacker:** Airbnb Experiences
**Vector:** Already has both sides of the market — tourists and hosts/instructors — in WaveUp's strongest segment (tourism-driven discovery)
**Time-to-threat:** Weeks
**% of value at risk:** 50%

### 2. Vertical Competitor
**Attacker:** Urban Sports Club
**Vector:** Established local presence across European cities with resident instructor relationships and a recurring user base — the segment Airbnb doesn't reach
**Time-to-threat:** Months
**% of value at risk:** 30%

### 3. Adjacent Expansion
**Attacker:** Instagram
**Vector:** Every surf/yoga instructor already has an Instagram profile — a native booking button would capture discovery and social trust without requiring a new app. WhatsApp Business adds a second adjacent threat: automated messaging and scheduling flows for service providers directly replicate the scheduling agent's core functionality.
**Time-to-threat:** Long-term
**% of value at risk:** 70%

---

## 90-Day Encroachment Plan
*Your partner played the Big Tech attacker. What was their plan to kill you?*

**Attacker:** Instagram (Head of Product perspective)

**Attack vector (target the weakest loop):** Domain Context — WaveUp's cross-sport intelligence is unproven and easy to dismiss as a moat

**Weeks 1-4 - what they ship:**
A "Book a Class" button on instructor profiles, integrated with existing Instagram Shopping infrastructure. No identity verification required — relies on existing follower trust signals.

**Weeks 5-8 - how they poach users:**
Instructors already active on Instagram migrate bookings there to avoid WaveUp's commission and skip building a second profile from scratch. Promoted via Instagram's existing creator tools.

**Weeks 9-12 - why users don't come back:**
Students already follow these instructors on Instagram — no new app to download, no second trust decision to make. WaveUp's verification and satisfaction guarantee become invisible if students never leave Instagram to discover them.

**Your defense:**
Double down on what Instagram structurally cannot offer: institutional trust (ID verification, background checks) and financial protection (satisfaction guarantee, credit-back policy) for first-time bookings with strangers — specifically targeting the safety-conscious segment (e.g. women booking solo) where social proof alone isn't enough. The scheduling agent deepens this defense: Premium instructors embedded in WaveUp's operational workflow have a higher switching cost than those using Instagram booking alone.
