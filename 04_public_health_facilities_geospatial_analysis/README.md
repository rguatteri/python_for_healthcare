# Public Health Facilities Geospatial Analysis

This project analyses the geographic distribution of hypothetical public health facilities through interactive mapping. It uses facility coordinates and facility-type information to visualise health-service locations and explore patterns that may support service planning and resource allocation.

## Environment

The analysis was developed locally with Python, Anaconda, Visual Studio Code, and Jupyter Notebook.

## Contents

| File | Description |
|---|---|
| `04_public_health_facilities_geospatial_analysis.ipynb` | Jupyter Notebook containing data exploration and interactive geospatial visualisations of public health facilities. |

## Input Data

The analysis uses `demo_health_facilities_geo_data_NHC.csv`, a course-provided demonstration dataset containing geographic coordinates for hypothetical public health facilities.

| Column | Description |
|---|---|
| `Facility Type` | Category of the public health facility |
| `Latitude` | Geographic latitude coordinate of the facility location |
| `Longitude` | Geographic longitude coordinate of the facility location |

The dataset includes four facility categories: Hospital, Primary Care Center, Specialized Healthcare Center, and Pharmacy.

The table below displays the first five observations in the dataset:

| Facility Type | Latitude | Longitude |
|---|---:|---:|
| Hospital | 5.593051 | 3.697007 |
| Hospital | 10.017569 | 9.921846 |
| Hospital | 7.568808 | 11.178651 |
| Hospital | 11.574567 | 12.594134 |
| Hospital | 6.093634 | 9.334974 |

## Analysis and Tools

- Loaded and inspected geographic facility data with **pandas**.
- Identified the distinct categories of public health facilities included in the dataset.
- Created interactive maps with **Folium** and plotted facility locations using markers coloured by facility type.
- Filtered the dataset to visualise selected facility categories, such as hospitals and pharmacies.
- Created a heat map to explore the spatial concentration of facilities.
- Applied marker clustering to improve the readability of maps containing many facility locations.

**Libraries:** pandas and Folium.

> **Note:** This is an educational project completed as part of the *Python Data Analysis for Healthcare* course by Wuraola Oyewusi on LinkedIn Learning. The dataset is a demonstration dataset supplied with the course. The facilities and geographic locations are hypothetical and do not represent real healthcare facilities.
