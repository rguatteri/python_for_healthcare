# Python Data Analysis for Healthcare

This repository contains Jupyter Notebook implementations of a collection of projects from the LinkedIn Learning course [Python Data Analysis for Healthcare](https://www.linkedin.com/learning/python-data-analysis-for-healthcare), taught by Wuraola Oyewusi. The project applies Python to a healthcare analytics scenario, covering multiple tasks:
- Exploratory Data Analysis (EDA) of Outpatient Visits
- Time-Series Forecasting of Medication Demand
- Sentiment Analysis of Patient Experience
- Geospatial Mapping of Public Health Facilities
- Data Wrangling

> ⚠️ **Development Environment** Although course demonstrations used Google Colab, I completed this analysis locally in **Jupyter Notebook**, using a project-specific **`conda`** environment and **Visual Studio Code** for script development. I used this environment to acquire hands-on expertise with tools relevant to future genomics and bioinformatics workflows.

## Repository Contents

| Directory | Project | Description |
|---|---|---|
| [`01_outpatient_visit_analysis`](01_outpatient_visit_analysis/README.md) | Outpatient Visit Analysis | Examines patient flow and waiting-time patterns across registration, nursing, laboratory, consultation, and pharmacy stages. |
| [`02_medication_demand_forecasting`](02_medication_demand_forecasting/README.md) | Medication Demand Forecasting | Uses historical pharmacy sales data and time-series forecasting to estimate future medication demand. |
| [`03_patient_experience_analytics`](03_patient_experience_analytics/README.md) | Patient Experience Analytics | Explores laboratory patient feedback through ratings, waiting times, interactive visualisations, and sentiment analysis of written reviews. |
| [`04_public_health_facilities_geospatial_analysis`](04_public_health_facilities_geospatial_analysis/README.md) | Public Health Facilities Geospatial Analysis | Maps the geographic distribution of hypothetical health facilities and explores facility-density patterns. |
| [`05_healthcare_data_wrangling`](05_healthcare_data_wrangling/README.md) | Healthcare Data Wrangling | Converts unstructured generic-medication records into structured datasets and compares the original course workflow with an improved implementation. |

> Each working folder contains a dedicated README with project-specific context, input-data documentation, workflow details, and results.

## Learning Objectives

The course focused on applying Python to common healthcare-data tasks, including:

- Understanding the role of clinical, administrative, operational, public-health, and pharmacy data in healthcare decision-making.
- Preparing datasets for analysis by identifying and addressing common problems related to data quality, cleanliness, and structure.
- Manipulating healthcare data with **pandas** and **NumPy**.
- Creating static, interactive, and geographic visualisations with **matplotlib**, **seaborn**, **Plotly**, and **Folium**.
- Exploring relationships between variables through descriptive analysis, correlations, and visualisations.
- Applying text-based sentiment analysis to patient-experience reviews.
- Developing reusable functions and scripts to automate repetitive analytical tasks.
- Evaluating data-storage approaches, including relational databases, NoSQL databases, and cloud storage.
- Applying time-series analysis and **Prophet** forecasting to support healthcare-resource and medication-demand planning.

## Skills Demonstrated

Across the projects in this repository, I practised:

- Healthcare data cleaning, transformation, and quality assessment.
- Exploratory data analysis and descriptive statistics.
- Static and interactive data visualisation.
- Analysis of patient flow, service waiting times, and patient experience.
- Pharmacy-data analysis and medication-demand forecasting.
- Geospatial visualisation of public-health facilities.
- Natural-language processing and sentiment analysis of free-text feedback.
- Text parsing with string operations and regular expressions.
- Creation of structured CSV outputs from unstructured text data.
- Project organisation and technical documentation with GitHub and Markdown.

## Technologies and Libraries

- **Language:** Python
- **Core data analysis:** pandas, NumPy
- **Visualisation:** matplotlib, seaborn, Plotly
- **Geospatial analysis:** Folium
- **Forecasting:** Prophet
- **Text analysis:** TextBlob
- **Notebook environment:** Jupyter Notebook

## Development Environment

Before beginning this project, I had previously used a standard Python installation through Git Bash. I then set up a dedicated local data-analysis environment based on **Anaconda**, **Visual Studio Code**, and **Jupyter Notebook**.

- Performed a clean Anaconda reinstallation on Windows, removing remnants of the previous installation first to avoid obsolete shortcuts, PATH conflicts, and environment-configuration issues.
- Installed the official **Python** extension for Visual Studio Code.
- Configured VS Code to use the Anaconda Python interpreter by selecting the relevant `python.exe` executable through **Python: Select Interpreter**.
- Initialised conda for PowerShell with:

  ```powershell
  conda init powershell
  ```

  This enabled conda environment activation directly within the VS Code integrated PowerShell terminal.
- Created a dedicated conda environment named `python_for_healthcare` and configured VS Code to use that environment rather than the default `base` environment.

This local setup was chosen to develop practical experience with conda environments, Jupyter-based analysis, and VS Code—tools that are particularly relevant to future data-analysis, genomic, and bioinformatics workflows.

## Project Structure

Each numbered folder contains one or more Jupyter Notebooks and a dedicated README. The folder-level documentation provides the most detailed information about the relevant dataset, analytical workflow, libraries, outputs, and project-specific considerations.

The `05_healthcare_data_wrangling` folder contains two notebooks:

- `05_original_healthcare_data_wrangling.ipynb` reproduces the course-based workflow.
- `05_healthcare_data_wrangling.ipynb` presents an improved version that standardises whitespace and separates medication names from dosage information.

## Note

All projects documented in this repository are educational projects completed as part of the LinkedIn Learning course [Python Data Analysis for Healthcare](https://www.linkedin.com/learning/python-data-analysis-for-healthcare/python-data-analysis-in-healthcare), taught by Wuraola Oyewusi. All datasets are demonstration datasets supplied with the course and do not contain real patient data.

## Acknowledgements

- Course: [Python Data Analysis for Healthcare](https://www.linkedin.com/learning/python-data-analysis-for-healthcare)
- Instructor: [Wuraola Oyewusi](https://www.linkedin.com/learning/instructors/wuraola-oyewusi)
- Platform: LinkedIn Learning

The project notebooks are based on course demonstrations and have been organised, documented, and—in the healthcare data-wrangling project—extended to support my own learning and portfolio development.
