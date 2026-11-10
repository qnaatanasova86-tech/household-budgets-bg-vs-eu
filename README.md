# Household Expenditure Structure: Bulgaria vs the EU

Final exam project, Data Science module.

**Author:** _<your name>_
**Date:** November 2026

## Project Goal

This project examines how households in Bulgaria allocate their budgets across the main spending categories (food, housing, transport, health, etc.) and how this profile differs from other EU countries.

## Research Questions

1. How does the structure of household expenditure in Bulgaria differ from that of other countries?
2. How has it changed over time?
3. Which countries are the closest to Bulgaria in terms of their spending profile?

## Data Sources

Planned independent sources (to be finalised when the data is downloaded):

| Source | Dataset | Content |
|---|---|---|
| Eurostat | `hbs_str_t211` | Structure of consumption expenditure (HBS) by COICOP category |
| Eurostat | `nama_10_co3_p3` | Annual household final consumption expenditure by COICOP category |
| NSI (National Statistical Institute of Bulgaria) | Household budgets | Expenditure by income quintile and region for Bulgaria |

Full details for every file (URL, download date, applied filters) will be added in the "Sources and Licences" section.

## Analysis Plan

1. Introduction and problem formulation
2. Data loading
3. Cleaning and validation
4. Merging by country, year and COICOP category
5. Exploratory data analysis (EDA)
6. Bulgaria vs the EU comparison
7. Clustering of countries (K-means, PCA)
8. Regression: food share vs income per capita
9. Conclusions, limitations and next steps
10. References

## Repository Structure

```
.
├── data/
│   ├── raw/          # original downloaded files (never modified)
│   └── processed/    # cleaned and merged data
├── notebooks/        # Jupyter notebook with the analysis
├── src/              # helper scripts
├── README.md
└── requirements.txt
```

## Sources and Licences

_To be completed at the end: table name, URL, download date, licence._
