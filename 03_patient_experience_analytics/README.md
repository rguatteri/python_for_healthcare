# Patient Experience Analytics

This project analyses patient-experience feedback collected by a hypothetical laboratory. It explores how staff ratings, speed ratings, waiting times, test types, and free-text reviews can be used to understand patient satisfaction and identify potential areas for service improvement.

## Environment

The analysis was developed locally with Python, Anaconda, Visual Studio Code, and Jupyter Notebook.

## Contents

| File | Description |
|---|---|
| `03_patient_experience_analytics.ipynb` | Jupyter Notebook containing exploratory analysis, interactive visualisations, and sentiment analysis of patient-experience feedback. |

## Input Data

The analysis uses `demo_patient_experience_data_NHC.csv`, a course-provided demonstration dataset containing feedback records from a hypothetical laboratory.

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

> **Note:** The source file also contains an `Unnamed: 0` column, which represents a saved row index rather than a meaningful analytical variable.

The table below displays the first five observations in the dataset. Reviews have been shortened for readability.

| Entry Code | Feedback Date | Patient Age | Staff Rating | Speed Rating | Wait Time (minutes) | Test Type | Review |
|---:|---|---:|---:|---:|---:|---|---|
| 1 | 2022-10-22 | 61 | 5 | 3 | 29 | Urine Test | “I couldn't have asked for better service from the staff, it was top-notch...” |
| 2 | 2022-01-12 | 26 | 3 | 4 | 171 | Biopsy | “I'm indifferent about the service provided by the staff; it neither impressed nor upset me...” |
| 3 | 2022-04-06 | 53 | 3 | 5 | 176 | Urine Test | “My experience with the staff was neither good nor bad, just average...” |
| 4 | 2022-03-15 | 34 | 4 | 3 | 67 | Ultrasound | “The staff was decent, but there were minor areas that could be better...” |
| 5 | 2022-12-13 | 28 | 1 | 1 | 45 | CT Scan | “The service was abysmal, and I'm extremely unsatisfied...” |

## Analysis and Tools

- Loaded, inspected, and prepared patient-experience data with **pandas**.
- Explored the distributions of staff ratings, speed ratings, waiting times, patient ages, and laboratory test types.
- Created interactive visualisations with **Plotly** to examine patterns and relationships in the feedback data.
- Applied **TextBlob** sentiment analysis to the free-text patient reviews.
- Categorised review sentiment as positive, neutral, or negative to support interpretation of patient feedback.
- Visualised sentiment patterns to identify opportunities for improving patient experience and service quality.

**Libraries:** pandas, matplotlib, Plotly, and TextBlob.

> **Note:** This is an educational project completed as part of the *Python Data Analysis for Healthcare* course by Wuraola Oyewusi on LinkedIn Learning. The dataset is a demonstration dataset supplied with the course and is not real patient data.
