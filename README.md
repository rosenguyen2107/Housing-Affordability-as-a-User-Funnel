# Housing Affordability as a User Funnel

## Business Question
Despite rising incomes, homeownership remains increasingly out of reach for many U.S. households. In this project, I'll explore why do many households fail to become homeowners even when incomes rise, and at which stage of the buying process does affordability break down?
Specifically:
Is income growth enough to improve affordability?
Which step causes the largest drop-off?
Are financing conditions a stronger constraint than prices themselves?

## Analytical Framing (Why a Funnel?)
Rather than treating affordability as a single ratio, I model it as a funnel:
Income-qualified – households earn enough to plausibly enter the market
Savings-capable – households can accumulate a down payment
Mortgage-eligible – households can qualify for financing
Homeowner – households successfully purchase a home
Each stage is defined as a binary condition, allowing conversion rates and drop-offs to be measured clearly—just like a product onboarding funnel.
Using 2022 state-level median data, I identify the binding financial constraints and their geographic and economic patterns.

## Data Sources
U.S. Census / ACS – household income, age, region
Housing price indices (Zillow / FHFA) – regional price levels
Mortgage rates (FRED) – financing conditions
Note: 
When direct savings data is unavailable, I use income-based proxies and clearly document assumptions.
ACS data is cross-sectional (2022) and merged with macro indicators to illustrate structural affordability constraints rather than time dynamics.

## Methodology
Cleaned and joined multi-year datasets at the household–region–year level
Normalized monetary values and aligned time periods
Constructed Funnel Stages (Binary Proxies):
Income-qualified
House price relative to income below affordability threshold.
Savings-capable
Price-to-income ratio low enough to plausibly accumulate a down payment.
Mortgage-eligible
Estimated monthly mortgage payment ≤ underwriting DTI threshold.
Homeowner (Proxy)
Households passing all three constraints above.
These proxies are not literal household approvals, but structural stress indicators that reveal where economic frictions bind at scale.
## Funnel Overview

<img width="1010" height="420" alt="Screenshot 2026-01-12 at 01 27 33" src="https://github.com/user-attachments/assets/57513ce8-784a-4c37-b76c-a74ea6ceb63c" />

The housing affordability funnel reveals a severe structural bottleneck in the path to homeownership. While approximately 71% of households meet basic income qualification thresholds, only 37% are able to accumulate sufficient savings for down payment, and just 23% ultimately meet mortgage underwriting criteria. The largest drop-off occurs at the savings capability stage, indicating that wealth constraints—rather than income alone—are the primary barrier to entering the housing market.

## Geographic inequality

## 
## Key Findings
 1. The largest drop-off occurs at the mortgage stage
Even among income-qualified households, a substantial share fails to qualify for financing—indicating that credit conditions, not income alone, are the primary bottleneck.
 2. Higher income does not fully offset financing constraints
Income growth improves early-stage funnel conversion, but does not prevent sharp drop-offs when mortgage conditions tighten.
 3. Affordability constraints vary sharply by region
High-cost regions experience significantly steeper funnel drop-offs, suggesting that price-to-income ratios amplify sensitivity to financing shocks.



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

## Why This Matters
For:
Banks: highlights interest-rate sensitivity of qualified borrower pools
Policymakers: identifies whether subsidies, zoning, or credit access should be targeted
Product & Analytics teams: demonstrates how funnel modeling reveals hidden friction points beyond surface KPIs

## Conclusion
By reframing housing affordability as a multi-stage funnel, this dashboard shows that the U.S. homeownership gap in 2022 is driven less by insufficient income and more by capital accumulation and mortgage financing constraints.
Unlocking access requires addressing credit frictions, not only raising wages.
