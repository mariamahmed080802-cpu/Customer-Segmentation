# Customer Segmentation using RFM Analysis

## Project Overview

This project performs **customer segmentation using RFM (Recency,
Frequency, Monetary) analysis** on the Online Retail dataset.

The goal is to analyze customer purchasing behavior and divide customers
into meaningful segments that help businesses understand: - Who their
**best customers** are - Which customers are **at risk of churning** -
Which customers are **loyal and generate consistent revenue**

The analysis includes **data cleaning, exploratory data analysis (EDA),
RFM scoring, and customer segmentation**.

------------------------------------------------------------------------

# Dataset Description

The dataset contains online retail transactions including:

-   Invoice number
-   Product (StockCode)
-   Product description
-   Quantity purchased
-   Invoice date
-   Price
-   Customer ID
-   Country

Each row represents a **transaction of a product within an invoice**.

------------------------------------------------------------------------

# Data Cleaning

## Handling Missing Values

Rows with missing **Customer ID** were removed because customer
identification is required for segmentation.

## Removing Duplicate Records

Duplicate rows were identified and removed.

## Fixing Data Types

-   `InvoiceDate` converted to datetime
-   `CustomerID` converted to string

## Revenue Calculation

A revenue column was created:

Revenue = Quantity × Price

## Removing Cancelled Orders

Invoices starting with **C** indicate cancelled transactions and were
removed.

## Standardizing Product Descriptions

Some products had multiple descriptions. The **longest description for
each StockCode** was selected and used to standardize product names.

------------------------------------------------------------------------

# Exploratory Data Analysis

## Country Sales Analysis

Revenue was aggregated by country.

**Insight:** The United Kingdom dominates total sales, indicating that
the retailer primarily operates in this market.

## Monthly Sales Trend

Monthly revenue was analyzed using the invoice date.

**Insight:** Sales increase significantly during the holiday season
toward the end of the year.

------------------------------------------------------------------------

# RFM Analysis

RFM analysis segments customers based on:

  Metric      Meaning
  ----------- -----------------------------------------
  Recency     Days since the customer's last purchase
  Frequency   Number of orders made
  Monetary    Total amount spent

------------------------------------------------------------------------

# RFM Calculation

A snapshot date was defined as one day after the last transaction.

Recency, Frequency, and Monetary values were then calculated for each
customer.

------------------------------------------------------------------------

# RFM Scoring

Customers were scored from **1 to 5** based on quantiles.

-   **Recency Score:** Lower recency receives higher scores.
-   **Frequency Score:** Higher purchase frequency receives higher
    scores.
-   **Monetary Score:** Higher spending receives higher scores.

The three scores were combined into an **RFM Score**.

Example:

-   `555` → Best customers
-   `111` → Lowest engagement customers

------------------------------------------------------------------------

# Customer Segmentation

Customers were segmented using their RFM scores into groups such as:

-   Champions
-   Loyal Customers
-   Potential Loyalists
-   At Risk
-   Lost Customers

------------------------------------------------------------------------

# Key Insights

## Market Concentration

The majority of sales come from the **United Kingdom**.

## Seasonal Demand

Sales increase significantly toward the **end of the year**, indicating
strong holiday demand.

## Customer Value Distribution

Customer spending varies widely: - Some customers purchase frequently
and spend large amounts. - Others purchase rarely or have stopped
purchasing.

## High Value Customers

**Champions and Loyal Customers generate the largest share of revenue.**

## At-Risk Customers

Customers who used to purchase frequently but haven't bought recently
are identified as **At Risk**, providing opportunities for targeted
retention campaigns.

------------------------------------------------------------------------

# Visualizations Included

The project includes visualizations such as:

-   Top Countries by Revenue
-   Monthly Revenue Trends
-   Recency Distribution
-   Frequency Distribution
-   Monetary Distribution
-   Customer Segment Distribution
-   Revenue Contribution by Segment
-   RFM Heatmap

------------------------------------------------------------------------

# Project Outcome

This project demonstrates how **RFM analysis can be used to segment
customers and generate actionable business insights**.

Businesses can use these insights to: - Reward **loyal customers** -
Re-engage **at-risk customers** - Identify **high-value customers** -
Improve **marketing strategies using data-driven decisions**

------------------------------------------------------------------------

# Recommended Actions

- Reward Champions: Offer loyalty programs, exclusive deals, and personalized offers to retain high-value customers.
- Engage Loyal & Potential Customers: Encourage repeat purchases through targeted promotions, recommendations, and incentives.
- Re-engage At-Risk Customers: Launch win-back campaigns to bring back previously active buyers.
- Manage Low-Value/Lost Customers: Minimize marketing spend on inactive buyers, focus resources on higher-value segments.
- Plan Seasonal & Regional Campaigns: Leverage holiday peaks and top-performing countries to maximize revenue.

------------------------------------------------------------------------

# Tools & Technologies

-   Python
-   Pandas
-   NumPy
-   Matplotlib
-   Seaborn
-   Jupyter Notebook
