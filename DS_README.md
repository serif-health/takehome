
# Data Scientist Take-Home Assignment

Welcome to the take-home assignment for the Serif Health Data Scientist role. This exercise is designed to assess your ability to integrate and harmonize different data sources into a unified schema and connect respective data rows that should be comparable. 

## Objective
At Serif Health, our goal is to make healthcare price transparency easy. One reason it is not easy is because, well, very little about healthcare is easy, and even when there are rules and guardrails, the various participants in the healthcare market don't always follow them. 

Case in point - there are two different main datasets for transparency, one produced by health insurers and another produced by hospitals. Each has a different schema, and each respective insurer and hospital comply to varying degrees of correctness and completeness.

Your task is to combine a small extract from each of these two distinct data samples consisting of three hospitals' pricing data for ten distinct medical billing codes. One sample comes from the Transparency in Coverage data, the other comes from the Hospital Price Transparency files hosted by those specific hospitals. The objective is to combine both samples into a cohesive and unified schema that aligns each billing code / payer / hospital combination. Do your best to identify the records that are common in both datasets and identify to what degree these data sets agree or disagree. 

### Concrete Example
The negotiated Aetna Commercial reimbursement rate for CPT/HCPCS code 43239 (an endoscopy and biospy procedure) at Montefiore Medical Center is listed at 1246.73 in their hospital file. When you look for the same hospital entity in the Aetna payer dataset, you'll find many different rates for 43239. Which rate is best to cross-compare? How might you align the sources?

This will involve:
- **Data Understanding**: Analyzing the structure and content of each data sample.
- **Data Integration**: Merging the data samples into a single, unified schema.
- **Data Cleaning**: Addressing any inconsistencies or discrepancies in the combined data.
- **Documentation**: Providing clear documentation of your approach and any assumptions made.

## Data Samples

You have been provided with two data samples:

1. **Payer Data Sample**: [Download](https://mrf.serifhealth.com/public/payer_extract_202502.csv)
2. **Hospital Data Sample**: [Download](https://mrf.serifhealth.com/public/hospital_extract_202502.csv)

Each data sample has its own unique schema, format, and content. Your goal is to analyze these samples and determine the best approach to integrate them into a unified schema.

## Expectations

- **Programming Language & Libraries**: You can use any appropriate language, libraries, frameworks, or toolchain that you deem appropriate.
- **Output**: A unified dataset resulting from the integration of the two data samples, as well as any Python scripts, SQL, notebooks, or code extracts you use to get the job done, along with a README that explains your approach, including any assumptions, methodologies, and decisions made during the process.
- **Time Investment**: We are a small engineering team with limited resources, and often have to make hard tradeoffs to meet deadlines and make rapid forward progress. We do not want this takehome to take more than a few hours out of your day. So, please timebox any solution to two hours max, and know that you have the opportunity to discuss the tradeoffs you made when submitting your solution. If you finish early, we'd recommend adding additional notes or commentary to the README (e.g. discussion of performance characteristics, how you would ideally test and release this in a production environment, feature iterations that might come next, so on).
 
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
   - Once you have completed the assignment, share the link to your repository with us for evaluation, by email us at [engineering@serifhealth.com](mailto:engineering@serifhealth.com)

## Evaluation Criteria

Your submission will be evaluated based on the following criteria:

- **Correctness**: The degree to which your unified dataset accurately connects rate records between the two data samples. There is no perfect answer, and there are some very hard subproblems that may not be solvable in a couple hours - that's ok. Just document those as todo's for future.
- **Code Quality**: Clarity, organization, and efficiency of your code.
- **Documentation**: Completeness and clarity of your documentation, including the README file.
- **Assumptions and Decisions**: Justification and reasoning behind any assumptions or decisions made during the integration process.

We look forward to reviewing your submission! If you have any questions or need further clarification, please do not hesitate to reach out.

Good luck!
