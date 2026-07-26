
# QuickBite Express - Crisis Recovery Analysis & Strategic Roadmap
In June 2025, QuickBite Express lost 69% of its customer base in less than 90 days.
This repository contains my complete Power BI analysis of what went wrong — and how data can guide the recovery.

**A comprehensive data-driven analysis of a food delivery startup's crisis 
and evidence-based recovery strategy.**

---

## 📋 Table of Contents

1. Project Overview
2. Problem Statement
3. Dataset Description
4. Methodology
5. Key Findings
6. Recommendations
7. Technical Implementation
8. Deliverables
9. Sources & References
10. How to Explore

---

## 🎯 Project Overview

**Project Type:** Business Case Analysis | Data Analytics | Strategic Consulting  
**Domain:** Food Delivery & Consumer Analytics  
**Time Period Analyzed:** January - September 2025  
**Focus:** Crisis Analysis & Recovery Strategy Development  
**Tools Used:** Power BI, DAX, Statistical Analysis  
**Audience:** Data Analysts, Business Strategists, Recruiters

### Executive Summary

In June 2025, QuickBite Express - a Bengaluru-based food delivery startup 
(founded 2020) - faced a critical crisis triggered by:
- Viral food safety incident involving partner restaurants
- Week-long delivery infrastructure outage during monsoon season
- Aggressive competitor campaigns capitalizing on operational failures

**Crisis Impact:**
- 73,000 customers churned (70% of active base)
- ₹27 million revenue lost in 4 months
- Customer ratings collapsed from 4.5 → 2.3 stars
- 20% restaurant partner exodus

**Key Discovery:**
Despite the severity, **30% of churned customers (22,000) were recoverable** 
because they left due to operational failure, not dissatisfaction.

**Strategic Output:**
A data-driven ₹70-80M recovery roadmap with 4 strategic pillars, expected 
to achieve 80-90% recovery within 6-9 months with 3-4x ROI on reactivation.

---

## 💼 Problem Statement

### Business Challenge

QuickBite Express requires a comprehensive analysis of its June-September 2025 
crisis to:

1. **Understand Crisis Severity:** Quantify impact across all business metrics
2. **Identify Root Causes:** Determine what triggered the cascade of failures
3. **Customer Impact Analysis:** Segment churned customers by recovery probability
4. **Competitive Context:** Benchmark against industry peers during crisis
5. **Recovery Strategy:** Design a data-backed turnaround plan with timelines & ROI
6. **Operational Insights:** Identify systemic vulnerabilities to prevent recurrence

### Analysis Questions Addressed

**Primary Analysis (10 questions):**
1. Monthly order decline comparison (pre-crisis vs crisis)
2. Top 5 cities by order decline percentage
3. Top 10 high-volume restaurants with largest decline
4. Cancellation rate trend analysis and geographic impact
5. Delivery SLA performance degradation
6. Monthly customer rating fluctuations
7. Negative keyword sentiment analysis
8. Revenue impact quantification
9. Loyalty impact on 5+ order customers with 4.5+ ratings
10. High-value customer (top 5%) decline patterns

**Secondary Analysis (5 questions + 3 extra details):**
- Most effective recovery strategies
- Restaurant type churn risk assessment
- Lapsed customer return probability
- Priority cities risk analysis
- Customer order value shift behavior
- Review spike correlation with delivery outage

---

## 📊 Dataset Description

### Data Sources

| Data Type | Source | Time Period | Records | Key Metrics |
|-----------|--------|-------------|---------|------------|
| **Orders** | QuickBite transactional DB | Jan-Sep 2025 | 149K orders | order_id, customer_id, order_date, order_total, phase |
| **Customers** | CRM system | Jan-Sep 2025 | 105K customers | customer_id, acquisition_date, total_spend, LTV |
| **Reviews & Ratings** | Review system | Jan-Sep 2025 | 69K reviews | rating, sentiment, review_text, date |
| **Restaurant Data** | Partner DB | Jan-Sep 2025 | 20K restaurants | restaurant_id, cuisine_type, order_count, status |
| **Operational Metrics** | Delivery/Operations DB | Jan-Sep 2025 | Daily logs | delivery_time, sla_compliance, cancellations, delays |

### Key Fields & Definitions

**Phase Classification:**
- **Pre-Crisis:** January - May 2025 (5 months baseline)
- **Crisis:** June - September 2025 (4 months of operational failure)

