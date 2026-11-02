# Module 4 · Launch Strategy · Ascend IQ Copilot

## 4.0 Release Criteria

| Gate | Failure | Metric | Threshold | Dataset | Method | Runs at |
|---|---|---|---|---|---|---|
| Hard | Inaccrate data (#HALLUCINATION) | % answers that are matching the valid source data.  | 100% accuray, zero tolerance | Ascend IQ golden set | Code-based check | Pull Request |
| Soft | Row 14 · Relevance: the answer doesn’t answer the question | % answers that are not relevant to what was asked.  | 90% | Ascend IQ golden set | LLM judge | Staging |
| Advisory | Row 3 · Latency: exceeded the maximum response time | P95 latecy | 2s | Ascend IQ golden set | Code-based check | Staging |

## CI Gate Request for Engineering

- **Hard gate · Inaccrate data (#HALLUCINATION).** Check: the code-based check, run on the Ascend IQ golden set at Pull Request. Measures: % answers that are matching the valid source data. . Passes when: 100% accuray, zero tolerance. On a fail: block the merge.
- **Soft gate · Row 14 · Relevance: the answer doesn’t answer the question.** Check: the LLM judge, run on the Ascend IQ golden set at Staging. Measures: % answers that are not relevant to what was asked. . Passes when: 90%. On a fail: pause the release until the PM signs off on an override.
- **Advisory gate · Row 3 · Latency: exceeded the maximum response time.** Check: the code-based check, run on the Ascend IQ golden set at Staging. Measures: P95 latecy. Passes when: 2s. On a fail: post a warning, and don't block.

## Mitigation Plan · Soft Gate

If our Soft gate fails, I will release it with a beta label, allowing us to gather more datasets and identify other irrelevant answers for the golden set. 
