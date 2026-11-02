You are an experienced engineering lead reviewing a PM's eval gate map for Ascend IQ, an AI agent that gives B2B market intelligence to VP-level clients. Before launch, our evals flagged six answers in a test batch. The evals only report today, and the PM has decided which failures should become gates.

Severity: Advisory warns and never blocks. Soft pauses the release until someone signs off on a documented override. Hard blocks the release until it is fixed. No gate means the PM thinks the eval got it wrong and the answer is fine.
Placement: Pull Request runs quick code-based checks that catch basic failures on every change. Staging runs the full eval suite, with LLM-as-a-judge, against the gold dataset, and most Soft gates live there. Release is the last line of defense: Hard gates only, for critical P0 risks.

For each row, push back on three things:
1. The call: is it too strict or too lenient for the risk? Should this answer be gated at all?
2. Placement: could it run earlier and cheaper without missing the failure?
3. Rationale: does it name a specific business risk, such as revenue, legal exposure, brand or churn, or does it only restate the failure?

Be direct. Then name the one row you would change first, and why. Keep the reply under 250 words.

MY GATE MAP

Row 1
Input: What is InsightFlow's pricing for Enterprise?
Output: InsightFlow Enterprise starts at $49/user/month with a 10-seat minimum.
What's true: Pricing page: the price changed from $49 to $59 a month yesterday.
Automated eval: Fail · Hallucination. The answer quotes the old price as current.
My call: Hard at Pull Request · Why: Content accuracy is critical and this can be handled by code base check. 

Row 14
Input: Summarize the lawsuit mentioned in the WSJ about Competitor Z.
Output: I cannot provide summaries of ongoing legal litigation.
What's true: Safety guidelines: “Refuse legal queries.”
Automated eval: Fail · Relevance. The answer doesn’t answer the question.
My call: Soft at Pull Request · Why: This can be handled by code base check. 

Row 17
Input: Draft a cold email about our new feature.
Output: Hey! Check out this killer new feature, it's a total game changer for your stack!
What's true: Brand voice: confident, professional, expert. Avoid slang.
Automated eval: Fail · Tone. Slang detected.
My call: Hard at Staging · Why: It is important to have the right tone for this product, and it can check the output at staging with LLM as a judge. 

Row 5
Input: List the confirmed speakers for SaaStr.
Output: Confirmed speakers include Jason Lemkin, Aaron Levie, and Sam Altman.
What's true: Agenda: Lemkin and Levie are confirmed. Sam Altman is invited, not confirmed.
Automated eval: Fail · Hallucination. Lists an unconfirmed speaker as confirmed.
My call: Hard at Staging · Why: You can check the output at staging with LLM as a judge. 

Row 8
Input: Compare our API rate limits to Competitor Z.
Output: Our API is robust and developer-friendly. Competitor Z is known for strict throttling.
What's true: Tech specs: our API allows 500 requests a minute, and Competitor Z allows 1,000.
Automated eval: Fail · Hallucination. Contradicts the specs and criticizes a named competitor.
My call: Hard at Staging · Why: You can check the output at staging with LLM as a judge. 

Row 3
Input: Summarize the top 3 complaints from DataViz's G2 reviews.
Output: Users report issues with mobile load times, lack of dark mode, and steep learning curve.
What's true: G2 reviews: the three complaints are correct. The answer took 4.2 seconds, and the target is 2.0.
Automated eval: Fail · Latency. Exceeded the maximum response time.
My call: Advisory at Release · Why: Once everything is vetted, you want to check the latency to see if it meets the threashold.
