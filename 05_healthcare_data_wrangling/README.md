# Healthcare Data Wrangling

This directory documents the preparation process of unstructured medication data for analysis purposes, as demonstrated in the LinkedIn Learning course [Python Data Analysis for Healthcare](https://www.linkedin.com/learning/python-data-analysis-for-healthcare/python-data-analysis-in-healthcare), taught by Wuraola Oyewusi. The workflow converts a plain-text list of generic medication names, dosage information, and medication classes into a structured CSV output.

> ⚠️ **Development Environment** Although course demonstrations used Google Colab, I completed this analysis locally in **Jupyter Notebook**, using a project-specific **`conda`** environment and **Visual Studio Code** for script development. I used this environment to acquire hands-on expertise with tools relevant to future genomics and bioinformatics workflows. Further details about how I set up this development environment are provided below.

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

### Output for `05_original_healthcare_data_wrangling.ipynb`

| med_name | med_class |
|---|---|
| `␠`Acetaminophen Tablet (500 mg)`␠` | `␠`Analgesic |
| `␠`Ibuprofen Tablet (200 mg)`␠` | `␠`Nonsteroidal Anti-Inflammatory Drug` |
| `␠`Aspirin Tablet (81 mg)`␠` | `␠`Platelet Aggregation Inhibitor` |
| `␠`Naproxen Tablet (250 mg)`␠` | `␠`Nonsteroidal Anti-Inflammatory Drug` |
| `␠`Morphine Tablet (15 mg)`␠` | `␠`Opioid Analgesic` |

> The `␠` symbol below represents leading or trailing whitespace retained in the original output.

### Output for `05_healthcare_data_wrangling.ipynb`

| med_name | med_class |
|---|---|
| Acetaminophen Tablet | Analgesic |
| Ibuprofen Tablet | Nonsteroidal Anti-Inflammatory Drug |
| Aspirin Tablet | Platelet Aggregation Inhibitor |
| Naproxen Tablet | Nonsteroidal Anti-Inflammatory Drug |
| Morphine Tablet | Opioid Analgesic |

### Notable Differences

The table below summarizes all 17 normalized discrepancies caused by different hyphen/delimiter handling in the outputs returned by `05_original_healthcare_data_wrangling.ipynb` (`med_name_and_class.csv`) and `05_healthcare_data_wrangling.ipynb` (`med_namenodosage_class.csv`). A `|` symbol separates the two parsed CSV columns (`med_name` | `med_class`).

| #     | `med_name_and_class.csv` normalized parsed row                                                          | `med_namenodosage_class.csv` normalized row                                        | Occurrences / CSV line(s), including header           | Delimiter-handling difference                                                                                                                                                                                                                                    |
| ----- | ----------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | ----------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1–5   | Clotrimazole \| Betamethasone Topical Cream (1/0.05%) - Antifungal/Corticosteroid Combination         | Clotrimazole-Betamethasone Topical Cream \| Antifungal/Corticosteroid Combination | 5 occurrences: lines 163, 339, 509, 705, 901          | The comma/delimiter in the older file splits the hyphenated medication name after Clotrimazole; it also leaves the class joined to the rest of the text. The dosage-free file correctly retains Clotrimazole-Betamethasone Topical Cream as the medication name. |
| 6–10  | Nystatin/Triamcinolone Topical Cream (100,000 units/g \| 0.1%) - Antifungal/Corticosteroid Combination | Nystatin/Triamcinolone Topical Cream \| Antifungal/Corticosteroid Combination    | 5 occurrences: lines 176, 346, 516, 712, 908          | The comma inside the dosage, 100,000 units/g, causes an unintended field split in the older file. The dosage-free file correctly stores the full drug name and its class in separate fields.                                                                     |
| 11–14 | L \| Arginine Tablet (500 mg) - Amino Acid Supplement                                                 | L-Arginine Tablet \| Amino Acid Supplement                                       | 4 corresponding occurrences: lines 269, 439, 609, 805 | The older file treats the hyphen in L-Arginine as a delimiter, splitting the medication name into L and the remaining text. The dosage-free file keeps the hyphenated name intact.                                                                               |
| 15–16 | L \| Arginine Tablet (1,000 mg) - Amino Acid Supplement                                               | L-Arginine Tablet \| Amino Acid Supplement                                       | 2 corresponding occurrences: lines 635, 831           | Same L-Arginine hyphen-splitting problem, with the 1,000 mg formulation. Once dosages are intentionally removed, these normalize to the same L-Arginine Tablet record as the 500 mg rows.                                                                        |
| 17    | No matching row                                                                                       | L-Arginine Tablet \| Amino Acid Supplement                                       | 1 extra occurrence: line 1001                         | This is the extra final L-Arginine Tablet entry in `med_namenodosage_class.csv`; it has no counterpart in `med_name_and_class.csv`, as the workflow in `05_original_healthcare_data_wrangling.ipynb` removes it.                                                                                                                                  |

> When accounting for discrepancies, *normalized* means "after stripping ordinary leading/trailing whitespaces".

## Analysis and Tools

The workflow uses **pandas** to load and inspect the unstructured `1000_generic_medication_names_NHC.txt` file. String operations and regular expressions are tested and used to extract medication names and medication classes. `05_healthcare_data_wrangling.ipynb` also removes leading and trailing whitespace, as well as dosage information from medication names. The parsed records are then converted into structured tabular data, and the output is exported as a CSV file.

## Note

This is an educational project completed as part of the LinkedIn Learning course [Python Data Analysis for Healthcare](https://www.linkedin.com/learning/python-data-analysis-for-healthcare/python-data-analysis-in-healthcare), taught by Wuraola Oyewusi. The dataset is a demonstration dataset supplied with the course and do not contain real patient data.
