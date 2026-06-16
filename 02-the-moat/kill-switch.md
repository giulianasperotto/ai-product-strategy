# Kill Switch Audit

## Vendor Dependency Assessment

| Dimension | Current State | Risk Level | 48-Hour Action |
|-----------|--------------|------------|---------------|
| **Provider** | Undecided — evaluating Gemini Flash, Claude Sonnet, and GPT-5.4 mini based on cost per generation and quality for short creative text | M | Select one provider for MVP based on cost-per-generation benchmarks |
| **Abstraction** | Architectural decision made: use an abstraction layer (e.g. Vercel AI SDK) — no direct provider API calls in product code | L | Confirm SDK choice and structure code so provider swap doesn't require rewriting logic |
| **Routing** | Not implemented — not needed yet with a single AI task (profile generation) | L | No action needed now; revisit once multiple AI tasks exist (e.g. matching, moderation) |
| **Eval** | No quality evaluation process exists | H | Define 5-10 fixed test inputs and a minimum acceptable quality bar for generated profiles |

## Portability Score
<!-- Ready / Partial / Locked -->
Partial — strong architectural decision (abstraction layer planned from day one), but missing the most critical piece, an eval harness, to swap providers with confidence.

## If [primary vendor] doubles pricing tomorrow:
<!-- What's your 48-hour response? -->
Switch to a cheaper provider behind the abstraction layer. Because no direct API calls exist in the code, this is a configuration change, not a rewrite.

## If [primary vendor] ships a competing product:
<!-- What's defensible that they can't replicate? -->
This is a strategic risk, not a technical one. The response isn't swapping providers — it's accelerating what WaveUp owns and the AI vendor doesn't: proprietary conversion data tied to real bookings on the platform. That data, not the AI generation itself, is the actual moat.
