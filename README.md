# survival-collaborate

**Collaborators:** Sean Carver (PhD, Applied Mathematics, Cornell) and Moussa Doumbia

*Completed in 2019 while attending the Flatiron School Data Science program, during a transition from academic research into applied data science.*

---

## Project Summary

This project investigates whether the causes of death in the United States shifted significantly during the Great Recession. Using CDC mortality data covering all US death records from 2005–2015, we compare the proportional distribution of causes of death between 2006 (a pre-recession boom year) and 2009 (the recession trough), across more than 2,000 cause-of-death codes.

The project demonstrates an end-to-end data pipeline: ingesting and trimming large-scale public health data, ETL processing into analysis-ready datasets, rigorous statistical testing with multiple-comparison correction, and publication-quality visualization of results.

---

## Skills and Tools Demonstrated

- **Data wrangling at scale:** Multi-step ETL pipeline in Jupyter/Python (pandas) to trim, transform, and combine large CDC mortality files that exceed memory limits if processed naively
- **Statistical rigor:** Binomial model, two-sample z-test for proportions, Bonferroni correction across 2,000+ simultaneous comparisons, Cohen's h effect-size ranking
- **Data quality:** Consistency checks (`explore_consistency.ipynb`), data validation notebooks, and intermediate serialized outputs (`.savepkl`) to ensure pipeline reproducibility
- **Visualization:** Slope graphs for top causes; violin plots of p-value distributions to assess significance patterns vs. a null uniform distribution
- **Collaboration:** Two-contributor repo with 54 commits and structured folder organization (etl / analysis / fig)
- **Languages / tools:** Python, pandas, Jupyter Notebook, pickle serialization, CDC public data (via Kaggle)

---

## Key Findings

- Identified **104 cause-of-death categories** where the proportion of deaths was significantly higher in 2009 than in 2006 (Bonferroni-corrected alpha = 0.0001, two-sided).
- Results were ranked by **Cohen's h** (effect size for proportions) to prioritize practically meaningful differences over purely statistically significant ones.
- Violin plots of raw p-values confirmed the necessity of multiple-comparison correction, illustrating how many false positives would arise without it.

---

## Repository Structure

```
survival-collaborate/
├── etl/                           # Data ingestion, trimming, and transformation
│   ├── trim2006.ipynb             # Trim raw 2006 mortality file to manageable size
│   ├── trim2009.ipynb             # Trim raw 2009 mortality file
│   ├── etl2006.ipynb              # ETL: extract and encode 2006 cause-of-death data
│   ├── etl2009.ipynb              # ETL: extract and encode 2009 cause-of-death data
│   ├── combine.ipynb              # Merge 2006 and 2009 into unified analysis dataset
│   ├── explore_consistency.ipynb  # Data quality and consistency checks
│   ├── explore_csv.ipynb          # Exploratory CSV inspection
│   ├── k6.savepkl                 # Serialized 2006 dataset (provided)
│   └── k9.savepkl                 # Serialized 2009 dataset (provided)
├── analysis/
│   └── calc_pvalues.ipynb         # Hypothesis testing, effect sizes, visualization
├── fig/                           # Output figures
└── README.md
```

---

## Data

**Source:** CDC Mortality Data, "Death in the United States" (2005–2015), obtained via [Kaggle](https://www.kaggle.com/cdc/mortality/downloads/mortality.zip/2).  
The dataset contains all US death records with identifying information redacted.  
**Years used:** 2006 (n ≈ 300M population, boom year) and 2009 (n ≈ 300M, recession year).

> **Note:** Raw data files are too large for GitHub. Download and extract `mortality.zip` into `./data/` before running the ETL notebooks.

---

## How to Reproduce

**Step 1 — Download data**
```bash
# Download from Kaggle (requires free Kaggle account):
# https://www.kaggle.com/cdc/mortality/downloads/mortality.zip/2
# Extract into ./data/
```

**Step 2 — Run ETL** (in order, closing each notebook before opening the next to manage memory)
```
etl/trim2006.ipynb
etl/trim2009.ipynb
etl/etl2006.ipynb
etl/etl2009.ipynb
etl/combine.ipynb        <- optional; pre-built outputs k6.savepkl / k9.savepkl are provided
```

**Step 3 — Run analysis**
```
analysis/calc_pvalues.ipynb
```

---

## Presentation

A project presentation is available here:  
[https://prezi.com/view/fL4qT4fdPz2KdBWE1euK/](https://prezi.com/view/fL4qT4fdPz2KdBWE1euK/)
