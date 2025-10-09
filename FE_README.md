# Frontend Engineer Take‑Home Assignment

## Price Transparency Data Table + Visualization

**Time budget**: ~2–3 hours  
**Role**: Frontend Engineer  
**Skills evaluated**: API integration / data fetching, data transformation, UI design (table + chart), responsiveness, code structure, choice of libraries, documentation & ease-of-use.  



## Overview

For this exercise, you will build a small frontend app (could be plain JS/TS, React, Vue, Svelte, etc.) that:

1. Fetches rate data from the given API endpoint  
2. Renders a table of the returned data  
3. Provides one or more meaningful visualizations (chart, summary, etc.) that help a user explore insights in the price transparency data  

We leave the visualization aspect somewhat open‑ended: the focus is on how you think about representing and exploring data, your technical choices, and the polish of your implementation. What kinds of 'insights' are identifiable from the resulting data frame? What would a typical consumer of price transparency data want to see? 

### API to Use

You should fetch data from:  
```
https://neuron.serifhealth.com/api/rates/v1?network_template_ids=07c56f6b-82cd-44a4-af42-d570b6ae89c6&limit=1000&codes=99203
```

An API key will be sent to you separately; you should send it in an X-API-KEY header to pass authentication with the API. If the key expires, errors, or goes over quota, contact engineering@serifhealth.com for an updated API key. If you hit a rate limit, please make sure you're appropriately spacing out API call timing client-side.

The endpoint returns JSON data representing Aetna of California price transparency / rate records for CPT code `99203`. Use that data as your input.

You may mock the API response for local development if needed, but your final solution should fetch real data (as long as the endpoint is accessible).



## Requirements

Your submission should satisfy the following:

### Functional Requirements

1. **API Fetch**  
   - Fetch the JSON data from the API above on load.

2. **Tabular View**  
   - Display the returned records in a table.  
   - Include relevant columns (e.g. provider, rate, payer, geography, etc. — depending on what the data contains).  

3. **Visualization / Chart**  
   - Provide at least one visualization (chart, plot, etc.) that helps a user understand the distribution, trends, or patterns in the data.  


## Deliverables

1. A git repo (GitHub, GitLab, etc.) containing your code
2. A `README.md` with:
   - Instructions to install & run  
   - Description of your approach, assumptions, decisions, as well as what you would do if you had more time.
3. Once you have completed the assignment, share the link to your repository with us for evaluation, by email us at [engineering@serifhealth.com](mailto:engineering@serifhealth.com)


## Expectations
- **Programming Language & Libraries**: You can use any appropriate language, libraries, frameworks, or toolchain that you deem appropriate. 
- **Time Investment**: We are a small engineering team with limited resources, and often have to make hard tradeoffs to meet deadlines and make rapid forward progress. We do not want this takehome to take more than a few hours out of your day. So, please timebox any technical work to 2-3 hours max, with 30 additional minutes dedicated to documenting your learnings and decisions. Know that you have the opportunity to discuss the tradeoffs you made when submitting your solution. Adding thoughtful commentary to the README is typically more valuable than making additional progress with technical implementation.

## Evaluation Criteria (Guideline)

| Area | Expectations |
|---|---|
| Functionality | Data is fetched, table is rendered, visualization is shown, interactions work |
| Code Quality | Clean, modular, readable, commented where needed |
| UI / UX | Clean appearance, good formatting, responsive |
| Thoughtfulness | Visualization helps provide some insight; good design choices |
| Documentation | Easy to run; clear README; explanation of tradeoffs |

We look forward to reviewing your submission! 