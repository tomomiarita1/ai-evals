# Eval Spec · Inaccrate data (#HALLUCINATION), an output risk

| Part | Spec |
|---|---|
| Target risk | Inaccrate data (#HALLUCINATION), an output risk |
| Evaluator | The rule check from Lab 1 |
| Threshold | 0; the rule check caught 8 of 8, the safety rule caught 0 of 1, the judge caught 8 of 8 |
| Business stakes | The cost of failure, such as churn, a lawsite or damange to teh brand |
| Owner | PM |

## Messages

**Engineering · acceptance criteria:** Pass an answer with a score of 1 only when all facts align with the sources; fail it with a score of 0 when any fact does not align with the sources. Block answers scoring 0, using threshold 0.

**Design · what the user sees:** When the check blocks an answer, show a clear message that the answer could not be verified against the sources and should not be shared as fact. Do not display the blocked answer as a verified result.

**Leadership · risk and return:** This check reduces the risk of inaccurate claims reaching VP-level clients and causing churn, a lawsite or damange to teh brand. It is worth the cost because the rule check caught 8 of 8 target failures, while the safety rule caught 0 of 1 and the judge caught 8 of 8.
