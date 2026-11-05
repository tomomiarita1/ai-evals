# Module 5 · Eval Budget · Ascend IQ

**Quarterly budget cap:** $200,000
**Online eval spend:** $150,000 (2 of at most 3 online evals)

## Budget

| Failure | Trust metric | Risk | Level | Cost |
| --- | --- | :---: | :---: | ---: |
| Data Fabrication | Hallucination Rate | P0 | Online eval | $85,000 |
| Context Specificity | Robustness | P1 | Periodic audit | $7,000 |
| Overconfident Tone | UX Trust | P1 | Online eval | $65,000 |
| Data Bias | Fairness | P2 | Periodic audit | $5,500 |
| Slow Answers | Latency | P3 | Code-based check | $1,250 |

## Downgrades

### Periodic audit · Context Specificity (Robustness · P1)
- **Cheaper check:** Each week, review 50 answers and check if the answers cover the actual question. 
- **Why it’s enough:** Catches systematic misses, such as the agent routinely summarizing all reviews when asked for negative ones. It misses one-off misses between audits. We can live with that because the online fabrication eval still catches the worst case, wrong data, and a scope miss is usually visible to the client in the answer itself.

### Periodic audit · Data Bias (Fairness · P2)
- **Cheaper check:** Every two weeks, review 100 answers and check the source origination. Flag if APAC sources fall below 25% on APAC questions.
- **Why it’s enough:** Catches a steady skew toward US sources within one or two cycles. It misses single biased answers. Acceptable while most questions are about US markets. We move this to online when APAC passes 20% of questions.

### Code-based check · Slow Answers (Latency · P3)
- **Cheaper check:** On every release, run a fixed set of multi-step questions and block if p95 is over 10 seconds. In production, log response time on every answer and alert if p95 goes above 10 seconds
- **Why it’s enough:** Latency is objective, so a timer catches every slow answer. An LLM judge would cost more and catch nothing extra.

