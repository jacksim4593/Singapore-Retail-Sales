# Singapore-Retail-Sales

## Overview
This repository presents an analysis of Singapore's retail sales trends, with a focus on the acceleration of online retail adoption during and post-COVID-19. The study examines whether pandemic-induced shifts led to deflationary pressures across retail categories through heightened online competition and provides strategic recommendations for retailers on balancing online and offline channels.

The analysis utilizes official retail sales data from the Singapore Department of Statistics (SingStat), processed via Python for data cleaning and transformation, and visualized in Tableau for interactive insights.

## Project Objectives

- Assess the impact of COVID-19 on online retail penetration in Singapore.
- Evaluate deflationary pressures in specific categories (e.g., Computer & Telecommunications Equipment, Furniture & Household Equipment, Supermarkets & Hypermarkets) driven by increased e-commerce competition.
- Derive actionable strategies for retailers to optimize channel positioning between online and offline sales.

## Data Sources

**Dataset:**
- Retail Sales Index, (2017 = 100), In Chained Volume Terms, Monthly, Seasonally Adjusted from SingStat via data.gov.sg.
  - Covers categories such as Total Retail Trade, Supermarkets & Hypermarkets, Computer & Telecommunications Equipment, and Furniture & Household Equipment.
  - Time Period: January 2008 to August 2025.
  - Key Metrics: Volume indices
 
- Retail Sales Index, (2017 = 100), At Current Prices, Monthly, Seasonally Adjusted from SingStat via data.gov.sg.
  - Covers categories such as Total Retail Trade, Supermarkets & Hypermarkets, Computer & Telecommunications Equipment, and Furniture & Household Equipment.
  - Time Period: January 2008 to August 2025.
  - Key Metrics: Price indices
 
- Online Retail Sales Proportion (Out Of The Respective Industry's Total Sales), Monthly from SingStat via data.gov.sg.
  - Covers categories such as Total Retail Trade, Supermarkets & Hypermarkets, Computer & Telecommunications Equipment, and Furniture & Household Equipment.
  - Time Period: January 2019 to August 2025.
  - Key Metrics: Online penetration percentages

Data is fetched programmatically using the data.gov.sg API.

## Methodology

1. **Data Acquisition and Cleaning:**
- Python script (Singapore Retails Sales Project.ipynb) retrieves raw data via API requests.
- Performs transformations including:
  - Pivoting wide-format monthly data into long format.
  - Calculating YoY percentage changes for volumes and prices.
  - Deriving category-specific deflationary deflators (price index minus volume index adjustments).
  - Handling missing values and ensuring seasonal adjustments.


2. **Analysis and Visualization:**
- Exported cleaned dataset (retail_master_v2.csv) serves as input for Tableau.
- Tableau dashboard explores trends in online vs. offline proportions, deflator breakdowns, and correlations (e.g., R² between online share and deflationary pressures).


Libraries Used: pandas, requests, numpy, seaborn, matplotlib, statsmodels, scipy.

## Key Insights

- **Online Adoption:** COVID-19 drove a structural shift, with online penetration reaching ~50% in electronics and stabilizing at 15-20% overall post-2021.
- **Deflationary Pressures:** Categories with high online penetration (e.g., electronics) exhibit deflators below the total retail average, widening gaps in 2023-2025 due to platform competition.
- **Channel Strategies:**
  - High-penetration categories: Shift budgets to online for aggressive pricing.
  - Low-penetration categories (e.g., groceries): Prioritize physical stores for experiential growth, using online tactically for share capture.


For detailed visualizations, refer to the interactive Tableau dashboard.

## Repository Structure
- Singapore Retails Sales Project.ipynb
   - Jupyter Notebook for data fetching, cleaning, and export.
- retail_master_v2.csv
  - Cleaned dataset (generated from the notebook; includes volumes, prices, online %, and deflators)
- README.md
  - This file

## Interactive Dashboard
View the live Tableau visualization: https://public.tableau.com/views/SingaporeRetailSalesTrend/SingaporeRetailTrends?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link 

Singapore Retail Trends

## Acknowledgments

- Singapore Department of Statistics (SingStat) for open data access.
- Tableau Public for visualization hosting.
