# Identifying Vulnerable Regions and Population Groups in Russia

## Project Overview

This project was developed as part of a research initiative by the *Civil Society Research Laboratory*. Its goal is to identify the most vulnerable regions of Russia in terms of poverty and broader socio-economic conditions.

To achieve this, multiple datasets from **Rosstat (1990–2022)** were combined, covering:

* income and wages
* demographics
* healthcare indicators
* production and retail activity
* social factors

Using clustering techniques, regions were grouped into three distinct socio-economic clusters:

* **Low-income regions** (North Caucasus, Kalmykia, Crimea, parts of Southern Siberia):
  characterized by high poverty rates, higher disability levels, and low economic activity.

* **High-income regions** (Far North, Far East, Moscow and Moscow Oblast):
  high income and economic activity, low poverty, but higher dependency-related indicators.

* **Middle group**:
  regions with moderate values across most indicators.

 Full final conclusion:
[`notebooks/clusterization/04_final_conclusion.md`](notebooks/clusterization/04_final_conclusion.md)

---

## Objectives

The main objective of this project is to identify socio-economic clusters of Russian regions and highlight population groups most affected by poverty.

Key tasks include:

1. Cluster regions based on socio-economic and demographic features
2. Identify regions most in need of support
3. Analyze vulnerable population groups and their relationship with poverty
4. Explore the relationship between poverty and economic activity (production & consumption)
5. Identify additional patterns associated with social inequality

---

## Data

The analysis is based on official statistics from **Rosstat** and related sources.

**Categories of data:**

* **Economic indicators:** income, wages, GRP, production, retail turnover
* **Demographics:** population size and structure, birth rate, infant mortality (urban/rural)
* **Social factors:** social spending, disability rates, alcohol and drug-related statistics

Time coverage: **1990–2022**
For modeling, the most recent available values were used for each feature.

---

## Methodology

* Merged **15 cleaned datasets** into a master dataset (2015–2020)
* Applied **log transformation** and **standardization** for skewed features
* Compared clustering methods: **KMeans vs. Agglomerative Clustering**
* Selected optimal number of clusters (k)
* Applied **PCA** to improve interpretability and reduce multicollinearity
* Evaluated models using:

  * Silhouette Score
  * Davies–Bouldin Index

**Interpretation tools:**

* Interactive cluster map (Folium)
* Boxplots and feature distributions
* Median comparison tables
* Statistical tests

---

## Key Findings

* **Cluster 0 (Low-income, ~12 regions):**
  low income, low GRP, low retail activity, high social spending, high birth rate, high disability, and high rural infant mortality

* **Cluster 1 (High-income, ~12 regions):**
  highest income, GRP, and retail activity; low poverty and rural infant mortality
  however, higher dependency ratios and addiction-related indicators

* **Cluster 2 (Middle group, ~61 regions):**
  intermediate values across most features

### Relationships

* Poverty is **negatively correlated** with economic activity (production & retail per capita)
* Poverty is **positively associated** with:

  * disability rates
  * dependency ratio

---

## Repository Structure

```
├── data/
│   ├── raw/
│   ├── clean/
│   └── geo/
├── notebooks/
│   ├── preprocessing/
│   ├── EDA/
│   ├── clusterization/
├── outputs/
├── README.md
└── requirements.txt
```

---

## How to Run

```bash
pip install -r requirements.txt
jupyter lab
```

Run notebooks in order:

`clusterization/01 → 02 → 03`
Final conclusions: `04_final_conclusion.md`

---

## Workflow

1. Data preprocessing
2. Exploratory Data Analysis (EDA)
3. Master dataset creation
4. Statistical testing
5. Clustering and interpretation

---

## Limitations

* Data consistency issues across years (Rosstat methodology changes)
* Regional naming inconsistencies
* Log transformations may affect interpretability
* Results describe **associations**, not causal relationships

---

## Data Sources

Primary sources include Rosstat and related public databases:

* Poverty rates
* Income & wages
* GRP per capita
* Production & retail
* Social spending
* Population statistics
* Infant mortality
* Disability statistics
* Alcohol & drug-related indicators

(See full links in original dataset section)

---

## Author

**Khamzat Dudaev**