**Customer Segmentation:**
Total Customers:     105,000 (all unique customers)
Active :             100,000 (placed 1+ non-cancelled orders )
Churned:             73,000 (orders pre-crisis, ZERO orders crisis)
New:                 18,000 (first order Jun-Sep 2025)
Retained:            14,000 (orders in both periods)

**Order Metrics:**
Pre-Crisis Monthly Average:   24,000 orders/month
Crisis Monthly Average:       9,000 orders/month
Decline:                      69% (24K → 9K)

**Revenue Metrics:**
Pre-Crisis Total:      ₹3.8 Crore (5 months)
Crisis Total:         ₹1.1 Crore (4 months)
Difference:           ₹2.7 Crore lost
Decline:              71%

---

## 🔬 Methodology

### 1. Data Analysis Framework

#### A. Descriptive Analysis
**Purpose:** Understand current state and crisis severity

**Metrics Calculated:**
- Order volume by month, city, cuisine
- Revenue by component (subtotal, delivery fee, discounts)
- Customer counts by status (active, churned, new, retained)
- Cancellation rates and SLA compliance trends
- Average ratings and sentiment scores

**Tools:** Power BI aggregations, DAX measures, statistical functions




#### B. Comparative Analysis
**Purpose:** Quantify pre-crisis vs crisis changes

**Methodology:**
Decline % = (Pre-Crisis Value - Crisis Value) / Pre-Crisis Value × 100
Example - Order Decline:
= (24,000 - 9,000) / 24,000 × 100
= 69% decline

**Applied to:** Orders, revenue, ratings, cancellations, SLA compliance



#### C. Customer Segmentation
**Purpose:** Identify recoverable customers

**Segmentation Criteria:**

**High Return Probability (60% return chance):**
IF (Pre-Crisis Orders ≥ 5) AND (Pre-Crisis Avg Rating ≥ 4.5) AND (Crisis Orders = 0)
THEN "High Return - Recoverable"
Sample Size: 22,000 customers
Rationale: Loyal customers lost due to failure, not dissatisfaction

**Medium Return Probability (40% return chance):**
IF (Pre-Crisis Orders = 3-4) AND (Pre-Crisis Avg Rating ≥ 3.5) AND (Crisis Orders = 0)
THEN "Medium Return - Price Sensitive"
Sample Size: 28,000 customers
Rationale: Mixed experience, cost-conscious, can be won back

**Low Return Probability (15% return chance):**
IF (Pre-Crisis Orders ≤ 2) AND (Pre-Crisis Avg Rating < 3.5)
THEN "Low Return - Low Priority"
Sample Size: 23,000 customers
Rationale: Never engaged fully, low potential

#### D. Revenue Impact Analysis
**Purpose:** Quantify financial loss across components

**Revenue Breakdown:**
Total Revenue = Subtotal Amount + Delivery Fee + Discounts Applied
Pre-Crisis Subtotal:     ₹36.34 Cr
Crisis Subtotal:        ₹10.56 Cr
Subtotal Decline:       70.95%
Pre-Crisis Delivery Fee: ₹3.47 Cr
Crisis Delivery Fee:     ₹1.01 Cr
Delivery Fee Decline:    70.84%
Pre-Crisis Discounts:    ₹2.19 Cr
Crisis Discounts:        ₹0.63 Cr
Discount Decline:        71.34%
Total Revenue Lost:      ₹27 million (70.92% decline)

#### E. Sentiment Analysis
**Purpose:** Understand customer perception changes

**Sentiment Scoring Method:**
Rating-Based Sentiment:

Rating 4.5-5.0:  Positive (1.0)
Rating 3.5-4.4:  Neutral (0.5)
Rating 2.5-3.4:  Mixed (-0.5)
Rating <2.5:     Negative (-1.0)

Average Sentiment = Sum of All Sentiment Scores / Total Reviews
Pre-Crisis Avg Rating:   4.55 → Positive Sentiment
Crisis Avg Rating:       2.30 → Negative Sentiment
Sentiment Change:        -0.49 (1.42 point drop on -1 to +1 scale)

**Keyword Analysis:**
- Text parsing on 69K reviews
- Frequency analysis of negative keywords
- Clustering by issue category (food quality, delivery, packaging, etc.)
- Crisis vs pre-crisis comparison

---


### 2. Recovery Strategy ROI Modeling

