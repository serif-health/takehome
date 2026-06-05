# Full Stack Engineer Take-Home Assignment

## Searchable Price Transparency Explorer

**Time budget**: ~2–3 hours  
**Role**: Full Stack Engineer  
**Skills evaluated**: data ingestion, file parsing, backend/API design, frontend search and filtering, UI/UX, code structure, documentation, and pragmatic tradeoff decisions.


## Overview

For this exercise, you will build a small full-stack application that reads a Transparency in Coverage index file, follows the referenced in-network rate files, normalizes the data, and makes it searchable through a user interface.

The goal is to show how you think about working with CMS-style machine-readable files end to end:

1. Read and parse the index file
2. Discover the in-network file URLs referenced in the index
3. Load one or more rate files from those URLs
4. Extract useful fields into a search-friendly shape
5. Present the results in a UI that supports filtering and exploration

This is intentionally open-ended. We care more about clear decisions, a working implementation, and a UI that makes the data easy to explore than about building a perfect production-grade pipeline.


## Data Source

Use this index file as the starting point for your solution:

```
https://www.centene.com/content/dam/centene/Centene%20Corporate/json/DOCUMENT/2026-04-28_fidelis_index.json
```

If link above is out of date the new can be found here: https://www.centene.com/price-transparency-files.html 

This file follows the CMS Transparency in Coverage table-of-contents conventions described in the CMS guide:

https://github.com/CMSgov/price-transparency-guide

The index contains reporting plan metadata and references to one or more in-network files. Your solution should use the index as the source of truth for which rate files to load, but you do not need to handle every possible edge case in the CMS format.


## Requirements

Your submission should satisfy the following:

### Functional Requirements

1. **Index Parsing**
	- Fetch and parse the index file above.
	- Extract the relevant in-network file URLs from the index structure.

2. **Rate File Ingestion**
	- Fetch the referenced in-network rate files.
	- Normalize the data into a searchable shape.
	- Keep the ingestion logic simple and workable for the provided files.

3. **Searchable UI**
	- Build a UI that lets a reviewer search and browse the loaded rate data.
	- Include a required search input for a specific billing code.
	- Support an optional set of provider identifiers to narrow results (for example NPI and/or EIN).
	- Show enough context for a reviewer to understand what result they are looking at and which source file it came from.

4. **Error Handling**
	- Keep error handling basic so the app does not crash if a fetch or parse error is encountered.
	- Show a simple loading or error state when something goes wrong.


## Deliverables

1. A git repo (GitHub, GitLab, etc.) containing your code
2. A `README.md` with:
	- Instructions to install and run
	- A short description of your architecture and data flow
	- Your assumptions, design decisions, and tradeoffs
	- What you would improve with more time
3. A working application that demonstrates the data ingestion and search experience


## Expectations

- **Programming Language & Libraries**: We use Vue.js and Golang internally, but you are welcome to submit in other languages, libraries, frameworks, or toolchains that you deem appropriate.
- **Architecture**: Choose a reasonable split between backend and frontend responsibilities. For example, you might use the backend to fetch and normalize the files and the frontend to query the resulting dataset.
- **Time Investment**: We are a small engineering team with limited resources, and often have to make hard tradeoffs to meet deadlines and make rapid forward progress. We do not want this takehome to take more than a few hours out of your day. Please timebox the technical work to 2–3 hours max, with additional time for documenting your learnings and decisions.


## Evaluation Criteria

| Area | Expectations |
|---|---|
| Functionality | Index is parsed, rate files are loaded, code search works, optional provider identifier filtering works, interactions are reliable |
| Code Quality | Clean, modular, readable, and appropriately structured |
| UI / UX | Clear presentation, useful search and filter controls, responsive layout |
| Data Handling | Sensible normalization, resilient parsing, good source traceability |
| Thoughtfulness | Good tradeoffs for CMS-style files, honest discussion of limitations |
| Documentation | Easy to run, clear README, concise explanation of the approach |


## Hints And Pointers

- The index is a table-of-contents style file and may reference multiple plans and file URLs.
- CMS transparency files can be large, nested, and inconsistent across issuers. A robust solution should not assume every file is perfectly uniform.
- A useful implementation often separates ingestion from presentation, even if both live in the same repo.
- Consider whether you want to search by plan name, issuer, billing code, facility, location, or other fields exposed in the source files.
- If you make simplifying assumptions, call them out clearly in the README.


## Submission Guidelines

1. **Repository Setup**:
	- Please locally copy this takehome to your own public repo or import it to your GitHub account before sharing your solution.
	- Direct public forks and pull requests will expose your identity and solution to other candidates also working on this interview question, and we want the interview process to be fair for everyone.

2. **README File**:
	- Provide a `README.md` file at the root of your repository.
	- Include an overview of your approach, how to run the app, and any assumptions or tradeoffs that would help us evaluate your work.

3. **Submission**:
	- Once you have completed the assignment, share the link to your repository with us for evaluation by emailing [engineering@serifhealth.com](mailto:engineering@serifhealth.com).


We look forward to reviewing your submission.
