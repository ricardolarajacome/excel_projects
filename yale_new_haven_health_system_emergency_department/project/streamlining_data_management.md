# Combining Admission and Discharge Data in the Emergency Department

For this project, authentic hospital data from the Yale New Haven Health System emergency department's electronic medical records has been utilized. The dataset encompasses various patient details including demographics, registration information, triage assessments, medications, and related data. Access to the dataset is available at: [Yale New Haven Health System Emergency Department Data.](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0201016)

## Creation of Master File: 
Our initial objective entails amalgamating two distinct datasets: one documenting emergency visits where patients were admitted for further care (dept_b_admit.csv), and the other capturing visits where patients were discharged to their home residences (dept_b_discharge.csv). 

<br>

<img width="1433" alt="Screenshot 2024-04-20 at 6 52 50 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/6096ae27-6fa8-41ce-af25-c3e874c41f24">

<br>

It's noteworthy that within the dataset, the column arrivalhour_bin necessitates the removal of a leading character ' for uniformity. This action has been executed by employing the 'Extract' feature within the 'Transform' tab of the ribbon, followed by selecting 'Text After Delimiter' and specifying the ' character as the delimiter. 

<br>

<img width="183" alt="Screenshot 2024-04-20 at 6 55 41 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/8efa5d1c-4811-4f4c-9a5b-5b46e56295c8">

<br>

<img width="606" alt="Screenshot 2024-04-20 at 6 56 48 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/14dfdcd2-3987-4b51-912c-db0a3df4bfbc">

<br>

Subsequently, the two queries are appended to generate a new query labeled "dept_b_master". 

<br>

<img width="622" alt="Screenshot 2024-04-20 at 6 58 52 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/07aece5f-4217-4b76-9024-fff209bc61b2">

<br>

Finally, the combined queries are loaded into the Excel Workbook, revealing a total of 23,964 emergency department visits encompassing both admitted and discharged patients.

<br>

<img width="1440" alt="Screenshot 2024-04-20 at 9 11 58 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/2719f6dd-857c-4221-a45f-706da15e36e7">

<br>

## Analysis of Emergency Severity Index (ESI) Scores: 
To comprehend the distribution of ESI scores across the data collection period for department b, a breakdown of triage scores by total visits is imperative. Given that ESI levels range from 1 to 5, with level 1 signifying the highest urgency, a meticulous analysis aids in resource allocation and staffing. The initial step involves importing the dept_b_triage_vitals.csv file and merging it with the dept_b_master query utilizing the 'Merge Queries' function. 

<br>

<img width="1193" alt="Screenshot 2024-04-20 at 7 17 46 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/49d22272-afd0-45cb-a8e7-d05b65991661">

<br>

<img width="658" alt="Screenshot 2024-04-20 at 7 19 47 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/80f14400-9622-4224-8cd7-22ccb83ae162">

<br>

Subsequently, a Pivot Table is created to ascertain total PatientID counts by ESI level, culminating in the identification that 69% of total emergency department visits exhibit an ESI score of 3 or lower.

<br>

<img width="1440" alt="Screenshot 2024-04-20 at 9 18 45 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/47f9dc1a-1e11-4eb9-b5d3-267e63bb7e58">

<br>

## Examination of Abdominal Pain Presentations: 
The project extends to scrutinize the surge in patients presenting with abdominal pain in the emergency department. This involves combining emergency visit data with visit chief complaint data to gauge any correlations and to assess the admission rate for resource planning. Admission Rate, computed as the percentage of total visits with a disposition of "admit" out of total emergency department visits, is instrumental in resource management. The process commences with the importation of the dept_b_chief_complaint.csv file, followed by pivoting the Attribute column and conducting an inner join to create a new query labeled "dept_b_abdominalpain". 

<br>

<img width="722" alt="Screenshot 2024-04-20 at 7 42 36 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/94cc97c1-d4e8-4b03-99b7-3fd4a4a56780">

<br>

