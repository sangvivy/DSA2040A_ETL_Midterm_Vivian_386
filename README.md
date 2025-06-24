# DSA2040A_ETL_Midterm_Vivian_386

This project demonstrates a complete **Extract, Transform, Load (ETL)** process using a mock dataset. It simulates a real-world scenario where data is ingested incrementally, transformed for analytical use, and stored in a structured format using SQLite.

##  Author
**Name:** Vivian  
**Student ID:** 386

---

## Project Folder Structure

ETL_Midterm_Vivian_386/
├── data/
│ ├── raw_data.csv
│ └── incremental_data.csv
├── transformed/
│ ├── transformed_full.csv
│ └── transformed_incremental.csv
├── loaded/
│ ├── full_data.db
├── etl_extract.ipynb
├── etl_transform.ipynb
├── etl_load.ipynb
├── README.md
└── .gitignore


---

## Technologies Used

- Python (v3.8+)
- Pandas
- SQLite3
- Jupyter Notebooks
- OS module for path management

---

##  ETL Pipeline Overview

### 1. Extract (`etl_extract.ipynb`)
- Loads `raw_data.csv` and `incremental_data.csv`.
- Displays `.head()` and `.info()` of each.
- Notes on structure, missing values, and potential keys.
- Saves original copies to the `data/` folder.

### 2. Transform (`etl_transform.ipynb`)
Applies the following transformations:

| Transformation Type | Description |
|---------------------|-------------|
| Cleaning            | Removed duplicates and rows with missing key data |
| Enrichment          | Added `total_price = quantity * unit_price` |
| Structural          | Converted `signup_date` to `datetime` |
| Categorization      | Created `age_group` column (e.g., Teen, Adult, Senior) |

- Outputs are saved to `transformed/` as:
  - `transformed_full.csv`
  - `transformed_incremental.csv`

### 3. Load (`etl_load.ipynb`)
- Loads the transformed CSVs.
- Inserts them into `full_data.db` SQLite database:
  - `full_data` table
  - `incremental_data` table
- Verifies the tables with SQL queries and previews 5 rows from each.

---

## Sample Output

**Preview of `full_data` table:**

| user_id | quantity | unit_price | total_price | age | age_group |
|---------|----------|------------|-------------|-----|-----------|
| 101     | 2        | 150        | 300         | 23  | Adult     |
| 102     | 1        | 400        | 400         | 19  | Teen      |

---

##  How to Run

1. Clone the repository or download the folder.
2. Ensure the following packages are installed:
   ```bash
   pip install pandas jupyter
   jupyter notebook

## Open and run each notebook in order:

- etl_extract.ipynb

- etl_transform.ipynb

- etl_load.ipynb


