# QM640 GES Capstone

## Project Title

Data-Driven Analysis and Predictive Modeling of Graduate Employment and Salary Outcomes in Singapore

## Author

Kumaran Sundaram  
Walsh College  
QM640: Data Analytics Capstone  
Mentor: Prof. Sharath Srivatsa  
Term 3, 2026

## Project Overview

This repository supports the QM640 Data Analytics Capstone project titled **Data-Driven Analysis and Predictive Modeling of Graduate Employment and Salary Outcomes in Singapore**.

The project analyzes Singapore graduate employment and salary outcomes using the official Graduate Employment Survey dataset published by the Ministry of Education through data.gov.sg. The study examines graduate outcomes at the programme level and focuses on employment rates, full-time permanent employment, salary indicators, salary spread, stability, and programme-level trends.

The project follows a complete data analytics flow:

1. Descriptive analytics to understand employment and salary trends over time.
2. Diagnostic analytics to test differences across universities and degree programmes.
3. Regression and feature-importance analysis to identify key drivers of salary and career value.
4. Machine learning classification to predict high-employment, high-salary, and high-career-value programmes.
5. Clustering and segmentation to group degree programmes into meaningful employability-salary profiles.

## Problem Statement

Graduate outcome data is often interpreted using isolated indicators such as median salary or overall employment rate. However, graduate career outcomes are multidimensional. A degree programme may have high overall employment but lower full-time permanent employment, or high median salary but wider salary spread or higher year-to-year volatility.

This project addresses that gap by developing a data-driven decision-support framework that jointly analyzes employment, salary, stability, prediction, and segmentation using official Singapore programme-level graduate outcome data.

## Data Source

The primary dataset is:

**Graduate Employment Survey - NTU, NUS, SIT, SMU, SUSS & SUTD**  
Publisher: Ministry of Education, Singapore  
Source: data.gov.sg  
Dataset URL: https://data.gov.sg/datasets/d_3c55210de27fcccda2ed0c63fdd2b352/view

The dataset contains programme-level graduate employment and salary outcomes for Singapore autonomous universities. The downloaded CSV contains 1,550 programme-year observations before cleaning and 12 columns.

## Important Note About the Dataset

The source dataset is provided by the Ministry of Education through data.gov.sg. The dataset is made available under the terms of the Singapore Open Data Licence version 1.0.

The MIT License in this repository applies only to the analysis code, notebooks, and original project materials created for this capstone. It does not replace or override the licence terms of the original dataset.

Users should refer to the original data.gov.sg dataset page and the Singapore Open Data Licence for the permitted use of the dataset.

## Attribution Statement

Contains information from the **Graduate Employment Survey - NTU, NUS, SIT, SMU, SUSS & SUTD** dataset accessed from data.gov.sg, which is made available under the terms of the Singapore Open Data Licence version 1.0.

Dataset source:  
https://data.gov.sg/datasets/d_3c55210de27fcccda2ed0c63fdd2b352/view

Licence source:  
https://data.gov.sg/open-data-licence

## Research Questions

### RQ1
How have employment and salary outcomes evolved across Singapore university degree programmes from 2013 to 2025?

### RQ2
Do employment and salary outcomes differ significantly across universities and degree programmes?

### RQ3
Which factors contribute most to graduate salary outcomes and graduate career value across Singapore university programmes?

### RQ4
Can machine learning models accurately predict high-employment, high-salary, and high-career-value degree programmes?

### RQ5
Can degree programmes be segmented into meaningful employability-salary profiles to support student, university, and policy decision-making?

## Planned Analytical Approach

- Data cleaning and feature engineering
- Descriptive statistics and trend analysis
- ANOVA and Kruskal-Wallis tests
- Correlation and multiple linear regression
- Graduate Career Value Index construction
- Logistic regression, decision tree, and random forest classification
- K-means clustering, hierarchical clustering, and PCA visualization
- Dashboard-style visual summaries

## Graduate Career Value Index

The Graduate Career Value Index, or GCVI, is a constructed decision-support measure that combines employment, full-time permanent employment, salary, and stability indicators.

A starting formulation is:

```text
GCVI = 0.30(Overall Employment Score)
     + 0.30(Full-Time Permanent Employment Score)
     + 0.25(Median Salary Score)
     + 0.15(Stability Score)
```

All components will be normalized before aggregation. Sensitivity analysis will be used to test whether results are stable under alternative weighting schemes. Principal Component Analysis may also be explored as a data-driven comparison.

The GCVI is not intended to be a definitive ranking of programme quality. It is used as a structured decision-support measure for comparing multidimensional graduate outcomes.

## Repository Structure

```text
QM640_GES_Capstone/
├── data/
│   ├── raw/
│   │   └── graduate_employment_survey.csv
│   └── processed/
│       └── ges_cleaned.csv
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   ├── 02_eda_trends.ipynb
│   ├── 03_statistical_tests.ipynb
│   ├── 04_regression_and_gcvi.ipynb
│   ├── 05_machine_learning.ipynb
│   └── 06_clustering.ipynb
├── outputs/
│   ├── figures/
│   └── tables/
├── dashboard/
├── README.md
├── requirements.txt
└── LICENSE
```

## Main Dataset Fields

The main fields include:

- `year`
- `university`
- `school`
- `degree`
- `employment_rate_overall`
- `employment_rate_ft_perm`
- `basic_monthly_mean`
- `basic_monthly_median`
- `gross_monthly_mean`
- `gross_monthly_median`
- `gross_mthly_25_percentile`
- `gross_mthly_75_percentile`

Additional derived fields may include:

- `salary_iqr`
- `salary_premium`
- `employment_premium`
- `stability_score`
- `career_value_index`
- `high_employment`
- `high_salary`
- `high_career_value`

## Tools and Libraries

Python, Jupyter Notebook, pandas, NumPy, matplotlib, scikit-learn, scipy, statsmodels, and openpyxl.

## Reproducibility

The repository is organized to support reproducibility. Raw data will be stored separately from processed data. Analysis notebooks will be numbered in the expected workflow order. Output figures and tables will be stored separately to allow easy review and reuse in the final report or presentation.

## Limitations

This project uses aggregated programme-level data. It does not contain individual student-level information such as grades, internships, socioeconomic background, job-search effort, or personal skills. Therefore, the results should not be interpreted as predicting individual student employability.

The findings will be interpreted only at the programme level.

## License and Dataset Attribution

**Copyright (c) 2026 Kumaran Sundaram.**

The analysis code, notebooks, figures, and original project documentation in this repository are licensed under the MIT License.

The source dataset is provided by the Ministry of Education through data.gov.sg and is subject to the Singapore Open Data Licence version 1.0. The dataset licence remains governed by data.gov.sg and is not replaced by the MIT License used for this repository.

Contains information from the Graduate Employment Survey - NTU, NUS, SIT, SMU, SUSS & SUTD dataset accessed from data.gov.sg, which is made available under the terms of the Singapore Open Data Licence version 1.0.
