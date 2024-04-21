# Combining Admission and Discharge Data in the Emergency Department

For this project, authentic hospital data from the Yale New Haven Health System emergency department's electronic medical records has been utilized. The dataset encompasses various patient details including demographics, registration information, triage assessments, medications, and related data. Access to the dataset is available at: [Yale New Haven Health System Emergency Department Data.](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0201016)

## Creation of Master File: 
Our initial objective entails amalgamating two distinct datasets: one documenting emergency visits where patients were admitted for further care (dept_b_admit.csv), and the other capturing visits where patients were discharged to their home residences (dept_b_discharge.csv). 


<img width="1433" alt="Screenshot 2024-04-20 at 6 52 50 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/6096ae27-6fa8-41ce-af25-c3e874c41f24">


It's noteworthy that within the dataset, the column arrivalhour_bin necessitates the removal of a leading character ' for uniformity. This action has been executed by employing the 'Extract' feature within the 'Transform' tab of the ribbon, followed by selecting 'Text After Delimiter' and specifying the ' character as the delimiter. 


<img width="183" alt="Screenshot 2024-04-20 at 6 55 41 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/8efa5d1c-4811-4f4c-9a5b-5b46e56295c8">

<img width="606" alt="Screenshot 2024-04-20 at 6 56 48 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/14dfdcd2-3987-4b51-912c-db0a3df4bfbc">


Subsequently, the two queries are appended to generate a new query labeled "dept_b_master". 


<img width="622" alt="Screenshot 2024-04-20 at 6 58 52 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/07aece5f-4217-4b76-9024-fff209bc61b2">


Finally, the combined queries are loaded into the Excel Workbook, revealing a total of 23,964 emergency department visits encompassing both admitted and discharged patients.


<img width="1440" alt="Screenshot 2024-04-20 at 9 11 58 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/2719f6dd-857c-4221-a45f-706da15e36e7">


## Analysis of Emergency Severity Index (ESI) Scores: 
To comprehend the distribution of ESI scores across the data collection period for department b, a breakdown of triage scores by total visits is imperative. Given that ESI levels range from 1 to 5, with level 1 signifying the highest urgency, a meticulous analysis aids in resource allocation and staffing. The initial step involves importing the dept_b_triage_vitals.csv file and merging it with the dept_b_master query utilizing the 'Merge Queries' function. Subsequently, a Pivot Table is created to ascertain total PatientID counts by ESI level, culminating in the identification that 69% of total emergency department visits exhibit an ESI score of 3 or lower.

## Examination of Abdominal Pain Presentations: 
The project extends to scrutinize the surge in patients presenting with abdominal pain in the emergency department. This involves combining emergency visit data with visit chief complaint data to gauge any correlations and to assess the admission rate for resource planning. Admission Rate, computed as the percentage of total visits with a disposition of "admit" out of total emergency department visits, is instrumental in resource management. The process commences with the importation of the dept_b_chief_complaint.csv file, followed by pivoting the Attribute column and conducting an inner join to create a new query labeled "dept_b_abdominalpain". Subsequent analysis reveals an admission rate of 38% for patients arriving at the emergency department with the chief complaint of abdominal pain. Out of 2,444 emergency department visits with the chief complaint of Abdominal Pain, 940 (38%) warranted admission for further care, underscoring the significance of this statistic for ongoing monitoring and discussion.
