# Final Project — Data Analyst Bootcamp (TripleTen)

## Overview

This repository contains the deliverables for the Data Analyst Bootcamp final project at TripleTen. The project consists of **3 independent case studies**, each with its own datasets, objectives, and analysis.

---

## Repository Structure

```
final-project-data-analyst/
│
├── README.md
├── task_decomposition.ipynb
│
├── case1_telecom/
│   ├── telecom_analysis.ipynb
│   ├── telecom_presentation.pdf
│   ├── final_report_CAR.pdf
│   ├── telecom_tableau_ready.csv
│   └── dashboard.txt
│
├── case2_ab_test/
│   └── ab_test_analysis.ipynb
│
├── case3_sql/
│   └── sql_analysis.ipynb
│
└── datasets/
    ├── telecom_dataset_new.csv
    ├── telecom_clients.csv
    ├── final_ab_events_upd_us.csv
    ├── final_ab_new_users_upd_us.csv
    ├── final_ab_participants_upd_us.csv
    └── ab_project_marketing_events_us.csv
```

---

## Case 1: Telecom — Identifying Inefficient Operators

**Business Problem:** The virtual phone service CallMeMaybe needed a tool to provide supervisors with insights on underperforming operators to improve service quality.

**Inefficiency Criteria:**
- High rate of missed incoming calls (internal and external)
- Long wait times on incoming calls
- Low number of outgoing calls (for outbound operators)

**Methodology:**
- Exploratory Data Analysis on 48,892 call records across 1,092 operators
- Defined quantitative thresholds using 90th/10th percentiles
- Statistical hypothesis testing (Mann-Whitney U, Kruskal-Wallis, Shapiro-Wilk)

**Key Findings:**
- Identified **228 inefficient operators** (20.9% of total)
- Thresholds: missed rate > 3.70%, wait time > 115.2s, outgoing calls < 3
- All hypothesis tests confirmed statistically significant differences (p < 0.05)
- 8,172 unassigned calls (98.5% missed incoming) indicate routing algorithm issues

**Deliverables:** Jupyter Notebook, PDF Presentation, CAR Report, Tableau Dashboard

**Tools:** Python (pandas, scipy, matplotlib, seaborn), Tableau Public

---

## Case 2: A/B Test — Recommender System Evaluation

**Business Problem:** An international e-commerce store launched an A/B test to evaluate an improved recommender system, expecting at least 10% conversion improvement at each funnel stage.

**Test Specifications:**
| Parameter | Value |
|-----------|-------|
| Test Name | `recommender_system_test` |
| Groups | A (control) vs B (new payment funnel) |
| Period | Dec 7, 2020 – Jan 1, 2021 |
| Target Audience | 15% of new EU users |
| Expected Participants | 6,000 |

**Methodology:**
- Test configuration validation (audience, sample size, overlap detection)
- Funnel analysis: login → product_page → product_cart → purchase
- Z-test for proportions with Bonferroni correction (α = 0.05/3)

**Key Findings:**
- **5 critical execution issues** identified:
  - Only 3,675 participants vs 6,000 expected (61.3%)
  - Severely unbalanced groups (A: 2,747 vs B: 928, ratio 3:1)
  - 887 users participating in both tests simultaneously
  - Christmas promo overlapping with last 7 days of test
  - 194 non-EU users in the test
- Group B performed **worse** than Group A across all funnel stages
- **Recommendation:** Do not implement the recommender system; redesign and rerun the test

**Deliverables:** Jupyter Notebook with full validation and statistical analysis

**Tools:** Python (pandas, scipy, statsmodels, matplotlib)

---

## Case 3: SQL — Book Database Analysis

**Business Problem:** A digital reading service needed to generate a value proposition for a new product using their book database containing information about books, publishers, authors, ratings, and reviews.

**Database Schema:** 5 tables — `books`, `authors`, `publishers`, `ratings`, `reviews`

**SQL Queries Performed:**
1. Count of books published after January 1, 2000
2. Number of reviews and average rating per book
3. Publisher with the most books over 50 pages
4. Author with the highest average rating (books with ≥50 ratings only)
5. Average number of text reviews among users who rated 50+ books

**Key Insights:**
- Catalog is primarily contemporary (post-2000), ideal for a digital platform
- Identified leading publisher for substantial books (>50 pages) — potential strategic partner
- Top-rated authors with statistically significant sample sizes identified for curated collections
- Power users (50+ ratings) represent a valuable segment for product engagement

**Deliverables:** Jupyter Notebook with pure SQL queries and business-oriented conclusions

**Tools:** PostgreSQL, SQLAlchemy, pandas

---

## Tech Stack

| Category | Tools |
|----------|-------|
| Programming | Python 3, SQL (PostgreSQL) |
| Data Analysis | pandas, NumPy |
| Statistical Testing | SciPy, statsmodels |
| Visualization | Matplotlib, Seaborn, Tableau Public |
| Database | PostgreSQL via SQLAlchemy |
| Reporting | ReportLab (PDF generation) |

---

## Skills Demonstrated

- **Data Wrangling:** Cleaning, transforming, and merging datasets with missing values, duplicates, and type inconsistencies
- **Exploratory Data Analysis:** Distribution analysis, temporal trends, segmentation, funnel analysis
- **Statistical Hypothesis Testing:** Parametric vs non-parametric test selection, Bonferroni correction, effect size interpretation
- **SQL:** Complex queries with JOINs, subqueries, aggregation functions, and HAVING clauses
- **Data Visualization:** Interactive dashboards, histograms, scatter plots, funnel charts, pie charts
- **Business Communication:** CAR-format reporting, actionable recommendations, stakeholder-oriented conclusions

---

## Author

- **Name:** Karin Ortiz
- **Program:** Data Analyst Bootcamp — TripleTen
- **Date:** March 9 2026
- **Email:** yamir.ortiz9024@gmail.com
