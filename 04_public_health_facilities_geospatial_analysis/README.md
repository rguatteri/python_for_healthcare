# Public Health Facilities Geospatial Analysis

This directory documents a geographic distribution analysis I conducted while completing the LinkedIn Learning course [Python Data Analysis for Healthcare](https://www.linkedin.com/learning/python-data-analysis-for-healthcare/python-data-analysis-in-healthcare), taught by Wuraola Oyewusi. The goal of this analysis is to gain insights into health-service locations and explore patterns that may support service planning and resource allocation.

> ⚠️ Course demonstrations used Google Colab, however, I completed this analysis in **Jupyter Notebook** and a local **`conda`** environment, using **Visual Studio Code** for script development. The reason is, I regard this setup as a valuable tool to have in my skillset (especially when it comes to genomic and bioinformatic workflows) and wanted to acquire expertise in using it.

## Contents

| File | Description |
|---|---|
| `04_public_health_facilities_geospatial_analysis.ipynb` | Jupyter Notebook containing data exploration and interactive geospatial visualisations of public health facilities. |

## Input Data

The analysis examines the `demo_health_facilities_geo_data_NHC.csv` dataset (available in the [`exercise_files`](../exercise_files/) working directory), a demonstration dataset storing geographic coordinates for hypothetical public health facilities. This dataset stores facility coordinates and facility-type information about **767 public health facilities**. The tables below record its structure and representative first five entries, respectively.

| Column | Description |
|---|---|
| `Facility Type` | Category of the public health facility (Hospital, Primary Care Center, Specialized Healthcare Center, and Pharmacy) |
| `Latitude` | Geographic latitude coordinate of the facility location |
| `Longitude` | Geographic longitude coordinate of the facility location |

| Facility Type | Latitude | Longitude |
|---|---:|---:|
| Hospital | 5.593051 | 3.697007 |
| Hospital | 10.017569 | 9.921846 |
| Hospital | 7.568808 | 11.178651 |
| Hospital | 11.574567 | 12.594134 |
| Hospital | 6.093634 | 9.334974 |

## Analysis and Tools

The analysis focuses on visualizing the geospatial location of public health facilities by creating different types of interactive maps. To this purpose, the following Python tools are used:
- **pandas**: to load and prepare data, and for general data manipulation purposes;
- **matplotlib**: to visualize the count of distinct categories of public health facilities, and for general visualization purposes;
- **geopandas**: to handle and visualize geospatial data;
- **folium**: to plot facility locations and create different types of interactive maps (e.g., filtered by selected facility categories, or heatmaps to explore their spatial concentration).

## Note

This is an educational project completed as part of the LinkedIn Learning course [Python Data Analysis for Healthcare](https://www.linkedin.com/learning/python-data-analysis-for-healthcare/python-data-analysis-in-healthcare), taught by Wuraola Oyewusi. The dataset is a demonstration dataset supplied with the course and is not real patient data.
