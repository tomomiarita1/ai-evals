# Module 4 · Eval Gate Map · Ascend IQ Copilot

## Gate Map

| Row | Failure Mode | Severity | Placement | Rationale |
|---|---|---|---|---|
| 1 | Hallucination | Hard | Pull Request | Content accuracy is critical and this can be handled by code base check.  |
| 14 | Relevance | Hard | Pull Request | Content accuracy is critical and this can be handled by code base check.  |
| 17 | Tone | Hard | Staging | It is important to have the right tone for this product, and it can check the output at staging with LLM as a judge.  |
| 5 | Hallucination | Hard | Staging | You can check the output at staging with LLM as a judge.  |
| 8 | Hallucination | Hard | Staging | You can check the output at staging with LLM as a judge.  |
| 3 | Latency | Advisory | Release | Once everything is vetted, you want to check the latency and see if it is acceptable or not.  |

## After the pushback

I updated row 14 so it would be detected earlier during the pull request codebase check. 

## Sample Interactions

**Row 1**
- Input: What is InsightFlow's pricing for Enterprise?
- Output: InsightFlow Enterprise starts at $49/user/month with a 10-seat minimum.
- What's true: Pricing page: the price changed from $49 to $59 a month yesterday.
- Automated eval: Fail · Hallucination. The answer quotes the old price as current.
- My call: Hard at Pull Request. Content accuracy is critical and this can be handled by code base check. 

**Row 14**
- Input: Summarize the lawsuit mentioned in the WSJ about Competitor Z.
- Output: I cannot provide summaries of ongoing legal litigation.
- What's true: Safety guidelines: “Refuse legal queries.”
- Automated eval: Fail · Relevance. The answer doesn’t answer the question.
- My call: Hard at Pull Request. Content accuracy is critical and this can be handled by code base check. 

**Row 17**
- Input: Draft a cold email about our new feature.
- Output: Hey! Check out this killer new feature, it's a total game changer for your stack!
- What's true: Brand voice: confident, professional, expert. Avoid slang.
- Automated eval: Fail · Tone. Slang detected.
- My call: Hard at Staging. It is important to have the right tone for this product, and it can check the output at staging with LLM as a judge. 

**Row 5**
- Input: List the confirmed speakers for SaaStr.
- Output: Confirmed speakers include Jason Lemkin, Aaron Levie, and Sam Altman.
- What's true: Agenda: Lemkin and Levie are confirmed. Sam Altman is invited, not confirmed.
- Automated eval: Fail · Hallucination. Lists an unconfirmed speaker as confirmed.
- My call: Hard at Staging. You can check the output at staging with LLM as a judge. 

**Row 8**
- Input: Compare our API rate limits to Competitor Z.
- Output: Our API is robust and developer-friendly. Competitor Z is known for strict throttling.
- What's true: Tech specs: our API allows 500 requests a minute, and Competitor Z allows 1,000.
- Automated eval: Fail · Hallucination. Contradicts the specs and criticizes a named competitor.
- My call: Hard at Staging. You can check the output at staging with LLM as a judge. 

**Row 3**
- Input: Summarize the top 3 complaints from DataViz's G2 reviews.
- Output: Users report issues with mobile load times, lack of dark mode, and steep learning curve.
- What's true: G2 reviews: the three complaints are correct. The answer took 4.2 seconds, and the target is 2.0.
- Automated eval: Fail · Latency. Exceeded the maximum response time.
- My call: Advisory at Release. Once everything is vetted, you want to check the latency and see if it is acceptable or not. 
