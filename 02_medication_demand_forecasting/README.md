# Medication Demand Forecasting

This directory documents a medication demand forecasting analysis I conducted while completing the LinkedIn Learning course [Python Data Analysis for Healthcare](https://www.linkedin.com/learning/python-data-analysis-for-healthcare/python-data-analysis-in-healthcare), taught by Wuraola Oyewusi. The goal of this analysis is to gain insights into historical pharmacy sales data and estimate future medication demand by applying time-series forecasting. Most notably, forecasting medication demand can support inventory planning and help reduce the risk of stock shortages or overstocking.

> ⚠️ Course demonstrations used Google Colab, however, I completed this analysis in **Jupyter Notebook** and a local **`conda`** environment, using **Visual Studio Code** for script development. The reason is, I regard this setup as a valuable tool to have in my skillset (especially when it comes to genomic and bioinformatic workflows) and wanted to acquire expertise in using it.

## Contents

| File | Description |
|---|---|
| `02_medication_demand_forecasting.ipynb` | Jupyter Notebook containing the complete analysis. |

## Input Data

The analysis examines the `demo_pharmacy_sales_data.csv` dataset (available in the [`exercise_files`](../exercise_files/) working directory), a demonstration dataset storing medication class and sales data of an hypothetical pharmacy. This dataset stores information about **1 million pharmacy-sale records**. The tables below record its structure and representative first five entries, respectively.

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

The analysis focuses on the following areas of interest:
- Medication Class Frequency
- Medication Demand Forecasting

To this purpose, the following Python tools are used:
- **pandas**: to load and prepare data, and for general data manipulation purposes;
- **matplotlib**, **seaborn**, and **WordCloud**: to explore medication sales and demand patterns over time through data visualisation (WordCloud is specifically used to create word clouds);
- **numpy**: for general calculation purposes;
- **Prophet**: to conduct the medication demand forecasting analysis.

## Note

This is an educational project completed as part of the LinkedIn Learning course [Python Data Analysis for Healthcare](https://www.linkedin.com/learning/python-data-analysis-for-healthcare/python-data-analysis-in-healthcare), taught by Wuraola Oyewusi. The dataset is a demonstration dataset supplied with the course and is not real patient data.