#### Pillar 1: Customer Reactivation
Target Segment:        22,000 high-probability customers
Incentive:             40% off + 3 months premium membership
Expected Reactivation: 60% (industry benchmark)
Customers Recovered:   13,200
Avg Customer LTV:      ₹8,500
Revenue Recovered:     ₹1.12 Cr
Investment:            ₹20-25M (incentives + marketing)
ROI:                   3-4x within 12 months
#### Pillar 2: Food Safety Certifications
Investment:            ₹15-20M (FSSAI/HACCP audits, badges, promotion)
Expected Trust Impact: 35-40% improvement
Timeline:              2-3 months to certification
Permanent Benefit:     Ongoing compliance & customer confidence
#### Pillar 3: Operational Excellence
Components:

Weather-adaptive routing: ₹8-10M
Fleet expansion: ₹12-15M
SLA monitoring systems: ₹5-7M
Total Investment:      ₹25-30M

Expected SLA Improvement: 12% → 40%+
Cancellation Reduction:   11.6% → <7%
Timeline:                 6 months

#### Pillar 4: Restaurant Support
Commission Reduction:  5-10% for 6 months on <50 orders/month

Marketing Support:     Featured listings, campaigns

Financial Assistance:  Working capital support

Target:                Small cloud kitchens (highest risk)

Expected Retention:    85% (vs. current 79%)

Investment:            ₹10-15M

**Total Recovery Roadmap:**

Total Investment:      ₹70-80M

Timeline:              6-9 months

Expected Recovery:     80-90% of pre-crisis metrics

Cumulative ROI:        2.5-3x on total investment

---

## 📈 Key Findings

### Crisis Impact Summary

| Metric | Pre-Crisis | Crisis | Change | % Change |
|--------|-----------|--------|--------|----------|
| Monthly Orders | 24,000 | 9,000 | -15,000 | -62.5% |
| Monthly Revenue | ₹7.6M avg | ₹2.75M avg | -₹4.85M | -63.8% |
| Total Revenue (period) | ₹38M | ₹11M | -₹27M | -71% |
| Active Customers | 100,000 | 27,000 | -73,000 | -73% |
| Avg Rating | 4.55 stars | 2.30 stars | -2.25 | -49% |
| SLA Compliance | 44% | 12% | -32% | -73% |
| Avg Delivery Time | 40 min | 60 min | +20 min | +50% |
| Cancellation Rate | 6.2% | 11.6% | +5.4% | +87% |

### Root Causes

**Primary (Operational):**
1. SLA compliance collapsed 44% → 12%
2. Delivery infrastructure failed during monsoon
3. High cancellations cascaded to negative reviews

**Secondary (Reputational):**
1. Food safety viral incident
2. Negative review sentiment hit 90% by September
3. Top complaints: Quality (1,596), Safety (1,076), Packaging (997)


### Recovery Opportunity

**Recoverable Customer Base:**
- High-priority: 22,000 customers (60% recovery probability)
- Revenue at risk: ₹1.12 Cr annually from top 5% segment alone
- Geographic concentration: Bengaluru (27%) and Mumbai (15%)
- Order frequency recovery potential: 4.1 → 2.5+ orders/month

**Key Insight:**
Customers didn't leave due to preference shift; they left due to service failure. 
This is reversible through targeted reactivation + operational fixes.

---

## 💡 Recommendations

### Immediate Actions (Month 1)

1. **Launch VIP Reactivation Campaign**
   - Target: 22,000 high-return customers
   - Offer: 40% off + 3 months premium
   - Expected: 13,200 returns, ₹1.12 Cr recovery

2. **Begin Food Safety Certification**
   - FSSAI + HACCP audits for all partners
   - Visible hygiene badges on app
   - Expected: 35-40% trust improvement

3. **Restaurant Support Program**
   - 5-10% commission reduction for small partners
   - Marketing support for vulnerable cuisines
   - Focus: North Indian/Biryani (75% at-risk)

### Medium-term (Month 2-6)

4. **Operational Infrastructure Overhaul**
   - Implement weather-adaptive routing
   - Expand delivery fleet in monsoon-heavy zones
   - Real-time SLA monitoring system

5. **Customer Retention Program**
   - Tiered loyalty benefits
   - Regular engagement campaigns
   - Feedback loops for continuous improvement

### Long-term (Month 6-9)

6. **Market Repositioning**
   - Competitive differentiation based on reliability
   - Premium segment recovery (vs. budget)
   - Geographic expansion from recovered base

---

## 🛠️ Technical Implementation

### Tools & Technologies Used

**Data Visualization:**
- **Power BI Desktop:** Interactive dashboards, 7 comprehensive pages
- **Visual Types:** Cards, charts, tables, donut charts, heatmaps, word clouds
- **DAX Functions:** CALCULATE, SWITCH, IF, DIVIDE, DISTINCTCOUNT, SUMMARIZE

