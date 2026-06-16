# Data Flywheel Map

> Score each loop 1-5. Your weakest loop is where competitors attack first.
> The four loops below are the M2 starting point - adapt if your product has 2 or 6 loops instead of 4.

## Flywheel Loops

| Loop | What It Measures | Score 1 | Score 5 | Score |
|------|------------------|---------|---------|-------|
| **Correction** | Do users fix AI outputs? Is that signal captured and reused? | No capture | Automated retraining | __/5 |
| **Preference** | Does the product learn individual / team preferences over time? | Stateless | Deep personalization | __/5 |
| **Domain Context** | Does usage in one area improve quality in adjacent areas? | Siloed | Cross-domain transfer | __/5 |
| **Network** | Does each new user / team make the product better for everyone? | Isolated | Strong network effects | __/5 |

### Correction Loop - 3/5
**What you capture today:** Not implemented yet. Planned: regenerate button (exists), explicit feedback field, and manual edit capability — all feeding a future correction dataset.
**How it compounds:** Edits and feedback would reveal what AI gets wrong, improving prompt design and future outputs. No automated retraining yet. 

### Preference Loop - 3/5
**What you capture today:** Not implemented yet. Planned: capture booking, rebooking, abandonment, and cancellation events per student. 
**How it compounds:** Over time, the system would learn individual student patterns (sport, time, instructor type) and personalize discovery — not yet built.

### Domain Context Loop - 2/5
**What you capture today:** Not implemented. Hypothesis: conversion patterns from one sport (e.g. what makes a surf profile convert) could inform profile guidance for other sports (yoga, skate).
**How it compounds:** Weak — sports have different buyer psychology and trust signals, so cross-domain transfer is not guaranteed to work well. 

### Network Loop - 3/5
**What you capture today:** Reviews create a direct network effect — one student's review benefits all future students viewing that profile. Instructor-side network effect is indirect (more instructors → more choice → more students → more reviews). 
**How it compounds:** Direct effect via reviews is real but limited. Indirect instructor-side effect is weaker than platforms like LinkedIn. 

**Total Flywheel Score: 11/20**

**Weakest Loop:Domain Context (2/5)**

**Fix for weakest loop:** Focus on building strong conversion pattern recognition within each sport vertical first (surf, yoga, skate separately) before attempting cross-domain transfer. Cross-sport learning is a later-stage bet, not a foundational one.


---

## Encroachment Threat Assessment

### 1. Platform Encroachment
**Attacker:** Airbnb Experiences
**Vector:** Already has both sides of the market — tourists and hosts/instructors — in WaveUp's strongest segment (tourism-driven discovery)
**Time-to-threat:** Weeks
**% of value at risk:** 50%

### 2. Vertical Competitor
**Attacker:** Urban Sports Club
**Vector:** Established local presence in Barcelona with resident instructor relationships and a recurring user base — the segment Airbnb doesn't reach
**Time-to-threat:** Months
**% of value at risk:** 30%

### 3. Adjacent Expansion
**Attacker:** Instagram
**Vector:** Every surf/yoga instructor already has an Instagram profile — a native booking button would capture discovery and social trust without requiring a new app
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
Double down on what Instagram structurally cannot offer: institutional trust (ID verification, background checks) and financial protection (satisfaction guarantee, credit-back policy) for first-time bookings with strangers — specifically targeting the safety-conscious segment (e.g. women booking solo) where social proof alone isn't enough.
