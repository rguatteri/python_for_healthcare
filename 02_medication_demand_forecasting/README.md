# Medication Demand Forecasting

This project analyses historical pharmacy-sales data and applies time-series forecasting to estimate future medication demand. Forecasting medication demand can support inventory planning and help reduce the risk of stock shortages or overstocking.

## Environment

The analysis was developed locally with Python, Anaconda, Visual Studio Code, and Jupyter Notebook.

## Contents

| File | Description |
|---|---|
| `02_medication_demand_forecasting.ipynb` | Jupyter Notebook containing data preparation, exploratory analysis, and medication-demand forecasting. |

## Input Data

The analysis uses `demo_pharmacy_sales_data.csv`, a course-provided demonstration dataset containing pharmacy-sale records.

| Column | Description |
|---|---|
| `Date Sold` | Date on which the medication sale was recorded |
| `Med_name` | Name, formulation, and strength of the medication sold |
| `Med_class` | Pharmacological or therapeutic class of the medication |
| `Quantity Sold` | Number of medication units sold in the recorded transaction |
| `Price` | Recorded price associated with the medication sale |

The table below displays the first five observations in the dataset:

| Date Sold | Med_name | Med_class | Quantity Sold | Price |
|---|---|---|---:|---:|
| 07/05/2021 | Clotrimazole Topical Cream (2%) | Antifungal | 66 | 86.9 |
| 09/08/2021 | Alprostadil Urethral Suppository (125 mcg) | Prostaglandin E1 Analog | 15 | 22.9 |
| 15/06/2021 | Methyltestosterone Tablet (10 mg) | Androgen Hormone | 5 | 5.9 |
| 19/02/2021 | Buspirone Tablet (5 mg) | Anxiolytic | 89 | 55.7 |
| 24/09/2022 | Hydrocodone/Acetaminophen Tablet (5/325 mg) | Opioid Analgesic/Analgesic Combination | 79 | 0.7 |

## Analysis and Tools

- Loaded, inspected, and prepared pharmacy sales data with **pandas**.
- Explored medication sales and demand patterns over time through data visualisation.
- Reshaped historical sales data into a time-series format suitable for forecasting.
- Applied **Prophet** to generate a forecast of future medication demand.
- Visualised forecasted demand and its uncertainty intervals.

**Libraries:** pandas, matplotlib, seaborn, and Prophet.

> **Note:** This is an educational project completed as part of the *Python Data Analysis for Healthcare* course by Wuraola Oyewusi on LinkedIn Learning. The dataset is a demonstration dataset supplied with the course and is not real patient data.
