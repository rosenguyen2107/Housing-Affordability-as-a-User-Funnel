# Housing Affordability as a User Funnel

## Business Question
Despite rising incomes, homeownership remains increasingly out of reach for many U.S. households. In this project, I'll explore why do many households fail to become homeowners even when incomes rise, and at which stage of the buying process does affordability break down?
Specifically:
- Is income growth enough to improve affordability?
- Which step causes the largest drop-off?
- Are financing conditions a stronger constraint than prices themselves?

## Analytical Framing (Why a Funnel?)
Rather than treating affordability as a single ratio, I model it as a funnel:
   1. Income-qualified – households earn enough to plausibly enter the market
   2. Savings-capable – households can accumulate a down payment
   3. Mortgage-eligible – households can qualify for financing
   4. Homeowner – households successfully purchase a home
      
Each stage is defined as a binary condition, allowing conversion rates and drop-offs to be measured clearly—just like a product onboarding funnel.
Using 2022 state-level median data, I identify the binding financial constraints and their geographic and economic patterns.

## Data Sources
1. U.S. Census / ACS – household income, age, region

2. Housing price indices (Zillow / FHFA) – regional price levels

3. Mortgage rates (FRED) – financing conditions

Note: 
- When direct savings data is unavailable, I use income-based proxies and clearly document assumptions.
- ACS data is cross-sectional (2022) and merged with macro indicators to illustrate structural affordability constraints rather than time dynamics.

## Methodology

Cleaned and joined multi-year datasets at the household–region–year level.

Normalized monetary values and aligned time periods.

Constructed Funnel Stages (Binary Proxies):

- Income-qualified: House price relative to income below affordability threshold.

- Savings-capable: Price-to-income ratio low enough to plausibly accumulate a down payment.

- Mortgage-eligible: Estimated monthly mortgage payment ≤ underwriting DTI threshold.

- Homeowner (Proxy): Households passing all three constraints above.

   These proxies are not literal household approvals, but structural stress indicators that reveal where economic frictions bind at scale.

## Funnel Overview

<img width="1010" height="420" alt="Screenshot 2026-01-12 at 01 27 33" src="https://github.com/user-attachments/assets/57513ce8-784a-4c37-b76c-a74ea6ceb63c" />


The funnel analysis reveals that the primary constraint to homeownership is not monthly income, but balance-sheet capacity. While approximately 71% of households satisfy basic income qualification thresholds, only 36% are able to accumulate sufficient savings for a down payment, and merely 23% ultimately meet mortgage underwriting criteria. The largest drop-off occurs between the savings capability and mortgage eligibility stages, indicating that wealth accumulation and debt constraints, rather than wage levels alone, are the dominant barriers to market entry.

This distinction highlights a critical economic mechanism: cash-flow affordability and balance-sheet affordability are no longer aligned. Many households can theoretically service a mortgage, yet are excluded by initial capital requirements and debt-to-income limits.

## Geographic Inequality

<img width="738" height="439" alt="Screenshot 2026-01-12 at 01 38 16" src="https://github.com/user-attachments/assets/5336a6fb-47ac-4bac-8607-4d1b05c53318" />
<img width="738" height="439" alt="Screenshot 2026-01-12 at 01 38 51" src="https://github.com/user-attachments/assets/1b3e9b72-20d8-4b81-a272-ccec3d591abb" />
<img width="738" height="439" alt="States with Lowest Price-to-Income Ratio" src="https://github.com/user-attachments/assets/62ad7aa9-c205-4bca-b125-b41d32a5b4fc" />


Geographically, affordability is highly uneven. Coastal and high-growth states such as Hawaii, California, and the District of Columbia exhibit extreme price-to-income ratios, systematically pushing households beyond sustainable debt-to-income limits. Even in states with comparable median incomes, housing prices vary widely, leading to sharp differences in mortgage eligibility and ownership outcomes.


<img width="738" height="439" alt="California" src="https://github.com/user-attachments/assets/89407382-c865-4bc4-8825-4bbe850b8ead" />


In high-cost coastal markets such as California, the median price-to-income ratio exceeds 7.5. At this level, the typical household is unable to accumulate a sufficient down payment within a reasonable time horizon, resulting in near-zero savings capability and mortgage eligibility rates in the funnel proxy. Homeownership becomes effectively restricted to existing asset holders, reinforcing wealth-based sorting and intergenerational lock-in.


<img width="738" height="439" alt="Iowa" src="https://github.com/user-attachments/assets/db648fba-8322-45b9-80eb-78cfb10d9fc9" />


In contrast, states such as Iowa exhibit price-to-income ratios below 3.0. Under these conditions, median-income households are able to build savings and satisfy credit constraints, producing near-universal mortgage eligibility and ownership outcomes. The comparison demonstrates that spatial variation in asset prices, rather than labor income, is the principal driver of ownership inequality.


## Structural Relationships

<img width="738" height="439" alt="Screenshot 2026-01-12 at 01 39 14" src="https://github.com/user-attachments/assets/01d9013c-7106-46d4-8dae-260f14235d2e" />


The relationship between median household income and median home value is positive but highly dispersed across states, reflecting the role of local supply constraints, zoning, and demand concentration. States with similar income levels can face radically different housing costs, leading to stark differences in affordability and credit access.


<img width="738" height="439" alt="Screenshot 2026-01-12 at 01 39 49" src="https://github.com/user-attachments/assets/fd962413-f3da-41ed-9fef-3d2a87343bce" />


Furthermore, the near-linear relationship between the price-to-income ratio and total debt-to-income ratios indicates that housing price inflation rapidly pushes households beyond underwriting thresholds. As prices rise faster than incomes, credit exclusion intensifies even in economically strong regions.

Together, these patterns suggest that the U.S. housing crisis is less a problem of insufficient earnings and more a problem of asset price dynamics and down payment constraints, creating persistent barriers to wealth accumulation and intergenerational mobility.


## Interactive Dashboard

The full interactive Power BI dashboard is available in:

`/dashboard/housing_affordability_dashboard.pbix`

To view:
1. Download Power BI Desktop
2. Open the `.pbix` file
3. Navigate through the 4 pages:
   - Funnel Overview
   - Bottleneck Diagnostics
   - Geographic Inequality
   - Structural Relationships

Preview images of each page are available in `/dashboard_preview/`.

## Key Insights
The dashboard shows that the U.S. housing crisis is not primarily an income problem, but a balance-sheet and asset-price problem. While most households earn enough to service a mortgage in theory, only a minority can accumulate sufficient wealth and meet debt constraints in high-price regions. Geographic price dispersion transforms housing from a labor-market good into a wealth-gated asset, reinforcing spatial and intergenerational inequality.

## Why This Matters
- For banks: highlights interest-rate sensitivity of qualified borrower pools.
- For policymakers: identifies whether subsidies, zoning, or credit access should be targeted.
- For product & analytics teams: demonstrates how funnel modeling reveals hidden friction points beyond surface KPIs.

## Conclusion
By reframing housing affordability as a multi-stage funnel, this dashboard shows that the U.S. homeownership gap in 2022 is driven less by insufficient income and more by capital accumulation and mortgage financing constraints. Unlocking access requires addressing credit frictions, not only raising wages.
