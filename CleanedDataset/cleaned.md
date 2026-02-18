# Data Cleaning and Preparation Log

## Overview

This document tracks all data cleaning and preparation steps performed on the raw dataset to create the final cleaned dataset for customer retention analysis.

---

## Cleaning Timeline

| Date | Action Taken | Rows Affected | Rationale |
|------|--------------|---------------|-----------|
| 16/02/2026 | Initial Setup | 10,000 | Created Cleaned_Data sheet and standardized headers |
| 16/02/2026 | Remove Duplicates | 0 | Removed exact row duplicates to prevent double-counting sales |
| 16/02/2026 | Format Standardization | 10,000 | Converted Date and Price columns to numeric formats for calculation |
| 16/02/2026 | Guest Segregation | 2,459 | Moved rows with missing customer_id to "Guest" tab - cannot perform retention analysis on unidentified users |
| 16/02/2026 | Junk Artifact Removal | 209 | Removed non-product SKUs (Postage, Bank Charges) to ensure product analysis only reflects retail items |
| 16/02/2026 | Feature Engineering | 10,000 | Created 'total_line_value' (Qty × Price) to calculate Monetary value for RFM |
| 16/02/2026 | Aggregation | 2,412 | Created Pivot Table to aggregate data by Customer ID for RFM analysis |
| 16/02/2026 | Feature Engineering | 1,384 | Calculated 'Recency' as (Reference Date - Last Purchase Date). Reference Date set to 2011-12-10 |
| 16/02/2026 | Feature Engineering | 1,384 | Calculated R, F, and M scores (1-5 scale) using Quintile (PercentRank) methodology |
| 16/02/2026 | Segmentation | 1,384 | Applied logic-based rules to group customers into 'Champions', 'Lost', etc. based on R and F scores |
| 16/02/2026 | Visualization | N/A | Created Dashboard with Segment Distribution (Bar), Revenue Share (Pie), and RF Matrix (Scatter) to visualize insights |
| 16/02/2026 | KPI Calculation | All Customers | Calculated high-level metrics: Total Revenue (£151k), Total Customers (1,383), and ARPU (£109) for executive summary |
| 16/02/2026 | Dashboard Construction | N/A | Assembled 'Customer Retention Dashboard' integrating KPI Scorecards, Segmentation Charts, and RFM Matrix |
| 16/02/2026 | Interactivity | N/A | Implemented Slicers on 'Customer_Segment' to allow dynamic filtering of all dashboard visualizations |
| 16/02/2026 | Final Validation | N/A | Cross-referenced Dashboard totals against raw data to ensure accuracy (Checksum validation) |

---

## Data Quality Summary

### Records Processed

| Stage | Record Count | Change |
|-------|--------------|--------|
| Initial Raw Data | 10,000 | - |
| After Duplicate Removal | 10,000 | 0 removed |
| After Guest Segregation | 7,541 | 2,459 removed |
| After Junk Removal | 7,332 | 209 removed |
| Final Cleaned Dataset | 7,332 | - |

### Data Quality Issues Addressed

| Issue | Count | Resolution |
|-------|-------|------------|
| Missing Customer IDs | 2,459 | Segregated to separate "Guest" tab |
| Non-product SKUs | 209 | Removed (Postage, Bank Charges) |
| Duplicate Records | 0 | None found |
| Format Inconsistencies | 10,000 | Standardized date and price formats |

---

## Feature Engineering

### Derived Columns

| Column Name | Formula | Purpose |
|-------------|---------|---------|
| total_line_value | Quantity × Price | Calculate transaction monetary value |
| Recency | Reference Date - Last Purchase Date | RFM Analysis - Recency score |
| Frequency | Count of transactions per customer | RFM Analysis - Frequency score |
| Monetary | Sum of total_line_value per customer | RFM Analysis - Monetary score |
| R_Score | Quintile ranking (1-5) | RFM segmentation |
| F_Score | Quintile ranking (1-5) | RFM segmentation |
| M_Score | Quintile ranking (1-5) | RFM segmentation |

### RFM Scoring Methodology

**Reference Date:** 2011-12-10

**Scoring Scale:** 1-5 (using Quintile/PercentRank)
- 5 = Best (Most recent, Most frequent, Highest monetary)
- 1 = Worst (Least recent, Least frequent, Lowest monetary)

---

## Customer Segmentation

### Segment Definitions

| Segment | R Score | F Score | Customer Count | Strategy |
|---------|---------|---------|----------------|----------|
| Champions | 4-5 | 4-5 | TBD | VIP treatment, exclusive offers |
| Loyal Customers | 3-5 | 3-5 | TBD | Loyalty programs, rewards |
| Potential Loyalists | 3-5 | 1-2 | TBD | Engagement campaigns |
| At Risk | 1-2 | 3-5 | TBD | Win-back campaigns |
| Lost | 1-2 | 1-2 | TBD | Reactivation efforts |

---

## Dashboard Components

### KPI Scorecards

| KPI | Value | Description |
|-----|-------|-------------|
| Total Revenue | £151,000 | Sum of all transaction values |
| Total Customers | 1,383 | Unique customer count |
| ARPU | £109 | Average Revenue Per User |

### Visualizations Created

1. **Segment Distribution (Bar Chart)** - Customer count by segment
2. **Revenue Share (Pie Chart)** - Revenue contribution by segment
3. **RF Matrix (Scatter Plot)** - Recency vs Frequency visualization
4. **Interactive Slicers** - Filter by Customer_Segment

---

## Validation Checks

| Check | Status | Notes |
|-------|--------|-------|
| Checksum Validation | Passed | Dashboard totals match raw data |
| Data Type Consistency | Passed | All columns have correct data types |
| Missing Value Check | Passed | No unexpected nulls in cleaned data |
| Duplicate Check | Passed | No duplicate records found |
| Calculation Accuracy | Passed | total_line_value = Quantity × Price verified |

---

## Files Generated

| File | Records | Description |
|------|---------|-------------|
| cleanedSheet1.csv | 9,999 | Main cleaned dataset (2009-2010) |
| cleanedSheet2.csv | 7,495 | Secondary cleaned dataset (2010) |
| Guest_Transactions.csv | 2,459 | Transactions without customer IDs |
| RFM_Aggregated.csv | 1,384 | Customer-level RFM scores |

---

## Notes

- Reference date for Recency calculation: 2011-12-10
- RFM scoring uses quintile methodology for fair distribution
- Guest transactions excluded from retention analysis but retained for revenue reporting
- Non-product items (Postage, Bank Charges) removed to focus on retail product performance

---

**Last Updated:** 16/02/2026  
**Prepared By:** Section A - Group 14  
**Status:** Final
