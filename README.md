# Data-Driven Inventory Optimization

Course project for **Probability and Inference (PI Game 2025)** at **VU Amsterdam**, focused on solving a real-world **newsvendor / inventory optimization** problem for a bakery chain in Vilnius, Lithuania. The project combines **statistical modeling, Monte Carlo simulation, bootstrap inference, and demand analysis** to recommend optimal production quantities under uncertain demand. :contentReference[oaicite:0]{index=0}

## Project Overview

This project studies how a bakery chain can determine the **optimal quantity of traditional dessert to produce** when demand is uncertain, surplus products are sold at a lower clearance price, and additional shipping costs apply to unsold inventory. The business objective is to reduce waste, improve operational efficiency, and protect profitability across different store locations. :contentReference[oaicite:1]{index=1} :contentReference[oaicite:2]{index=2}

The analysis covers both **theoretical** and **empirical** parts of the newsvendor problem:

- extending the profit function to include **clearance price** and **shipping cost**
- comparing **parametric vs. non-parametric quantile estimators**
- evaluating estimator performance through **Monte Carlo simulation**
- estimating **store-specific optimal order quantities**
- analyzing pricing strategy under a projected **25% cost increase**
- exploring a **Markov chain extension** for non-i.i.d. demand in the bonus task :contentReference[oaicite:3]{index=3} :contentReference[oaicite:4]{index=4} :contentReference[oaicite:5]{index=5}

## Business Problem

The bakery sells perishable traditional Lithuanian desserts across **4 stores** with different demand patterns. Two stores were affected by COVID-related structural demand shifts, while the others opened later and show more stable behavior. Because demand varies by location and weekday/weekend pattern, a single inventory rule is not appropriate. The goal is to estimate **location-specific and day-specific order quantities** that maximize expected profit under uncertainty. :contentReference[oaicite:6]{index=6} :contentReference[oaicite:7]{index=7}

## Data

The empirical analysis uses daily bakery demand data from **11 May 2016 to 28 May 2025** for **4 store locations** in Vilnius. Demand is measured in **0.25 kg units**. The report identifies meaningful structural patterns such as:

- COVID-related demand troughs for **Main Street A** and **Station A**
- distinct **weekday/weekend** demand regimes
- multimodal demand distributions at some locations
- a “slow start” period for **Main Street A**, which was removed before fitting distributions :contentReference[oaicite:8]{index=8} :contentReference[oaicite:9]{index=9}

## Methods

### Inventory / statistical methods
- Newsvendor model
- Parametric quantile estimation
- Non-parametric quantile estimation
- Maximum likelihood estimation
- Bootstrap confidence intervals
- Sensitivity analysis
- Monte Carlo simulation
- Goodness-of-fit testing :contentReference[oaicite:10]{index=10} :contentReference[oaicite:11]{index=11}

### Statistical tests
- Jarque-Bera
- Shapiro-Wilk
- Lilliefors
- Cramér-von Mises :contentReference[oaicite:12]{index=12}

### Bonus task extension
- First-order Markov chain modeling
- k-means / median-split state clustering
- Dirichlet smoothing for transition probabilities
- simulation-based confidence intervals for dependent demand :contentReference[oaicite:13]{index=13}

## Key Questions Addressed

1. How should the standard newsvendor profit function be adjusted when surplus goods are sold at a lower price and incur shipping costs? :contentReference[oaicite:14]{index=14}  
2. When does **parametric estimation** outperform **non-parametric estimation**, and when does model misspecification make non-parametric methods preferable? :contentReference[oaicite:15]{index=15}  
3. How should short-run order quantities be estimated across bakery stores with different demand structures? :contentReference[oaicite:16]{index=16}  
4. How much should prices increase to offset a projected **25% cost shock** while preserving profit? :contentReference[oaicite:17]{index=17}  
5. What changes when the i.i.d. demand assumption is relaxed and temporal dependence is modeled explicitly? :contentReference[oaicite:18]{index=18}

## Main Results

- The project shows that **parametric estimators generally outperform non-parametric estimators** for extreme quantiles and smaller sample sizes, with lower RMSE, bias, and profit loss in many simulation settings. :contentReference[oaicite:19]{index=19}
- When the parametric model is **misspecified**, its performance deteriorates sharply, and **non-parametric methods become more robust**. :contentReference[oaicite:20]{index=20}
- For the bakery data, both parametric and non-parametric approaches produced **similar short-run optimal quantities** and **narrow bootstrap confidence intervals**, supporting the stability of the estimates. For example, Main Street A Friday had a parametric estimate of **94.56** and a non-parametric estimate of **94.13**. :contentReference[oaicite:21]{index=21}
- Under a projected **25% cost increase**, the analysis found that roughly **19%–23% store-specific price increases** would be required to maintain baseline profit. Station A required the highest average increase (**23.12%**), while Station B required the lowest (**19.35%**). :contentReference[oaicite:22]{index=22}
- In the bonus task, the Markov-chain-based approach showed that **day-to-day dependence can materially change order quantity estimates** for some stores, while for others the simpler i.i.d. assumption still produced similar results. :contentReference[oaicite:23]{index=23}

## Example Findings

- Increasing shipping cost in the theoretical model reduced the optimal order quantity from about **113.6** to **96.5**, while expected profit fell from about **274.5** to **245.0**. :contentReference[oaicite:24]{index=24}
- The project identified location-specific demand structures such as:
  - **trimodal demand** for Main Street A
  - **bimodal weekday/weekend patterns** for Main Street B, Station A, and Station B :contentReference[oaicite:25]{index=25}
- Across selected bakery segments, parametric and non-parametric confidence intervals were closely aligned, supporting robust operational recommendations. :contentReference[oaicite:26]{index=26}

## Repository Structure

```text
.
├── notebook/
│   └── inventory_optimization_analysis.ipynb
├── report/
│   └── Group_6_Report.pdf
├── project_brief/
│   └── ACSK_PIGame.pdf
├── bonus/
│   └── Group_6_Bonus_Task.pdf
├── figures/
├── data/
├── README.md
└── requirements.txt
