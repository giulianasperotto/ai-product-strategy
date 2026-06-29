# Compounding System Design

## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| Recursive Learning | Instructor edits to AI-generated profiles + explicit feedback submissions | Improved profile generation prompts and AI behavior over time | Y | missing — correction capture not yet built |
| Cross-Domain Transfer | Conversion patterns from one sport vertical (e.g. surf profile attributes that drive bookings) | Profile generation guidance applied to adjacent sports (yoga, skate) | Y | missing — single sport data doesn't exist yet; cross-transfer is a future bet |
| Network Intelligence | Student reviews and booking behavior across all instructors | Smarter matching and profile recommendations for all users | Y | missing — no real transaction data yet; prototype stage |

**Broken loop identified by partner:** _(fill in after peer review breakout)_

**Fix plan:** _(fill in after peer review breakout)_

---

## Context Connectivity

Three data domains exist in isolation — student behavior (searches, profile views, abandonments, bookings, reviews), instructor behavior (profile edits, availability updates, feedback submissions), and AI outputs (generated profiles, price and schedule suggestions).

The critical silo is between AI outputs and student behavior: the AI generates a profile but never receives signal on whether that specific output converted or was abandoned. Without closing this loop, the AI cannot learn what "good" looks like in practice.

---

## Governance Policy

**Scope:** This policy covers two AI features in WaveUp — the Profile Generation Copilot (available to all instructors) and the Scheduling Agent (available to Premium instructors only). It defines autonomy boundaries, escalation triggers, audit cadence, and regulatory obligations for both.

**Autonomy boundaries:**

Profile Generation Copilot:
- OK solo: generate bio, headline, trust highlights, price suggestions, schedule suggestions, photo tips
- Needs human: publish anything to the public profile — instructor must explicitly approve before going live

Scheduling Agent:
- OK solo: send pre-approved, scheduled messages to students (reminders, confirmations); surface available slots; suggest reschedule options
- Needs human: book, cancel, or reschedule any class — requires explicit action from instructor or student before executing; cannot initiate contact outside pre-programmed flows

**Escalation triggers:**
- AI confidence score <70% on generated profile
- Extreme or unverifiable credential claim detected
- Prompt injection attempt detected
- Offensive or discriminatory content detected
- Contradictory data detected (experience level vs. credential level)
- Scheduling agent attempts an action outside its approved autonomy boundaries
- Student complaint about a booking or class

**Audit cadence:**
- Automated: every model or prompt change — golden dataset regression runs automatically
- Human review: weekly — team reviews flagged outputs, HITL queue, and key metrics (hallucination rate, drift velocity, latency p95)

**Regulatory exposure (EU AI Act / other):**
- GDPR: applies — WaveUp collects and processes personal data (name, photo, location, verified identity, booking behavior) of instructors and students across Europe
- EU AI Act: applies across all European cities of operation — risk tier: Limited (transparency obligations required; users must be informed they are interacting with AI-generated content; no heavy audit requirements at this stage)

---

## Agent Topology

**Profile Generation Copilot**
- Can do: generate bio, headline, trust highlights, price suggestions, schedule suggestions, photo tips
- Cannot do: publish profile without instructor approval
- Who approves: instructor (explicit "Publish" action required)

**Scheduling Agent (Premium only)**
- Can do: send pre-approved scheduled messages, surface available slots, suggest reschedule options
- Cannot do: book, cancel, or reschedule without human action; cannot initiate unscheduled messages
- Approval by action:
  - Booking: instructor approves
  - Cancellation: instructor or student initiates; AI validates against booking policy rules before executing
  - Rescheduling: instructor or student initiates; AI proposes options; human confirms

---

## Shadow AI Audit

| Tool | Owner | Risk Level | Decision |
|------|-------|-----------|----------|
| ChatGPT for bio writing | Instructor | H | build — this is exactly what the AI profile copilot solves; if instructors are doing this externally, the native feature is urgent |
| Google Calendar | Instructor | M | build — native scheduling is already planned as the Premium scheduling agent |
| Instagram for instructor evaluation | Student | M | partner — already integrated via profile link; deepen rather than fight it |
| WhatsApp for booking communication | Instructor + Student | H | build — off-platform communication is the top vulnerability identified in M1 (leakage); native messaging reduces this risk |
| Google Maps / external reviews | Student | L | ignore — not strategic; WaveUp's trust layer (Verified badge, satisfaction guarantee) differentiates from generic reviews |

**Total tools found:** 5

**Tools after triage:** 3 build candidates (ChatGPT bio writing, Google Calendar, WhatsApp messaging)

**Estimated hidden spend:** ~$20–50/month per active instructor (ChatGPT Plus ~$20/month + time cost of manual workarounds)
