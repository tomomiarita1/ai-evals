# Eval Spec · Inaccrate data (#HALLUCINATION), an output risk

| Part            | Spec                                                                                                               |
| --------------- | ------------------------------------------------------------------------------------------------------------------ |
| Target risk     | Inaccrate data (#HALLUCINATION), an output risk                                                                    |
| Evaluator       | The rule check from Lab 1                                                                                          |
| Threshold       | 100% accuray, zero tolerance. The rule check caught 8 of 8, the safety rule caught 0 of 1, the judge caught 8 of 8 |
| Business stakes | The cost of failure, such as churn, a lawsite or damange to teh brand                                              |
| Owner           | PM                                                                                                                 |

## Messages

**Engineering · acceptance criteria:** Pass an answer only when every factual claim aligns with the verified source; fail it if any claim contradicts the source or includes unsupported information. The check must achieve 100% accuracy with zero tolerance for factual errors.

**Design · what the user sees:** When the check blocks an answer, show a clear message that the answer could not be provided because it contains information that does not match the verified source. Do not display the unsupported claim as a confirmed fact.

**Leadership · risk and return:** This check reduces the risk of inaccurate information reaching VP-level clients, preventing potential churn, legal issues, and brand damage. The rule check caught 8 of 8 failures and the judge caught 8 of 8, supporting the investment in a zero-tolerance accuracy standard.

Make the pass/fail rule fully testableKeep the evaluator scope consistent
