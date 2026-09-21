# Outpatient Visit Analysis

This directory documents an outpatient visit analysis I conducted while completing the LinkedIn Learning course [Python Data Analysis for Healthcare](https://www.linkedin.com/learning/python-data-analysis-for-healthcare/python-data-analysis-in-healthcare), taught by Wuraola Oyewusi. The goal of this analysis is to gain insights into patient flow and identify potential sources of delay across the visit pathway.

> ⚠️ **Development Environment** Although course demonstrations used Google Colab, I completed this analysis locally in **Jupyter Notebook**, using a project-specific **`conda`** environment and **Visual Studio Code** for script development. I used this environment to acquire hands-on expertise with tools relevant to future genomics and bioinformatics workflows. Further details about how I set up this development environment are provided below.

## Contents

| File | Purpose |
|---|---|
| [`01_outpatient_visit_analysis.ipynb`](01_outpatient_visit_analysis.ipynb) | Jupyter Notebook containing the complete analysis. |

## Input Data

The analysis examines the `demo_hospital_outpatient_data_NHC.csv` dataset (available in the [`exercise_files`](../exercise_files/) working directory), a demonstration visit dataset of the outpatient department of an hypothetical hospital. This dataset stores information about **1 million outpatient visits**. The tables below record its structure and representative first five entries, respectively.

| Column        | Description                                                       |
| ------------- | ----------------------------------------------------------------- |
| Visit_Date    | Date on which the outpatient visit took place                     |
| Patient_ID    | Unique identifier assigned to each patient                        |
| Age           | Patient age at the time of the visit                              |
| Gender        | Recorded patient gender                                           |
| Diagnosis     | Primary diagnosis associated with the outpatient visit            |
| Has_Insurance | Indicates whether the patient has health insurance (TRUE / FALSE) |
| Postcode      | Patient postcode or geographic area code                          |
| Total_Cost    | Total cost associated with the outpatient visit                   |
| Registration  | Waiting time, in minutes, associated with the patient-registration stage               |
| Nursing       | Waiting time, in minutes, associated with the nursing stage of the visit               |
| Laboratory    | Waiting time, in minutes, associated with laboratory services or testing               |
| Consultation  | Waiting time, in minutes, associated with the clinical consultation                    |
| Pharmacy      | Waiting time, in minutes, associated with pharmacy services or medication collection   |

| Visit_Date | Patient_ID | Age | Gender | Diagnosis                         | Has_Insurance | Postcode | Total_Cost | Registration | Nursing | Laboratory | Consultation | Pharmacy |
| ---------- | ---------- | --- | ------ | --------------------------------- | ------------- | -------- | ---------- | ------------ | ------- | ---------- | ------------ | -------- |
| 06/05/2020 | 688923     | 68  | Female | Diabetes                          | TRUE          | 20006    | 2274       | 33           | 105     | 101        | 28           | 112      |
| 04/08/2018 | 886361     | 62  | Female | Urinary Tract Infection           | FALSE         | 20005    | 3430       | 46           | 75      | 84         | 102          | 36       |
| 10/04/2021 | 464823     | 70  | Female | Upper Respiratory Tract Infection | TRUE          | 10003    | 1836       | 107          | 81      | 5          | 77           | 36       |
| 01/10/2021 | 655214     | 8   | Female | Upper Respiratory Tract Infection | FALSE         | 10006    | 3250       | 66           | 31      | 101        | 35           | 92       |
| 30/04/2018 | 454666     | 24  | Male   | Malaria                           | TRUE          | 10006    | 2262       | 68           | 55      | 60         | 90           | 104      |

## Analysis and Tools

The analysis focuses on multiple areas of interest:
- Patient Demographics
- Yearly and Monthly Trend of Visits
- Wait Time Patterns
- Correlation Between Variables
- Visit and Insurance Costs

To this purpose, several Python tools are used:
- **pandas**: to load and prepare data, and for general data manipulation purposes;
- **openpyxl** and **zipfile**: to save the dataset to different file formats;
- **numpy** and **pyreadstats**: to compute descriptive statistics, and for general calculation purposes;
- **matplotlib** and **seaborn**: to visualize results.

## Note

This is an educational project completed as part of the LinkedIn Learning course [Python Data Analysis for Healthcare](https://www.linkedin.com/learning/python-data-analysis-for-healthcare/python-data-analysis-in-healthcare), taught by Wuraola Oyewusi. The dataset is a demonstration dataset supplied with the course and do not contain real patient data.
