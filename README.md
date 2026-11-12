# Overview

| Summary Component | Description |
| :-------------: | ------ |
| **Dataset Size** | 50k |
| **Time Range** | 2019-2023 |
| **Tools Used** | Tableau, Python, VSCode |
| **Key Metrics** | Click-Through Rate (CTR), Signup Rate, Cost-per-Signup (CPS) |
| **Outcome** | Identified 17% CTR & 13% Signup Rate improvement opportunities for the Marketing Team through improved resource allocation. |

Jump to:
- [Executive Summary](#executive-summary)
- [Insights Deep-Dive](#insights-deep-dive)
  - [Insight 1: Campaign Performance Differences](#insight-1-high-vs-low-performing-campaigns)
  - [Insight 2: Campaign Type-Category Links](#insight-2-customer-testimonial-surge-drives-compare-health-coverage-signups)
  - [Insight 3: Geographical Performance](#insight-3-segmentation)
  - [Insight 4: Product Underperformance](#insight-4-plan-performance)
- [Recommendations](#insights--recommendations)
- [Caveats & Next Steps](#caveats--next-steps)
- [Appendix with Dashboard Screenshot](#appendix)

# Project Background
Founded in 2016, Safety Net is a health insurance provider serving thousands of customers in the US. It launched new marketing campaigns in 2019 with customers able to sign up to one of 4 insurance plans. It recently hired a new data team and aims to use data-driven insights based on past performance to determine next year's marketing budget allocation.

The data team's focus is on analysing marketing campaign performance to improve the Marketing Team's resource allocation and on building a dynamic dashboard to allow them to self-serve insights, aimed at meeting the following goals:
- Increase brand awareness
- Generate new signups.

**Business Question: How should the Marketing Team reallocate next year’s budget to maximize awareness, signups, and cost efficiency across 12 campaigns?**

For each campaign, we evaluate the following **North Star Metrics:**

- **Click-Through-Rate (CTR)** - % of people who click on a link after seeing a campaign.
- **Signup Rate**  - % of people who sign up to a plan after clicking on a link.
- **Cost per Signup (CPS)** - amount in US$ it takes to convert a customer.

View dataset ERD [here](https://raw.githubusercontent.com/Shree-Analyst/SafetyNet_Marketing_Analysis/main/ERD.png).

View interactive self-serve [Tableau dashboard here](https://public.tableau.com/app/profile/shreeraj.salunke/viz/SafetyNetDashboard/Dashboard).

# Executive Summary

![North Star KPIs: CTR | Cost-per-Click | Signup Rate | CPS](https://raw.githubusercontent.com/Shree-Analyst/SafetyNet_Marketing_Analysis/edit/Visualisations/Dashboard%20Top.png)

Safety Net's **CTR was 9.39%, Signup Rate 1.92%, and CPS $3.68**, falling in line with industry benchmarks.

### Insights & Recommendations

- **4 campaigns generated 83% of all signups**: Health For All, Compare Health Coverage, #HealthyLiving, and #CoverageMatters.
- **CTR & Signup Rate split campaigns into 4 performance categories**, based on contribution to increasing brand awareness & generating signups.
- **One-fifth of marketing budget ($11k) was spent on 2 underperforming campaigns** - #InsureYourHealth and Golden Years Security, indicating a core inefficiency of resource allocation.
- **Campaign signup surges linked to campaign types** - Customer Testimonial type campaigns are linked to a surge in monthly signups from Compare Health Coverage campaign.

**We recommend Safety Net's Marketing Team to reallocate resources** and adjust its marketing strategy based on campaign performance. This would **boost CTR by 17%, Signup Rate by 13%**, and lead to stronger efficiency gains.

<div style="page-break-after: always"></div>

# Insights Deep Dive
## Insight 1: High vs Low Performing Campaigns

![Campaign Cost Scatterplot](https://raw.githubusercontent.com/Shree-Analyst/SafetyNet_Marketing_Analysis/main/Visualisations/Scatter%205%20-%20Cost%20(presentation).png)

We can **separate campaigns into 4 performance categories** based on CTR & Signup Rates:
1. **High CTR & High Signup Rate to increase awareness & generate signups** - **Health For All was the outright best-performing campaign** at CTR 25% & Signup Rate 8.2%. Compare Health Coverage followed with CTR 14% & Signup Rate 3%. Combined, these campaigns cost $14k.
2. **Low CTR & High Signup Rate to generate signups** - #CoverageMatters (2.8%), #HealthyLiving (2.8%), and Tailored Health Plans (1.2%) generated signups despite low CTR (10%, 10%, 7% respectively). Combined, these campaigns cost $14k.
3. **Low Signup Rate & High CTR to increase awareness** - Benefit Updates (22%), Summer Wellness Tips (18%), Affordable Plans (13%), and Preventive Care News (12%) increased awareness despite low Signup Rate (ranging from 0.1% to 0.5%). Combined, these campaigns cost $17k.
4. **Low CTR & Low Signup Rate to neither increase awareness nor generate signups** - **Golden Years Security was the outright worst-performing campaign** at CTR 1% & Signup Rate 0.4%. #InsureYourHealth was next with CTR 8% & Signup Rate 0.4%. Combined, these campaigns cost $11k.

$11k allocated to poor performers indicate ineffective results despite high budget allocation. Only $3k more were allocated to high performers despite excellent results. For the Marketing Team, this suggests that **marketing budget is not allocated based on performance.**

<div style="page-break-after: always"></div>

## Insight 2: Customer Testimonial Surge Drives Compare Health Coverage Signups

<div style="display: flex; justify-content: center; align-items: center; gap: 10px;">
  <img src="https://raw.githubusercontent.com/Shree-Analyst/SafetyNet_Marketing_Analysis/main/Visualisations/Signups-Category%20Line%20-%20CHC%20Highlighted%20(presentation).png" alt="CHC Highlighted Line" width="49%">
  <img src="https://raw.githubusercontent.com/Shree-Analyst/SafetyNet_Marketing_Analysis/main/Visualisations/CHC%20Time%20Series%20(presentation).png" alt="CHC Type Line" width="49%">
</div>

**Most campaigns showed a similar trend** in terms of new monthly signups:
- Sharp rise with a **peak in April 2020**, driven by the onset of the Covid-19 pandemic
- **Steady decline since then until 2023**, falling to pre-pandemic levels.

**Exceptionally, the Compare Health Coverage campaign peaked in early-2021 and fell sharply in mid-2022 driven by Customer Testimonial type campaigns**. Overall, Customer Testimonials had a **high CTR (31%) and a high Signup Rate (3.5%)**. Customers also converted at a **low CPS of $1.8, indicating a significant return on investment** despite high spend on Compare Health Coverage ($10k).

Other campaign categories were linked to specific campaign types (eg., #CoverageMatters category with Product Promotion type campaigns). For the Marketing Team, this suggests that further investigation may surface insights on more category-type pairs.

## Insight 3: Segmentation

- **2 states make up over half of customers**: **New Jersey** accounts for 50% of customers - 8.2k out of 16.4k total. A further 1.3k were from neighbouring **New York**, indicating that 58% of customers come from these states. For the Marketing Team, this implies a narrow geographical focus of marketing campaigns.

## Insight 4: Plan Performance

- **Underperformance of platinum & bronze plans.** Only 12 customers signed up to the platinum plan, at a high CPS of $491. Similarly, the bronze plan also generated few signups (591) at a high CPS of $24. For the Product Team, this suggests poor performance of portfolio components.

<div style="page-break-after: always"></div>

# Recommendations:

Our findings would enable the Marketing & Product Teams to reallocate resources and improve acquisition efficiency. We would recommend the marketing & product teams to consider the following:

- **Reallocate budget from underperformers**: Reallocate $11k allocated to poorly performing campaigns (Golden Years Security & #InsureYourHealth) to top performers (Health For All & Compare Health Coverage). This would **boost CTR by 17% and Signup Rate by 13%.**
- **Expand Customer Testimonials to high-performing campaigns**: thanks to attractive performance for Compare Health Coverage, apply Customer Testimonials to high-performing Health For All, #CoverageMatters, and #Healthy Living campaigns. This would **generate new signups at low CPS of $1.8**.
- **Identify campaign-type pairs**: Work with the Marketing Team to evaluate further campaign-type links such as Compare Health Coverage-Customer Testimonials and #CoverageMatters-Product Promotion. This is expected to **surface insights on attractive copies that increase awareness & most efficiently generate signups**.
- **Re-evaluate offering**: Consider eliminating the Platinum plan & making improvements to the Bronze plan due to poor performance. This is expected to **lower acquisition costs, increase efficiency, and optimise marketing resource use**.

# Caveats & Next Steps:

To improve analysis, we recommend the following:
- **Address Data Quality Issues with Data Engineering Team:** Family Coverage Plan had no data on clicks. 49 (0.3%) customer signups were not linked to any campaign. Combining data from separate tables creates nulls in new dimensions.
- **Add Dimensions to Improve Analysis with Marketing Team:** Adding campaign start & end dates allows establishing a link of campaign performance with spend over time. Adding First Touch allows linking signups to marketing channel performance. Adding customer claims helps to explore links between campaign types and claim amount with categories.
- **Explore Dashboard for Self-Serve Insights:**

# Appendix
View presentation to share findings [here](https://raw.githubusercontent.com/Shree-Analyst/SafetyNet_Marketing_Analysis/main/Presentation.pdf) and live presentation demo [here](https://www.loom.com/share/7e2b31d1d441467885cd1067f38347a1).

Tools used: Excel, Tableau, Python, VSCode, GitHub.

View technical process in presentation snippet [here]](https://raw.githubusercontent.com/Shree-Analyst/SafetyNet_Marketing_Analysis/main/Visualisations/Technical%20Process.png).

**Dashboard Screenshot:**
![Dashboard Screenshot](https://raw.githubusercontent.com/Shree-Analyst/SafetyNet_Marketing_Analysis/main/Visualisations/Dashboard.png)