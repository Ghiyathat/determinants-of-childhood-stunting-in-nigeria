# Determinants of Childhood Stunting in Nigeria: A Population-Based Secondary Analysis (MICS Simulation Cohort)

## Short Description
An end-to-end biostatistical public health study investigating the socioeconomic, maternal healthcare, and environmental determinants of linear growth faltering (stunting) among 2,870 under-five children in Nigeria using simulated UNICEF Multiple Indicator Cluster Survey (MICS6) data. Features survey weighting, cluster-robust multivariable logistic regression, and publication-ready visualizations.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Research Objectives](#research-objectives)
3. [Dataset Architecture](#dataset-architecture)
4. [Statistical Methodology](#statistical-methodology)
5. [Key Empirical Findings](#key-empirical-findings)
6. [Repository Structure](#repository-structure)
7. [Installation & Reproduction](#installation--reproduction)
8. [Public Health Implications](#public-health-implications)
9. [Citation & Author](#citation--author)

## Project Overview
Childhood stunting (height-for-age z-score HAZ < -2 SD) represents chronic, cumulative nutritional deprivation and repeated infectious insults during the critical first 1,000 days of life. Nigeria carries one of the world's highest pediatric undernutrition burdens. This capstone project deploys an open, reproducible computational epidemiology pipeline in Python to examine the relative contribution of distal structural factors versus proximal clinical and environmental conditions.

## Research Objectives
* Quantify Prevalence: Estimate national and regional prevalence of stunting across geopolitical zones and settlement types.
* Bivariable Association Screening: Assess candidate predictors via Pearson's Chi-square (chi2) tests of independence.
* Multivariable Modeling: Identify independent predictors of stunting using binary multivariable logistic regression adjusted for primary sampling unit (HH1) cluster effects, reporting Adjusted Odds Ratios (aOR) and 95% Confidence Intervals.

## Dataset Architecture
* Source: Simulated extract modeled on the UNICEF MICS6 Under-Five Child (ch) Questionnaire.
* Sample Size: N = 2,870 complete anthropometric records (110 missing values excluded).
* Sampling Design: Stratified two-stage cluster survey across 200 primary sampling units in Nigeria's 6 geopolitical zones, weighted using normalized child weights (chweight).

## Statistical Methodology
* Data Wrangling: Automated variable mapping, missing data filtering, and category standardization using pandas and numpy.
* Inferential Statistics: Pearson's chi2 hypothesis testing with scipy.stats.
* Econometric/Epidemiological Modeling: Binary logit regression with empirical cluster-robust covariance estimation via statsmodels.
* Data Visualization: High-resolution forest plots (log scale) and APA-formatted summary tables rendered via matplotlib.

## Key Empirical Findings
* Epidemiological Burden: The national stunting prevalence is 33.5% unweighted (33.7% survey-weighted), surpassing the WHO critical threshold (30%).
* Socioeconomic Monopoly: Household poverty is the single strongest predictor. Children in the poorest quintile face a 7-fold increase in stunting odds (aOR = 7.08, 95% CI: 3.75-13.37, p < 0.001) relative to the richest quintile.
* Protective Role of Female Education: Children of mothers without formal education have nearly 5 times higher odds of stunting (aOR = 4.94, 95% CI: 2.82-8.64, p < 0.001) compared to mothers with higher education.
* Cumulative Vulnerability: Stunting risk peaks among children aged 48-59 months (aOR = 1.68, 95% CI: 1.29-2.21), highlighting cumulative nutritional deficits post-weaning.
* Covariate Attenuation: Geographic zone, rural residence, antenatal care attendance, and unimproved WASH indicators were attenuated to statistical non-significance in the multivariable model, demonstrating they function as downstream proxies of poverty and educational deprivation.

## Repository Structure
```
├── data/
│   ├── MIVA_PHS410_DS1_MICS_Extract_SIMULATED.csv
├── outputs/
│   ├── table1_baseline_characteristics.png
│   ├── table2_bivariate_analysis.png
│   ├── table3_multivariable_logistic_regression.png
│   ├── forest_plot_stunting.png
├── scripts/
│   ├── analysis_pipeline.py
├── docs/
│   ├── Capstone_Manuscript.docx
├── README.md
├── requirements.txt
└── LICENSE
```

## Installation & Reproduction
```bash
# Clone the repository
git clone https://github.com/your-username/mics-childhood-stunting-nigeria.git
cd mics-childhood-stunting-nigeria

# Install required dependencies
pip install -r requirements.txt

# Run the complete analytical pipeline
python scripts/analysis_pipeline.py
```

## Public Health Implications
1. Multi-Sectoral Social Safety Nets: Standalone clinical interventions (micronutrient supplementation, deworming) must be integrated with targeted cash transfers and social protections for the lowest two wealth quintiles.
2. Female Education Investment: Universal secondary education for girls serves as a high-leverage intergenerational public health strategy.
3. Targeted Complementary Feeding: Public health nutrition programs must concentrate counseling and dietary diversity support during the 6-24 month window.

## Author & Academic Affiliation
* Public Health Capstone Research Project
* Department of Public Health Science, MIVA Open University
* Simulated Secondary Survey Analysis
