# Semiconductor Yield Analysis

This project analyzes a semiconductor manufacturing dataset to
characterize process behavior, investigate yield variation, identify
potential yield limiters, and detect unusual lot-level excursions. The dataset can be found on Kaggle: https://www.kaggle.com/datasets/ayyappanmarimuthu/semiconductor-yield 

## Project Structure

``` text
semiconductor-yield-analysis/
├── data/
│   └── semiconductor_data.csv
├── notebooks/
│   ├── data_inspection.ipynb
│   ├── process_characterization.ipynb
│   └── yield_engineering.ipynb
├── .gitignore
└── README.md
```

## Analysis Workflow

### 1. Data Inspection

-   Validated dataset structure and data quality
-   Examined missing values, duplicates, and variable cardinality
-   Identified the manufacturing hierarchy of wafers nested within lots
-   Distinguished lot-level factors from wafer-level measurements

### 2. Process Characterization

-   Characterized lithography, etch, deposition, implantation,
    metrology, defect, and electrical variables
-   Examined process distributions and variability
-   Evaluated differences across technology nodes
-   Screened for unusual process observations

### 3. Yield Engineering

-   Characterized wafer- and lot-level yield performance
-   Evaluated technology node, product, and equipment associations with
    yield
-   Used lot-level ANOVA to respect the hierarchical sampling structure
-   Investigated wafer-level yield limiters using regression and
    cluster-robust inference
-   Identified defect density as the most consistent measured
    yield-limiter candidate
-   Investigated upstream process associations with defect density
-   Performed robust lot-level excursion analysis

## Key Findings

Technology node was the strongest measured lot-level factor associated
with yield.

Defect density showed the most consistent negative association with
yield across technology nodes. Threshold voltage and critical dimension
were also associated with yield in some nodes, but their relationships
were less consistent.

The measured process variables explained only a limited portion of
defect-density variation, preventing a definitive upstream root cause
from being established.

Two unusual low-yield 28 nm lots were identified. One lot showed
unusually high focus offset together with unusually high defect density,
providing a plausible process investigation lead. The other low-yield
excursion could not be explained by the measured variables.

## Limitations

The dataset is observational and does not support causal conclusions.

Additional manufacturing information---such as equipment history,
chamber and recipe context, maintenance records, wafer position, defect
classification and spatial maps, and controlled experiments---would be
required for stronger root-cause analysis and actionable process-control
development.

## Tools

-   Python
-   pandas
-   NumPy
-   Matplotlib
-   SciPy
-   statsmodels
-   Jupyter Notebook
