# HEALTHCARE-DATA-ANALYTICS-WITH-HEALFICA
The 30-Day Readmission Penalty

HEALFICA COMMUNITY | Healthcare Data Challenge 01
1. Project Overview

This project investigates 30-day readmission patterns among hospital encounters involving patients with diabetes. The objective is to identify characteristics associated with higher observed readmission rates and develop a simple, explainable prioritisation rule that could inform care-coordination planning.
Stakeholder: Vice President of Population Health, Meridian Care Network.
Tools: Microsoft Excel, Power Query, and Microsoft Power BI.

2. Business Problem
Healthcare teams need to understand which groups of encounters experience higher observed readmission rates and how limited care-coordination resources might be prioritised.
The project addresses the overall 30-day readmission rate, variation across patient and admission characteristics, the development of a preliminary risk flag, and the workload implications of targeting the flagged group.

3. Dataset
The analysis uses the UCI Diabetes 130-US Hospitals dataset covering 1999–2008.
The original dataset contains 101,766 inpatient encounters, 50 variables, and records from 130 US hospitals.
Each row represents a hospital encounter rather than necessarily a unique patient. The same patient may therefore appear in multiple rows.

4. Data Preparation
Data preparation was carried out using Excel and Power Query.
Key steps included:
•	Inspecting missing values, unusual categories, and data types.
•	Checking for duplicate encounter rows.
•	Standardising unknown and invalid category labels.
•	Preserving diagnosis codes as text.
•	Joining human-readable admission, discharge, and admission-source descriptions from the mapping file.
•	Creating a binary 30-day readmission outcome.
•	Creating grouped categories for previous inpatient visits.
•	Creating a preliminary encounter-prioritisation flag.
The original raw data was retained separately from the cleaned data.
Values represented by ? were treated as unknown rather than automatically deleted or replaced with invented values. Detailed cleaning decisions and record counts are documented in the cleaning log.

5. Definition of 30-Day Readmission
The original readmission field contains three categories:
•	<30: Readmitted within 30 days.
•	>30: Readmitted after 30 days.
•	NO: No recorded readmission.
For the binary outcome, <30 was classified as Yes, while >30 and NO were classified as No.
This distinction ensures that readmissions occurring after 30 days are not incorrectly counted as 30-day readmissions.

6. Analytical Questions
The analysis examined:
1.	What proportion of encounters were followed by a recorded readmission within 30 days?
2.	How did observed readmission rates vary across age groups?
3.	How did rates vary by admission type and length of stay?
4.	How were medication counts and previous healthcare utilisation associated with readmission?
5.	Could a simple, explainable rule identify a group with a higher observed readmission rate?
6.	What would targeting that group mean for the number of encounters receiving follow-up?

7. Key Findings
The analysis identified 11,357 recorded 30-day readmissions among 101,766 encounters, corresponding to an overall observed rate of approximately 11.2%.
Emergency admissions recorded an observed rate of 11.5% across 53,990 encounters.
The 10-day length-of-stay category recorded a rate of 14.3% across 2,342 encounters, while one-day stays recorded a rate of 8.2% across 14,208 encounters.
Previous inpatient utilisation showed a clear descriptive pattern. The observed readmission rate rose from 8.4% among encounters with no previous inpatient visits to 36.4% among encounters with five or more previous inpatient visits.
Readmission rates varied across age groups rather than increasing steadily with age.

8. Preliminary Risk Flag
The analytical rule classified an encounter as Higher Priority when the recorded number of previous inpatient visits was at least two. Encounters below this threshold were classified as Standard Priority.
The Higher Priority group contained 14,615 encounters and had an observed 30-day readmission rate of 21.4%. The Standard Priority group contained 87,151 encounters and had a rate of 9.4%.
The rule identified 3,128 of the 11,357 recorded 30-day readmissions, capturing 27.5% of readmissions. The remaining 72.5% occurred in the Standard Priority group.
This is an exploratory prioritisation rule based on observed patterns. It is not a clinically validated prediction model, diagnosis, or substitute for clinical judgement.

9. Workload Estimate
Under an illustrative assumption of one follow-up contact per encounter, targeting the Higher Priority group would involve 14,615 contacts, compared with 101,766 contacts if every encounter were targeted.
This represents an 85.6% reduction in the number of contacts in the illustrative scenario.
The dataset contains encounters rather than unique patients, and it does not provide actual contact duration, staffing costs, or coordination costs. The estimate therefore represents a comparison of encounter volumes, not confirmed savings.

10. Recommendations
•	Investigate previous inpatient utilisation as one of several signals for discharge-planning review.
•	Consider testing the preliminary rule alongside existing clinical assessment processes.
•	Avoid excluding Standard Priority encounters from all follow-up solely because they do not meet the rule.
•	Validate the approach using more recent patient-level data before operational adoption.
•	Monitor readmission outcomes, follow-up completion, and workload during any pilot.

11. Limitations
The dataset covers 1999–2008 and may not reflect current healthcare practices.
The analysis is observational and cannot establish that any characteristic causes readmission.
The preliminary risk flag has not been clinically validated and captures only a minority of recorded 30-day readmissions.
Encounter counts do not equal unique patient counts. The workload estimate is illustrative and does not represent measured financial savings.
Very small categories can produce unstable readmission rates, so group sizes should always be considered alongside percentages.

12. Project Files
•	HEALFICA_Cleaned_Diabetic_Encounters.xlsx — cleaned analytical dataset.
•	Data_Dictionary — definitions and handling of analytical fields.
•	Cleaning_Log — documented data preparation decisions.
•	Recommendation_Memo — findings and proposed actions for the stakeholder.
•	README.md — project documentation.
•	Power BI dashboard — visual presentation of the analysis.

13. Dashboard
Dashboard link is unavailable.

14. Conclusion
This analysis demonstrates how healthcare encounter data can be used to identify differences in observed 30-day readmission rates and explore potential prioritisation strategies.
Previous inpatient utilisation was associated with higher observed readmission rates in the dataset. However, the preliminary flag's limited coverage of recorded readmissions means that it should support further investigation and clinical assessment rather than operate as a standalone screening method.
