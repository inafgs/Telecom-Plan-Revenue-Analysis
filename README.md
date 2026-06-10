# Telecom-Plan-Revenue-Analysis
Comparative revenue analysis of two telecom prepaid plans using Python. Integrates and cleans 5 datasets, computes monthly user revenue, and applies statistical hypothesis testing to identify the most profitable plan.

# Overview
This project analyzes two prepaid plans offered by Megaline, a fictional telecommunications company, to determine which plan generates more revenue. The findings are intended to help the commercial team make data-backed decisions about advertising budget allocation.
The analysis covers data cleaning and integration across 5 independent datasets, monthly revenue calculation per user, behavioral comparisons between plan subscribers, and formal statistical hypothesis testing.

# Business Problem
Megaline offers two prepaid plans — Surf and Ultimate — and needs to know which one is more profitable in order to optimize its marketing budget. This project answers:

Which plan generates higher average monthly revenue per user?
Do users behave differently depending on their plan (calls, messages, data usage)?
Is the revenue difference between plans statistically significant?
Do users from the NY-NJ area generate different revenue compared to users in other regions?


# Dataset
Five independent tables were provided:
TableDescriptionplansPlan conditions: monthly fee, included minutes, messages, and datausersUser information: plan, registration date, churn date, citycallsCall logs per user: date and duration in minutesmessagesSMS logs per user: date sentinternetData usage logs per user: date and MB consumed

# Tools & Technologies
ToolPurposePythonCore programming languagepandasData cleaning, integration, and aggregationmatplotlibData visualizations (histograms, boxplots)SciPy (stats)Statistical hypothesis testingJupyter NotebookDevelopment environment

# Methodology
1. Data Preparation

Inspected all 5 tables for missing values, incorrect data types, and duplicates
Converted date columns to datetime format
Rounded call durations up to the nearest minute (as per billing conditions)
Converted internet usage from MB to GB

2. Data Enrichment

Extracted month and year from date columns for monthly aggregation
Merged all tables into a single unified DataFrame with one record per user per month

3. Revenue Calculation

Computed monthly consumption per user (calls, messages, data)
Applied plan conditions: subtracted free allowances, calculated overage charges
Added monthly base fee to produce total monthly revenue per user

4. Behavioral Analysis

Compared call duration, message count, and data usage between Surf and Ultimate users
Computed descriptive statistics (mean, variance, standard deviation)
Visualized distributions using histograms and boxplots

5. Hypothesis Testing
Two formal statistical tests were performed using a significance level of α = 0.05:

Test 1: Is the average monthly revenue from Ultimate users different from Surf users?

Applied Welch's t-test (unequal variances confirmed)
Result: Statistically significant difference confirmed — Ultimate generates higher revenue


Test 2: Is the average revenue from NY-NJ users different from users in other regions?

Same methodology
Result: No statistically significant difference found




# Key Findings

The Ultimate plan generates higher average monthly revenue per user (~72 USD) compared to the Surf plan (~57 USD)
Ultimate users tend to use slightly more calls, messages, and data on average
Surf plan users more frequently exceed their included allowances, generating overage charges
Despite the higher base fee of Ultimate, the revenue difference is statistically confirmed
Geographic region (NY-NJ vs. other) does not significantly impact revenue generation


# Business Recommendations

Prioritize advertising budget toward the Ultimate plan — it yields significantly higher revenue per user
Monitor Surf plan overages — a segment of Surf users consistently exceed limits, making them strong upgrade candidates
Regional campaigns are not justified by revenue differences — marketing efforts should focus on plan type rather than geography
