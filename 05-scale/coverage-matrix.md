# Module 5 · Coverage Matrix · AI Voice Agent

## Coverage Row

| Product | Hallucination Rate | Fairness | Latency | UX Trust | Robustness |
|---|---|---|---|---|---|
| AI Voice Agent | ⚠️ Partial | ❌ Gap | ❌ Gap | ⚠️ Partial | ⚠️ Partial |

## What Runs Today

- An eval gate tests its answers to 300 billing questions before every release.
- A supervisor listens to 10 random calls a week for tone.
- A drift monitor alerts when callers start asking about things the agent wasn’t tested on.

## Accepted Gap

**Fairness.** We accept this gap because the agent only handles basic calls and any caller can reach a person. 

We’ll look again: We’ll look again if escalation or hang-up rates for any caller language or region run 5+ points above the overall rate, or at the next quarterly review.

## Critical Gap

We’ve identified latency as the most critical gap for the AI Voice Agent. Users expect timely answers. If responses are slow, they’ll hang up and call a person instead. To close it, we’ll add a drift monitor on response time per call turn, alerting when p95 goes above 2 seconds over a rolling hour. We’ll also add a latency threshold to the release eval gate, blocking release if p95 on the 300-question set goes above 2 seconds. When the alert fires, the on-call engineer is paged.

## After the Pressure Test

I changed the answers multiple times due to not following the intent of the lab initially. Corrected Latency to ❌ and Robustness and Hallucination to ⚠️. Rewrote the Fairness rationale (it was about tone) and replaced the complaint trigger with a measurable escalation-rate trigger. Moved the critical gap from Robustness to Latency and added a specific check, threshold and frequency.
