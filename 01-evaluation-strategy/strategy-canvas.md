# AI Evaluation Strategy Canvas

> Repo file `ai-evals/01-evaluation-strategy/strategy-canvas.md` (the repo is your submission).

## 1. Product Strategy, The Context

**Who it's for:** VP-level strategists and product leaders at Fortune 500 companies who pay upward of $50,000 a year for verified market intelligence.

**What they use it for:** Asking plain-language questions, like “Compare the pricing models of Stripe and Adyen,” and getting answers in seconds instead of digging through the platform.

**What's at stake:** Engagement is dropping, Q4 retention is at risk, and the CPO wants Ascend IQ live for the top 50 enterprise accounts next month. One poor answer to the wrong client can do lasting damage to the relationship.

## 2. Measurements, The Execution

**User promise.** For VP-level strategists and product leaders at our top enterprise accounts, Ascend IQ promises to answer plain-language market questions in under 30 seconds with every claim cited to Ascend’s verified data, and to say “not enough evidence” rather than guess, so that they can put Ascend insights straight into roadmap decisions without re-checking, which restores daily engagement and protects Q4 renewals.

**Top 3 trust metrics:**
- **Latency**, Response speed (P95 / P99). Slow kills engagement.
- **Hallucination Rate**, % of outputs that are confidently false or fabricated.
- **Robustness**, Coherence on messy, adversarial, out-of-scope inputs.

**Why these three:** - Latency: Enforces the “under 30 seconds” commitment, keeping Ascend IQ faster than the manual research VPs would otherwise do, which is what drives daily engagement.

- Hallucination Rate: Measures whether every claim is cited to verified data and whether the system says “not enough evidence” instead of guessing, the core accuracy guarantee behind using insights without re-checking.

- Robustness: Ensures consistent, accurate answers across varied phrasings and thin-data questions, including saying “not enough evidence” instead of guessing, so trust holds under real-world use.

## 3. Strategic Trade-Offs, The Cost

### Trade-off 1 · Latency ↔ Robustness
We prioritize Robustness over Latency because inaccurate output erodes customer trust, and that trust is what lets leaders act on Ascend insights without re-checking.

### Trade-off 2 · Hallucination Rate ↔ Latency
We prioritize Hallucination over Latency because inaccurate output erodes customer trust, and that trust is what lets leaders act on Ascend insights without re-checking.

---
_Generated from the AI Evaluation Strategy Canvas, M1 lab tool, AI Evals Certification._
