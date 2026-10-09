# Iris Dataset Analysis & Setup Guide

##  Introduction & Overview (المقدمة)
This project is an end-to-end data analysis workflow performed on the classic Iris Dataset. The project demonstrates setting up a modern, isolated Python environment using `uv`, loading and cleaning structured data, performing exploratory data analysis (EDA), generating data visualizations, and exporting processed subsets for downstream tasks.

---

##  Project Purpose & Value (الفائدة من المشروع)
- Environment & Dependency Management: Practicing modern Python project initialization and reproducible environment management using `uv`.
  
- Data Manipulation & Analysis: Gaining hands-on experience with `pandas` for querying, filtering, grouping, and calculating summary statistics.
  
- Data Visualization: Leveraging `matplotlib` alongside `pandas` plotting tools to visually analyze species feature distributions and comparative metrics.
  
- Data Pipeline Operations: Exporting filtered subsets and structured statistical summaries back to CSV format

---

## Tasks Breakdown & Tools Used (تفصيل التاسكات والأدوات)

### Task 1: Python Environment Setup using `uv`
- Goal:Initialize an isolated Python environment and manage dependencies.
  
- Tools Used: `uv`

  
- Commands & Actions:
  - Initialized project: `uv init iris-analysis`
  - Created virtual environment: `uv venv`
  - Installed dependencies: `uv add pandas notebook matplotlib`
  - Launched environment: `uv run jupyter notebook`

### Task 2: Dataset Acquisition
- Goal: Download the raw Iris CSV dataset directly into the project repository.
 
- Tools Used: PowerShell (`Invoke-WebRequest`)
  
- Actions: Saved the raw CSV file inside the `data/` folder as `data/iris.csv`.

### Task 3: Loading & Initial Data Inspection
- Goal: Load the dataset and inspect its structure, dimensions, and schema.
  
- Tools Used: `pandas` (`pd.read_csv`, `head()`, `tail()`, `shape`, `dtypes`)
  
- Actions: Loaded the CSV file into a Pandas DataFrame `df` and inspected the first/last 5 rows, dataset shape (150 rows, 5 columns), column names, and data types.

### Task 4: Exploratory Data Analysis (EDA)
- Goal: Answer core statistical and analytical questions about the data.
  
- Tools Used: `pandas` (`isnull()`, `duplicated()`, `nunique()`, `value_counts()`, `mean()`, `max()`, `min()`, `groupby()`, `describe()`)
  
- Actions: Verified data integrity (0 missing values), identified duplicate records, counted species distributions, calculated feature range metrics, and generated descriptive statistics grouped by species.

### Task 5: Data Filtering & Feature Sorting
- Goal: Query specific conditions and rank records.

- Tools Used: `pandas` (Boolean Indexing, `idxmax()`, `sort_values()`)

    
- Actions: Filtered records where `sepal_length > 6`, `petal_width > 1.5`, isolated the `setosa` species, and sorted flowers by sepal length in descending order.

### Data Visualization Section (Pandas & Matplotlib)
- Goal: Graphically compare feature averages across species using official Pandas plotting standards.
  
- Tools Used: `pandas` (`.plot(kind='bar')`), `matplotlib.pyplot` (`plt.title()`, `plt.xlabel()`, `plt.ylabel()`, `plt.show()`)
  
- Actions: Utilized `matplotlib` to render and customize a bar chart showing average measurements for each Iris species.

### Task 6: Exporting Analysis Results
- Goal: Persist key findings and filtered subsets to external CSV files.
  
- Tools Used: `pandas` (`to_csv()`), `os`
  
- Actions: Created an `output/` directory and exported `species_summary.csv` and `filtered_iris.csv`

---

##  Directory Structure
```text
iris-analysis/
├── data/
│   └── iris.csv
├── output/
│   ├── species_summary.csv
│   └── filtered_iris.csv
├── iris_analysis.ipynb
├── pyproject.toml
├── uv.lock
└── README.md
---

## How to Run the Project
1. Navigate to the project directory:
   powershell
   cd iris-analysis