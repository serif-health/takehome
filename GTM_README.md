# GTM Engineer — Take-Home Assessment

**Time:** ~2–3 hours total
**Format:** Any (code + short written doc). Submit via email/repo link.

---

## Part 1: Outbound Campaign from Price Transparency Data

Here is a CSV of price transparency negotiated rate data for a single medical speciality (psychiatry) in a single insurance carrier network: [Download](https://mrf.serifhealth.com/public/mrf_rate_search_export.csv)

1. Using SQL or Python, explore this dataset and identify what you think
   is the single most compelling, sellable finding in it. Show your
   query/script and explain why you picked this finding over other
   things you could have highlighted.
2. Define the target: what type of data buyer would this specific finding resonate with, and why?
3. Write the actual outbound sequence — a templated cold email (subject + 3–5
   sentences) and a one-line LinkedIn follow-up — that references the
   specific data discovery you found. Generic value-prop copy won't score well.
4. In 3–4 sentences: how would you personalize this at scale across many
   employer segments, and where would automation or AI fit into doing
   that?
5. Name one or two metrics you'd track to know if the message is landing,
   and how you'd iterate.

**What we're evaluating:**

| Area | What good looks like |
|---|---|
| Data analysis | Query/script actually surfaces a real, specific pattern in *their* data |
| Judgment | The "why this finding" reasoning shows they weighed options, not just took the first thing they saw |
| Targeting logic | Persona choice is justified by the specific finding, not generic |
| Message quality | Copy references the actual number/insight, not boilerplate |
| Scale thinking | Concrete personalization approach + a real automation/AI angle |
| Iteration plan | Names a real metric and a real next step, not "monitor and adjust" |

---


## Part 2: AI Lead-Qualification Design Memo (written)

Serif gets inbound "Book a Demo" requests with a form response plus
enrichment data (company size, industry, role). Write a 1–2 page design
memo for an AI-assisted agent that qualifies and routes these leads.

Cover:

- What signals the agent uses and how it weighs them
- How it handles low-confidence or ambiguous cases (what happens instead
  of a wrong auto-route)
- How you'd evaluate the agent's decisions before launch and monitor it
  afterward
- Rollback/guardrails if it starts misrouting

**What we're evaluating:**

| Area | What good looks like |
|---|---|
| Qualification logic | Names concrete signals, not "the model decides" |
| Handling uncertainty | Has a human-in-the-loop path for ambiguous cases |
| Evaluation plan | Concrete method (labeled set, human baseline), not just "monitor it" |
| Judgment | Reasons about failure modes, not just the happy path |

*Bonus (not required): unprompted mention of data-privacy/compliance
considerations, given the healthcare-adjacent business.*

---

## Submission

Send both parts together. No need for production-grade polish — we're
evaluating reasoning and correctness, not how pretty the code is.