Subsequent analysis reveals an admission rate of 38% for patients arriving at the emergency department with the chief complaint of abdominal pain. Out of 2,444 emergency department visits with the chief complaint of Abdominal Pain, 940 (38%) warranted admission for further care, underscoring the significance of this statistic for ongoing monitoring and discussion.

<br>

<img width="1440" alt="Screenshot 2024-04-20 at 9 23 34 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/693e2759-5f95-48c5-be37-5f7b89474d58">

<br>

## Examination of Patients with Fever

Our next objective is to investigate the impact of patients presenting with a fever on their likelihood of admission. To achieve this, I will create a new column to identify the fever status based on the reported temperature during triage vitals assessment.

<img width="993" alt="Screenshot 2024-04-20 at 10 21 56 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/a1d7269c-a2f2-488d-91cf-83f2f6e457ad">

In the dept_b_master query, use the Column from Examples feature based on the selected column disposition to create a new column where "Discharge" is represented as 0 and "Admit" as 1. Name the new column "admit". Modify the earlier "Expanded dept_b_triage_vitals" step to include all columns except for PatientID and dep_name. Create a custom conditional column called "fever" based on triage_vital_temp. If the recorded temperature is not available, it should show null; if it's 100.4 degrees Fahrenheit or higher, display 1; otherwise, display 0.

<img width="1143" alt="Screenshot 2024-04-20 at 10 21 34 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/b0008b7f-2bf7-42b1-97ef-343b57e9b6bb">


## With this new column, we can extract the following insights:
13,441 visits had a recorded temperature but were classified as non-fever (below 100.4 degrees Fahrenheit).
There were 200 visits with temperatures recorded as 100.4 degrees Fahrenheit or higher.
Out of 200 visits with a fever, 89 resulted in an admission.
The highest recorded temperature among visits with a fever was 104.5 degrees Fahrenheit.

## Analysis of After-Hours Visits and Severity Breakdown

Next, I will perform an analysis of visits during after-hours periods to determine if staffing aligns well with demand. Additionally, I will assess the breakdown of Emergency Severity Index (ESI) scores during these after-hours.

<img width="868" alt="Screenshot 2024-04-20 at 10 28 17 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/14109829-ec6a-4dfd-a9e5-0db8a00271af">

In the dept_b_master query, remove any filters based on fever or admit. Create a new column called "afterhours" to denote if a visit occurred during after-hours (7:00 pm - 6:59 am) on a weekend (arrivalday as Saturday or Sunday). Close and load queries to the Excel Workbook, then create a pivot table from the dept_b_master table on a new worksheet to display after-hours visits vs. regular hours visits by ESI score.

<img width="1437" alt="Screenshot 2024-04-20 at 10 27 21 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/3ff16b4b-a75d-4f2b-a6da-72798702a979">

## Insights from Pivot Table:
There were 5,650 total visits with an ESI score of 1-2.
21.8% of after-hours visits with an ESI score were classified as high severity (ESI 1-2), similar but slightly lower than the overall percentage of high-severity visits at any arrival date/time (23.7%).
A total of 2,170 visits occurred after hours.

## Classifying EWS Scores
In the dept_b_master query, add new columns to classify heart rate values (triage_vital_hr), systolic blood pressure values (triage_vital_sbp), and respiratory rate values (triage_vital_rr) based on EWS scores. Create a new column for the total EWS score by summing up the individual scores. Sort the EWS scores in descending order.

<img width="868" alt="Screenshot 2024-04-20 at 10 28 17 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/e7dbdc5f-f547-4932-b9e0-1d514afeae89">

## Insight and Analysis
The average age for patients with an EWS of 5 or above was 53. This information will be valuable for the clinical team to understand about patients requiring critical assessment in the emergency room. By classifying heart rate, systolic blood pressure, and respiratory rate values based on EWS scores, we provided valuable insight. Notably, the average age for patients with an EWS of 5 or above was 53, which is crucial information for the clinical team.

In conclusion, this analysis provides valuable insights into emergency department operations, aiding in resource allocation, staffing, and patient care prioritization.


