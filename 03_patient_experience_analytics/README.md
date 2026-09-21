# Patient Experience Analytics

This directory documents a patient experience analysis I conducted while completing the LinkedIn Learning course [Python Data Analysis for Healthcare](https://www.linkedin.com/learning/python-data-analysis-for-healthcare/python-data-analysis-in-healthcare), taught by Wuraola Oyewusi. The goal of this analysis is to gain insights into patient-experience feedback and explore staff ratings, speed ratings, waiting times, test types, and free-text reviews. Most notably, these variables can support the understanding of patient satisfaction and the identification of potential areas for service improvement

> ⚠️ **Development Environment** Although course demonstrations used Google Colab, I completed this analysis locally in **Jupyter Notebook**, using a project-specific **`conda`** environment and **Visual Studio Code** for script development. I used this environment to acquire hands-on expertise with tools relevant to future genomics and bioinformatics workflows. Further details about how I set up this development environment are provided below.

## Contents

| File | Description |
|---|---|
| `03_patient_experience_analytics.ipynb` | Jupyter Notebook containing the complete analysis. |

## Input Data

The analysis examines the `demo_patient_experience_data_NHC.csv` dataset (available in the [`exercise_files`](../exercise_files/) working directory), a demonstration dataset storing feedback records from a hypothetical laboratory. This dataset stores information about **20000 feedback records**. The tables below record its structure and representative first five entries, respectively (in the latter, reviews have been shortened for readability).

| Column | Description |
|---|---|
| `Entry Code` | Unique identifier assigned to each feedback record |
| `Feedback Date` | Date on which the patient feedback was recorded |
| `Patient Age` | Age of the patient providing feedback |
| `Staff Rating` | Patient rating of staff service |
| `Speed Rating` | Patient rating of service speed |
| `Wait Time (minutes)` | Waiting time recorded for the patient, expressed in minutes |
| `Test Type` | Type of laboratory test received by the patient |
| `Review` | Free-text patient feedback describing their experience |

| Entry Code | Feedback Date | Patient Age | Staff Rating | Speed Rating | Wait Time (minutes) | Test Type | Review |
|---:|---|---:|---:|---:|---:|---|---|
| 1 | 2022-10-22 | 61 | 5 | 3 | 29 | Urine Test | “I couldn't have asked for better service from the staff, it was top-notch...” |
| 2 | 2022-01-12 | 26 | 3 | 4 | 171 | Biopsy | “I'm indifferent about the service provided by the staff; it neither impressed nor upset me...” |
| 3 | 2022-04-06 | 53 | 3 | 5 | 176 | Urine Test | “My experience with the staff was neither good nor bad, just average...” |
| 4 | 2022-03-15 | 34 | 4 | 3 | 67 | Ultrasound | “The staff was decent, but there were minor areas that could be better...” |
| 5 | 2022-12-13 | 28 | 1 | 1 | 45 | CT Scan | “The service was abysmal, and I'm extremely unsatisfied...” |

> The source file also contains an `Unnamed: 0` column, which represents a saved row index rather than a meaningful analytical variable.

## Analysis and Tools

The analysis focuses on the following areas of interest:
- Laboratory Patient Experience
- Sentiment Analysis of Patient Experience Reviews

To this purpose, the following Python tools are used:
- **pandas**: to load and prepare data, and for general data manipulation purposes;
- **matplotlib** and **plotly**: to explore patient experience and sentiment through data visualisation (plotly is specifically used to create interactive visualizations);
- **TextBlob**: to analyze free-text patient reviews and categorise their sentiment as positive, negative, or neutral.

## Note

This is an educational project completed as part of the LinkedIn Learning course [Python Data Analysis for Healthcare](https://www.linkedin.com/learning/python-data-analysis-for-healthcare/python-data-analysis-in-healthcare), taught by Wuraola Oyewusi. The dataset is a demonstration dataset supplied with the course and do not contain real patient data.
