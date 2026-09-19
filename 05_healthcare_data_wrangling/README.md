# Healthcare Data Wrangling

This directory documents the preparation process of unstructured medication data for analysis purposes, as demonstrated in the LinkedIn Learning course [Python Data Analysis for Healthcare](https://www.linkedin.com/learning/python-data-analysis-for-healthcare/python-data-analysis-in-healthcare), taught by Wuraola Oyewusi. The workflow converts a plain-text list of generic medication names, dosage information, and medication classes into a structured CSV output.

> ⚠️ Course demonstrations used Google Colab, however, I completed this analysis in **Jupyter Notebook** and a local **`conda`** environment, using **Visual Studio Code** for script development. The reason is, I regard this setup as a valuable tool to have in my skillset (especially when it comes to genomic and bioinformatic workflows) and wanted to acquire expertise in using it.

## Contents

| File | Description |
|---|---|
| `05_original_healthcare_data_wrangling.ipynb` | Course-based Jupyter Notebook. |
| `05_healthcare_data_wrangling.ipynb` | Improved Jupyter Notebook that prevents unnecessary leading/trailing whitespace, excludes dosage information from medication names, and correctly separates each medication name from the medication class. |

## Input Data

The analysis examines `1000_generic_medication_names_NHC.txt` (available in the [`exercise_files`](../exercise_files/) working directory), a demonstration plain-text file containing **1,000 generic-medication records**. Each entry follows this general structure:

```text
<Entry number>. <Medication name and dosage> - <Medication class>
```

The table below records its representative first five entries.

| Entry | Medication record |
|---:|---|
| 1 | Acetaminophen Tablet (500 mg) - Analgesic |
| 2 | Ibuprofen Tablet (200 mg) - Nonsteroidal Anti-Inflammatory Drug |
| 3 | Aspirin Tablet (81 mg) - Platelet Aggregation Inhibitor |
| 4 | Naproxen Tablet (250 mg) - Nonsteroidal Anti-Inflammatory Drug |
| 5 | Morphine Tablet (15 mg) - Opioid Analgesic |

## Output Data

The tables below compare the first five records produced both by `05_original_healthcare_data_wrangling.ipynb` (course-based) and `05_healthcare_data_wrangling.ipynb` (improved). Overall, the original output retains medication dosage information and includes leading/trailing whitespace, while the improved output removes dosage information from `med_name` and standardises whitespace in both columns.

### `05_original_healthcare_data_wrangling.ipynb` Output

| med_name | med_class |
|---|---|
| `␠`Acetaminophen Tablet (500 mg)`␠` | `␠`Analgesic |
| `␠`Ibuprofen Tablet (200 mg)`␠` | `␠`Nonsteroidal Anti-Inflammatory Drug` |
| `␠`Aspirin Tablet (81 mg)`␠` | `␠`Platelet Aggregation Inhibitor` |
| `␠`Naproxen Tablet (250 mg)`␠` | `␠`Nonsteroidal Anti-Inflammatory Drug` |
| `␠`Morphine Tablet (15 mg)`␠` | `␠`Opioid Analgesic` |

> The `␠` symbol below represents leading or trailing whitespace retained in the original output.

### `05_healthcare_data_wrangling.ipynb` Output

| med_name | med_class |
|---|---|
| Acetaminophen Tablet | Analgesic |
| Ibuprofen Tablet | Nonsteroidal Anti-Inflammatory Drug |
| Aspirin Tablet | Platelet Aggregation Inhibitor |
| Naproxen Tablet | Nonsteroidal Anti-Inflammatory Drug |
| Morphine Tablet | Opioid Analgesic |

## Analysis and Tools

The workflow 

- Loaded and inspected an unstructured text file containing numbered medication records.
- Used Python string operations and regular expressions to extract medication names and medication classes.
- Converted the parsed records into structured tabular data with **pandas**.
- Exported the course-based output as `med_name_and_class.csv`, which retains dosage information and includes leading and trailing whitespace in selected values.
- Developed an improved workflow that removes leading and trailing whitespace, removes dosage information from medication names, and exports the cleaned result as `med_namenodosage_class.csv`.
- Compared the two outputs to demonstrate the importance of precise text parsing and data-cleaning decisions in healthcare datasets.

**Libraries:** pandas and re.

## Note

This is an educational project completed as part of the LinkedIn Learning course [Python Data Analysis for Healthcare](https://www.linkedin.com/learning/python-data-analysis-for-healthcare/python-data-analysis-in-healthcare), taught by Wuraola Oyewusi. The dataset is a demonstration dataset supplied with the course and is not real patient data.
