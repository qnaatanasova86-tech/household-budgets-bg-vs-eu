# Household Expenditure Structure: Bulgaria vs European Countries

Final exam project, Data Science module.

**Author:** Yana Atanasova  
**Date:** November 2026

## Project Goal

This project examines how households in Bulgaria allocate their budgets across the 12 main COICOP spending categories (food, housing, transport, health, etc.) and how this profile differs from that of other European countries.

## Research Questions

1. How does the structure of household spending in Bulgaria differ from that of other countries?
2. How has it changed over time?
3. Which countries are closest to Bulgaria in their spending profile?
4. Does Engel's law hold across countries, and how does Bulgaria compare with the relationship?

## Data Sources

| Source | Dataset | Content |
|---|---|---|
| Eurostat, Household Budget Survey | `hbs_str_t211` | Structure of consumption expenditure by COICOP category (per mille) |
| World Bank, World Development Indicators | `NY.GDP.PCAP.PP.KD` | GDP per capita, PPP (constant 2021 international $) |

The main analysis uses the survey waves 2005, 2010, 2015 and 2020. Imputed rent is removed from both housing and total expenditure to make the countries more comparable. Details on the raw files are in [`data/raw/README.md`](data/raw/README.md).

## Methods

- Data cleaning, validation and merging by country and year
- Exploratory data analysis
- Euclidean distance between spending profiles
- K-means clustering and PCA
- OLS regression (semi-log and log-log) with standard errors clustered by country

## Main Results

- Bulgaria's food share (excluding imputed rent) fell from 40.3% in 2005 to 31.4% in 2020.
- In 2020 it was the third-highest of the 28 countries in the sample, behind Montenegro and Serbia. Romania and Portugal are not in the 2020 sample because imputed rent is not available for them.
- By Euclidean distance of the spending shares, the countries closest to Bulgaria in 2020 were Lithuania, Serbia and Poland.
- The food share falls as GDP per capita rises, consistent with Engel's law (elasticity -0.71 in the log-log model).
- Bulgaria's food share is above the model prediction in all four waves.

These results describe country-level associations, not causal effects.

## Repository Structure

```
.
├── data/
│   ├── raw/          # original downloaded files (never modified)
│   └── processed/    # cleaned and merged data
├── notebooks/
│   └── household_budgets_analysis.ipynb
├── README.md
└── requirements.txt
```

## How to Run

The notebook was created with Python 3.13. From the repository root:

```bash
pip install -r requirements.txt
jupyter notebook notebooks/household_budgets_analysis.ipynb
```

Then choose **Restart Kernel and Run All Cells**. The files in `data/processed/` are recreated by the notebook.

## Sources and Licences

- Eurostat, [`hbs_str_t211`](https://ec.europa.eu/eurostat/databrowser/view/hbs_str_t211/default/table), downloaded 15 November 2026. Licence: CC BY 4.0 (Eurostat reuse policy).
- World Bank, World Development Indicators, [`NY.GDP.PCAP.PP.KD`](https://data.worldbank.org/indicator/NY.GDP.PCAP.PP.KD), downloaded 24 November 2026. Licence: CC BY 4.0.
