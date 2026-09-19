# Healthcare Data Wrangling

This project demonstrates the preparation of unstructured medication data for analysis. It converts a plain-text list of generic medication names, dosage information, and medication classes into structured CSV output.

The folder includes both the course-based implementation and an improved version. The improved workflow removes leading and trailing whitespace and correctly separates each medication name, without dosage information, from its medication class.

## Environment

The analysis was developed locally with Python, Anaconda, Visual Studio Code, and Jupyter Notebook.

## Contents

| File | Description |
|---|---|
| `05_original_healthcare_data_wrangling.ipynb` | Course-based notebook that parses the source text file and generates `med_name_and_class.csv`. |
| `05_healthcare_data_wrangling.ipynb` | Improved notebook that removes unnecessary whitespace, excludes dosage information from medication names, and generates `med_namenodosage_class.csv`. |

## Input Data

Both notebooks use `1000_generic_medication_names_NHC.txt`, a course-provided plain-text file containing 1,000 numbered generic-medication records.

Each entry follows this general structure:

```text
<Entry number>. <Medication name and dosage> - <Medication class>
```

The table below displays the first five entries in the source file:

| Entry | Medication record |
|---:|---|
| 1 | Acetaminophen Tablet (500 mg) - Analgesic |
| 2 | Ibuprofen Tablet (200 mg) - Nonsteroidal Anti-Inflammatory Drug |
| 3 | Aspirin Tablet (81 mg) - Platelet Aggregation Inhibitor |
| 4 | Naproxen Tablet (250 mg) - Nonsteroidal Anti-Inflammatory Drug |
| 5 | Morphine Tablet (15 mg) - Opioid Analgesic |

## Analysis and Tools

- Loaded and inspected an unstructured text file containing numbered medication records.
- Used Python string operations and regular expressions to extract medication names and medication classes.
- Converted the parsed records into structured tabular data with **pandas**.
- Exported the course-based output as `med_name_and_class.csv`, which retains dosage information and includes leading and trailing whitespace in selected values.
- Developed an improved workflow that removes leading and trailing whitespace, removes dosage information from medication names, and exports the cleaned result as `med_namenodosage_class.csv`.
- Compared the two outputs to demonstrate the importance of precise text parsing and data-cleaning decisions in healthcare datasets.

**Libraries:** pandas and re.

> **Note:** This is an educational project completed as part of the *Python Data Analysis for Healthcare* course by Wuraola Oyewusi on LinkedIn Learning. The source file contains demonstration medication data and does not include patient-level information.
