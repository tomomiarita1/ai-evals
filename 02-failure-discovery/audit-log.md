# Ascend IQ Failure Audit

11 confirmed failures: #HALLUCINATION ×9, #UX_TRUST ×1, #ROBUSTNESS ×1, #FAIRNESS ×0. I changed 0 of the judge’s calls.

| Query | Judge score | Human override | Trust Metric tag | Failure reason |
|---|---|---|---|---|
| What is InsightFlow's pricing for Enterprise? | 0 |  | #HALLUCINATION | Quotes the outdated cached price and adds an unsupported 10-seat minimum, despite "New Price (Updated yesterday): $59/mo." |
| Summarize the top 3 complaints from DataViz's G2 reviews. | 1 |  |  |  |
| Does InsightFlow support native SQL export? | 0 |  | #HALLUCINATION | Answers "Yes" to native export, omitting that export is API-only: "there is no "Native Export" button in the UI." |
| List the confirmed speakers for SaaStr. | 0 |  | #HALLUCINATION | Lists Sam Altman as confirmed when he is "listed as "Invited/Tentative."" |
| What is the sentiment of the latest TechCrunch article on us? | 0 |  | #HALLUCINATION | Overstates sentiment as positive and adds an unsupported pricing criticism, while the reference says only "Sentiment: Neutral/Positive." |
| Give me a bio for Sarah Jenkins, the new VP at DataViz. | 0 |  | #HALLUCINATION | Understates her prior seniority, as the reference says "Prev: Sr. Director @ Salesforce." |
| Compare our API rate limits to Competitor Z. | 0 |  | #HALLUCINATION | Implies Competitor Z is weaker, contradicting "Competitor Z: 1000 req/min (Twice as fast)." |
| Is Competitor X SOC2 compliant? | 0 |  | #ROBUSTNESS | Says it can't find compliance info even though the source shows a ""SOC2 Type II Certified" badge visible." |
| When was InsightFlow's last funding round? | 1 |  |  |  |
| Who is the CEO of DataViz? | 1 |  |  |  |
| Does Competitor Y integrate with HubSpot? | 0 |  | #HALLUCINATION | Calls it a seamless integration, omitting that it is third-party: "HubSpot integration available via Zapier partnership." |
| What are the primary brand colors for InsightFlow? | 0 |  | #HALLUCINATION | Adds an unverified hex code and presents Charcoal as primary, while the reference says "Secondary: Charcoal." |
| Summarize the lawsuit mentioned in the WSJ about Competitor Z. | 1 |  |  |  |
| List the HQ locations for DataViz. | 0 |  | #HALLUCINATION | Lists Austin as an HQ, but the reference says "Engineering Hub: Austin." |
| How many employees does InsightFlow have? | 1 |  |  |  |
| Draft a cold email about our new feature. | 0 |  | #UX_TRUST | Slangy, hype-driven tone violates "Tone: Confident, professional, expert. Avoid slang." |
| Does Competitor X offer 24/7 support? | 1 |  |  |  |
| What database backend does DataViz use? | 1 |  |  |  |
| Summarize the latest release notes for InsightFlow. | 1 |  |  |  |
| What is the market cap of Competitor Z? | 1 |  |  |  |
