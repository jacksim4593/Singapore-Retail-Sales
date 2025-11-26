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

**Note on Online Volume Derivation:** Online volumes are approximated as the product of the nominal online penetration proportion (from Dataset 3) and the total retail sales index in chained volume terms (from Dataset 1). This method assumes that the volume share of online sales approximates the nominal proportion, adjusted implicitly through the chained volume index. In practice, this introduces a minor approximation, as the proportion reflects current-price (nominal) shares, and channel-specific price deflators are unavailable in the datasets. For precise applications, an online-specific deflator (e.g., from supplementary SingStat consumer price data) could refine this estimate. The approximation is suitable for trend analysis and preserves the time-series integrity.

2. **Analysis and Visualization:**
- Exported cleaned dataset (retail_master_v2.csv) serves as input for Tableau.
- Tableau dashboard explores trends in online vs. offline proportions, deflator breakdowns, and correlations (e.g., R² between online share and deflationary pressures).


Libraries Used: pandas, requests, numpy, seaborn, matplotlib, statsmodels, scipy.

## Key Insights

**Overall Online Adoption:** The COVID-19 pandemic catalyzed a structural shift in Singapore's retail landscape, accelerating online penetration by 50% to 200% relative to pre-2020 levels (from ~5-25% to 15-50% across categories), driven by lockdowns, digital infrastructure enhancements, and enduring consumer behavioral changes.

**Deflationary Pressures:** This heightened e-commerce adoption has exerted selective downward pressure on prices, with high-penetration categories (e.g., electronics) displaying deflators consistently below the overall retail average since 2020. The divergence has intensified through 2023–2025, attributable to platform-enabled competition, including algorithmic pricing and cross-border imports, thereby confirming pandemic-induced shifts as a catalyst for category-specific inflationary moderation.

**Category specific recommendations are as follow:**

- **Computer & Telecommunications Equipment:**
  - Retailers must treat online as the primary sales and marketing channel.
  - The category has undergone a permanent structural shift to around 50% online penetration post-COVID, enabling significantly more aggressive pricing than offline.
  - This is evidenced by the category deflator remaining consistently below the overall retail deflator since 2020, with an increasing gap in 2023–2025, reflecting intensified price competition on platforms.

- **Furniture & Household Equipment:**
  - Retailers should shift budget and strategy toward online channels, especially during year-end sales, where online proportion usually tops.
  - Despite an increase in the average category deflator from -1.773 to 3.008, the category deflator still generally stays below the total deflator.

- **Supermarkets & Hypermarkets:**
  - Supermarkets and hypermarkets remain predominantly offline-driven (~85–88% of volume), and online share has gradually declined from its 2021 peak.
  - Primary Implication: Traditional supermarkets/hypermarkets should continue prioritizing physical stores and in-store experience as the core growth driver.
  - Secondary/Strategic Implication: Online remains a powerful price-competition weapon. There is a strong positive correlation (R² ≈ 0.54) between online proportion and downward pressure on the category deflator. Therefore, retailers seeking to gain share in saturated or new sub-categories (e.g., premium groceries, private labels, health & wellness, alcohol, baby products) can use aggressive online pricing (via RedMart, Shopee Supermarket, PandaMart, own apps) as an effective tool to disrupt incumbents and capture share quickly.


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
