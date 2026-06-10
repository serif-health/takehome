# Data Scientist Take-Home Assignment

Welcome to the take-home assignment for the Serif Health Data Scientist role. This exercise is designed to assess your ability to integrate and harmonize different data sources into a unified schema and connect respective data rows that should be comparable. 

## Objective
At Serif Health, our goal is to make healthcare price transparency easy. One reason it is not easy is because, well, very little about healthcare is easy, and even when there are rules and guardrails, the various participants in the healthcare market don't always follow them. 

Case in point - there are two different main datasets for transparency, one produced by health insurers to document the negotiated payment rates for all entities in their commercial health plan networks, and another produced by hospitals to document all insurance and cash rates they accept. Each has a different schema, and each respective insurer and hospital comply to varying degrees of correctness and completeness.

Your task is to combine a small extract from each of these two distinct data samples. One sample comes from the Transparency in Coverage data, the other comes from the Hospital Price Transparency files hosted by those specific hospitals. The objective is to combine both samples into a cohesive and unified schema that aligns the datasets on the most relevant fieldset combination. Do your best to identify the records that are common in both datasets, the fields that correspond, and to what degree the rate values in these data sets agree or disagree when you find 'matches'. A deterministic join will only get you so far — we're also interested in how you'd build a principled matching approach for cases where the keys don't line up cleanly, and how you'd think about scaling that to the full national dataset.

### Concrete Examples
The negotiated UHC Commercial reimbursement rate for CPT/HCPCS code 43239 (an endoscopy and biopsy procedure) at United Healthcare is listed at 6438 in their hospital file. When you look for the same hospital entity in the UHC payer dataset, the same rate appears. However, both files have additional rates besides 6438 - why? What columns change when the price varies? Can any of the other records be aligned? As another example, Montefiore Medical Center lists Aetna PPO rates for DRG 872 at 29259.18. Do you see that rate in the Aetna TIC extract? (Hint: You will not.) What rates *do* you see? How should we handle this case?

A few things worth thinking through as you work — and worth addressing explicitly in your README: what is DRG 872, and why might DRG-based rates structurally behave differently from CPT/HCPCS-based rates when matching across payer and hospital files? Does plan type (PPO, EPO, HMO) belong in your matching key, or does it belong in your confidence score — and what are the implications of each choice? And when you find two records that look like a match but the rates are materially different, what are the realistic reasons that could happen legitimately, and how does that affect how you'd use the match downstream?

This will involve:
- **Data Understanding**: Analyzing the structure and content of each data sample.
- **Data Integration**: Merging the data samples into a single, unified schema.
- **Data Cleaning**: Addressing any inconsistencies or discrepancies in the combined data.
- **Modeling**: Building a matching approach that goes beyond exact joins, and thinking through how it scales.
- **Documentation**: Providing clear documentation of your approach and any assumptions made.

## Data Samples

You have been provided with two data samples:

1. **Payer (TiC) Data Sample**: [Download](https://mrf.serifhealth.com/public/tic_extract_20250213.csv)
2. **Hospital (HPT) Data Sample**: [Download](https://mrf.serifhealth.com/public/hpt_extract_20250213.csv)

Each data sample has its own unique schema, format, and content. The hospital extract consisting of three hospitals' pricing data for three distinct medical billing codes. The payer extract has the same three billing codes, extracted from three of the largest (Cigna / Aetna / UHC) commercial payers' national PPO files, for the relevant hospitals. Your goal is to analyze these samples and determine the best approach to integrate their data into a unified schema. Keep in mind that these are just data samples and that Serif Health ingests several billion records for each of these datasets on a monthly basis.

## Expectations

- **Programming Language & Libraries**: You can use any appropriate language, libraries, frameworks, or toolchain that you deem appropriate.
- **Output**: A single output dataset resulting from the integration of the two data samples. At the row level, the presence of a data point from either the hospital or payer data (or both, and the relative delta between them, in the case of a match) should be shown. You should share any Python scripts, SQL, notebooks, or code extracts you use to get the job done, along with a README that explains your approach, including any assumptions, methodologies, and decisions made during the process.
- **Time Investment**: We are a small engineering team with limited resources, and often have to make hard tradeoffs to meet deadlines and make rapid forward progress. We do not want this takehome to take more than a few hours out of your day. So, please timebox any technical work to 2-3 hours max, with 30 additional minutes dedicated to documenting your learnings and decisions. Know that you have the opportunity to discuss the tradeoffs you made when submitting your solution. Adding commentary to the README (e.g. expected fill rates, issues you foresee as payer and hospital count increase, how you would design and scale the matching approach at full national data volumes, how you would ideally test and release this in a production environment, feature iterations that might come next, so on) is typically more valuable than making more progress with technical implementations.

## Submission Guidelines
1. **Repository Setup**:
   - Please locally copy to your own public repo or import to your github account for use in sharing solutions back to us. Direct public forks and pull requests will expose your identity and solution to other candidates also working on this interview question, and we want the interview process to be fair for everyone.

3. **README File**:
   - Provide a `README.md` file at the root of your repository.
   - The README should include:
     - An overview of your approach.
     - Instructions on how to run your code.
     - Any other relevant information that would help in understanding and evaluating your work.

4. **Submission**:
   - Once you have completed the assignment, share the link to your repository with us for evaluation, by emailing us at [engineering@serifhealth.com](mailto:engineering@serifhealth.com)

## Evaluation Criteria

Your submission will be evaluated based on the following criteria:

- **Correctness**: The degree to which your unified dataset accurately connects rate records between the two data samples. There is no perfect answer, and there are some very hard subproblems that will not realistically be solvable in a couple hours - that's ok. Just do what's sensible, and document any followups and todo's you'd tackle if you had more time.
- **Domain Reasoning**: How well you articulate *why* certain matches are hard, why certain rate discrepancies are expected vs. suspicious, and how the structure of US healthcare billing shapes the matching problem. This is not a question you can answer correctly without knowing the domain.
- **Modeling Judgment**: The quality of your thinking on the matching approach — not just what you built, but whether you understand where it breaks down and how you'd harden it at scale.
- **Code Quality**: Clarity, organization, and efficiency of your code.
- **Documentation**: Completeness and clarity of your documentation, including the README file.
- **Assumptions and Decisions**: Justification and reasoning behind any assumptions or decisions made during the process.

We look forward to reviewing your submission! If you have any questions or need further clarification, please do not hesitate to reach out.

Good luck!
