# Module 5 · Coverage Matrix · AI Voice Agent

## Coverage Row

| Product | Hallucination Rate | Fairness | Latency | UX Trust | Robustness |
|---|---|---|---|---|---|
| AI Voice Agent | ✅ Covered | ❌ Gap | ✅ Covered | ⚠️ Partial | ❌ Gap |

## What Runs Today

- An eval gate tests its answers to 300 billing questions before every release.
- A supervisor listens to 10 random calls a week for tone.
- A drift monitor alerts when callers start asking about things the agent wasn’t tested on.

## Accepted Gap

**Fairness.** We accept this gap because we indicates that this is an AI agent and our customer will give a bit more leeway on tone as long as the information is accurate. 

We’ll look again: We will look at it again if our customers report the tone issue in a significant volume. 

## Critical Gap

We’ve flagged Robustness as the most critical gap for AI Voice Agent because having the AI agent is to cover all the inquiries around billing questions. If it does not answer the questions, it defeats the purpose and less people will try using the application. 

## After the Pressure Test

I changed my answer for the lowest from UX trust to Fairness. The analysis with 04 prompt identified that UX Trust isn't low risk. 