**Data Analysis:**
- **DAX Measures:** 50+ custom measures for segmentation, risk scoring, ROI
- **Calculations:** Statistical aggregations, trend analysis, probability scoring
- **Modeling:** Customer lifetime value, churn probability, recovery potential

### Dashboard Structure

**Page 1: Home**
- Quick navigation to all analysis sections
<img width="1907" height="920" alt="image" src= "https://github.com/Nagulasuprika/QuickBite-Crisis-Analysis/blob/a38e30b7980b3ec1f0c054bde1a7bff51f08743e/Home%20Page.png" />

**Page 2: Crisis Overview**
- KPI cards: Total orders, revenue, rating, cancellations
- Key metrics highlighted
- Monthly revenue trend
- Order volume comparison
- Top affected cities
- Revenue breakdown by component
<img width="1917" height="922" alt="image" src="https://github.com/Nagulasuprika/QuickBite-Crisis-Analysis/blob/36a942683cc0da6a3ad4c6db860460c83e1bb1fa/Crisis%20Overview.png" />



**Page 3: Customer Impact Analysis**
- Customer segmentation donut
- City distribution
- Customer status breakdown
- High-value customer impact
  <img width="1916" height="926" alt="image" src="https://github.com/Nagulasuprika/QuickBite-Crisis-Analysis/blob/1e7ba128efa5363c7eec5c01cf4cac6520df2e3e/Customer%20Impact%20Analysis.png" />


**Page 4: Operational Performance**
- SLA compliance trends
- Delivery time analysis
- Cancellation rates by city/vehicle
- Monthly operational metrics table
  <img width="1920" height="912" alt="image" src="https://github.com/Nagulasuprika/QuickBite-Crisis-Analysis/blob/af99110b044f96ecd282b634873fa5cd44840bb9/Operational%20Performance.png" />


**Page 5: Restaurant Analysis**
- Partner count by city
- Restaurant retention rates
- Cuisine-wise order comparison
- Restaurant risk categorization
  <img width="1916" height="906" alt="image" src="https://github.com/Nagulasuprika/QuickBite-Crisis-Analysis/blob/7a9afbe8a3441318c18aed6ec341eb81a507bba0/Restaurant%20Analysis.png" />


**Page 6: Customer Sentiment Analysis**
- Rating trend over time
- Review volume timeline
- Negative review word cloud
- Top negative keywords and themes
<img width="1915" height="923" alt="image" src="https://github.com/Nagulasuprika/QuickBite-Crisis-Analysis/blob/b65c184dceb94a1303dd2e12c57d426177e71e3d/Customer%20Sentiment%20Analysis.png" />


**Page 7: Strategic Recovery Insights**
- Restaurant churn by type (cloud kitchen vs dine-in)
- Customer return probability segmentation
- Order value shift analysis (premium → budget)
- SLA delay vs negative reviews correlation
<img width="1920" height="911" alt="image" src="https://github.com/Nagulasuprika/QuickBite-Crisis-Analysis/blob/6f83774f53d817496a6ca327c702352710ff081b/Strategic%20Recovery%20Insights.png" />

---

## 📊 Key Metrics Summary

| Category | Metric | Value | Context |
|----------|--------|-------|---------|
| **Orders** | Pre-Crisis Monthly | 24,000 | Baseline |
| | Crisis Monthly | 9,000 | Collapsed period |
| | Decline % | 69% | Severity indicator |
| **Revenue** | Pre-Crisis Total | ₹38M | 5-month period |
| | Crisis Total | ₹11M | 4-month period |
| | Loss | ₹27M | Absolute impact |
| **Customers** | Pre-Crisis Active | 100,000 | Loyal base |
| | Crisis Active | 27,000 | Dramatic drop |
| | Churned | 73,000 | Lost customers |
| | Recoverable | 22,000 (30%) | High-priority reactivation |
| **Ratings** | Pre-Crisis | 4.55 stars | Strong satisfaction |
| | Crisis | 2.30 stars | Critical deterioration |
| | Drop | 2.25 stars | Trust collapse |
| **Operations** | SLA Pre | 44% | Adequate |
| | SLA Crisis | 12% | Failure |
| | Delivery Time | 40 → 60 min | 50% increase |
| **Recovery** | Investment | ₹70-80M | Total budget |
| | Timeline | 6-9 months | Expected duration |
| | Expected Recovery | 80-90% | Success target |
| | ROI | 3-4x | Return on investment |



---

