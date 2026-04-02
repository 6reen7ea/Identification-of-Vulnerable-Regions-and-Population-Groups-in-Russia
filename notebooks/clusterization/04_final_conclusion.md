# Final Project Conclusion

## 1. Project Goal
This project was carried out as part of a thesis assignment for the “Laboratory for Civil Society Research” and aims to identify socio-economic differences across Russian regions, determine the most vulnerable areas and population groups, and uncover factors influencing poverty levels.

## 2. Data and Sources
The analysis is based on data from Rosstat and related sources for 1990–2022 (latest available years for each indicator), covering:
- poverty levels, income, and wages;
- socio-demographic structure (children, elderly, working-age population);
- disability and morbidity indicators;
- birth rates and infant mortality (urban/rural);
- social policy expenditures;
- gross regional product, production, and retail activity;
- addiction indicators (alcoholism, drug use).

The final model used 11 features that were log-transformed and standardized.

## 3. Methods
1. **Preprocessing**:
   - Data cleaning and harmonization of region names.
   - Merging 15 separate tables into a master dataset.
   - Log transformation of highly skewed features.

2. **Clustering**:
   - Algorithms: KMeans and Agglomerative Clustering.
   - Dimensionality reduction (PCA, 2 components) to reduce multicollinearity and improve interpretability.
   - Evaluation metrics: Silhouette Score and Davies–Bouldin Index.

3. **Model Selection**:
   - Final model — Agglomerative Clustering, k=3, excluding the `poverty_percent` feature (to focus on drivers of poverty rather than poverty itself).

4. **Interpretation**:
   - Cluster map visualization and boxplot distributions.
   - Median feature analysis by cluster.
   - Statistical tests (correlations, p-values) to identify relationships.

## 4. Clustering Results
Three stable clusters of regions were identified:

- **Cluster 0 (low-income regions, 12 regions)**  
  Highest poverty level (median 22.75%), low income, GRP, production, and retail per capita.  
  High social spending, high birth rates, high disability rates, and elevated rural infant mortality.  
  Geography: North Caucasus, Kalmykia, Crimea, parts of southern Siberia.

- **Cluster 1 (high-income regions, 12 regions)**  
  Highest income, GRP, production, and retail activity.  
  Low poverty (9.45%), low disability, and low rural infant mortality.  
  However, higher levels of alcohol and drug addiction, and a higher dependency ratio.  
  Geography: Far North, Far East, Moscow and Moscow region.

- **Cluster 2 (middle group, 61 regions)**  
  Intermediate values across most indicators, moderate poverty (13.8%).  
  Geography: central Russia, western regions, and much of Siberia.

## 5. Vulnerable Population Groups
Statistical analysis showed:
- **Disabled individuals (especially ages 51–60)** — strong positive relationship with poverty (r > 0.23, p < 0.0001).
- **Elderly population** — moderate relationship.
- **Children** — indirect relationship, likely culturally driven.
- **Working-age population** — inverse relationship (lower share → higher poverty).

## 6. Relationship Between Poverty and Economic Activity
- Retail per capita: r = –0.735, p < 0.0001  
- Production per capita: r = –0.319, p < 0.0001  

Conclusion: poverty is strongly linked to the level of economic development.

## 7. Additional Findings
- **Rural infant mortality**: 3–4 times higher in poorer regions.  
- **Addiction rates (alcohol, drugs)**: higher in economically developed regions.

## 8. Study Limitations
- Possible methodological changes in Rosstat data over time.
- Inconsistencies in region naming and administrative structure (e.g., Tyumen region vs autonomous okrugs).
- Log transformations may complicate interpretation of absolute values.

## 9. Conclusion
Clustering regions based on socio-economic and demographic characteristics allowed identification of the most vulnerable territories and key factors influencing poverty.  
The results can be used for targeted allocation of social and infrastructure support, as well as for developing regional poverty reduction strategies.

## 10. Practical Applications
The results can be applied:
- for **targeted distribution of social and infrastructure support** across regions;
- in **developing regional programs** to reduce poverty and improve quality of life;
- in **analytical and research work** by government agencies, NGOs, and think tanks;
- for **monitoring policy effectiveness** and tracking socio-economic changes over time.