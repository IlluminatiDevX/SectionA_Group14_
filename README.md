# Strategic Customer Retention Analysis

## Project Overview

Data-driven customer retention analysis for an online retail business (Dec 2009 - Dec 2010).

| Metric | Value |
|--------|-------|
| Total Revenue | £589,689 |
| Unique Customers | 2,494 |
| Transactions | 17,494 |
| Average Order Value | £58.97 |
| Return Rate | 22.1% |
| Time Period | 13 months |

---

## Dataset Information

### Raw Data

| Dataset | Records | Columns | Period |
|---------|---------|---------|--------|
| dataset1.csv | 525,461 | 8 | Dec 2009 - Jan 2010 |
| dataset2.csv | 541,910 | 8 | Dec 2010 |
| **Total** | **1,067,371** | **8** | **13 months** |

### Cleaned Data

| Dataset | Records | Columns |
|---------|---------|---------|
| cleanedSheet1.csv | 9,999 | 9 |
| cleanedSheet2.csv | 7,495 | 9 |
| **Total** | **17,494** | **9** |

---

## Directory Structure

```
SectionA_Group14_/
├── RawDataset/
│   ├── dataset1.csv
│   └── dataset2.csv
├── CleanedDataset/
│   ├── cleanedSheet1.csv
│   ├── cleanedSheet2.csv
│   └── cleaned.md
├── Calculation&Pivot/
│   ├── 2009-10/
│   └── 2010-11/
├── Dashboard/
├── Presentation/
│   └── Strategic_Customer_Retention_Report.pdf
├── README.md
└── PPT_Generation_Prompt.md
```

---

## Column Specifications

### Data Dictionary

| Column | Type | Description | Null Count | Unique Values |
|--------|------|-------------|------------|---------------|
| Invoice | String | Transaction ID | 0 | 25,900 |
| StockCode | String | Product code | 0 | 4,070 |
| Description | String | Product name | 1,454 | 4,223 |
| Quantity | Integer | Units purchased | 0 | 722 |
| InvoiceDate | DateTime | Transaction timestamp | 0 | 23,260 |
| Price | Float | Unit price (GBP) | 0 | 1,630 |
| Customer ID | Integer | Customer identifier | 135,080 | 4,372 |
| Country | String | Customer country | 0 | 38 |

### Derived Columns

| Column | Formula | Type | Description |
|--------|---------|------|-------------|
| Total_Value | Quantity × Price | Float | Transaction total |
| transaction_date | Parsed InvoiceDate | Date | Standardized date |

---

## Statistical Analysis

### Numerical Summary

| Metric | Quantity | Price (£) | Total_Value (£) |
|--------|----------|-----------|-----------------|
| Mean | 5.32 | 3.46 | 58.97 |
| Std Dev | 8.91 | 4.23 | 142.35 |
| Min | -80 | 0.00 | -433.24 |
| Median | 3 | 2.10 | 21.00 |
| Max | 600 | 649.50 | 8,142.75 |

### Categorical Summary

| Column | Unique | Most Frequent | Frequency |
|--------|--------|---------------|-----------|
| Country | 38 | United Kingdom | 6,912 (69%) |
| StockCode | 3,684 | 85123A | 58 |
| Customer ID | 2,494 | 14911 | 106 |

---

## Key Findings

### Customer Segmentation

| Tier | Count | % | Avg Spend | Revenue |
|------|-------|---|-----------|---------|
| High (>£1,000) | 42 | 1.7% | £1,847 | £77,574 |
| Medium (£200-£1,000) | 113 | 4.5% | £458 | £51,754 |
| Low (<£200) | 2,339 | 93.8% | £197 | £460,361 |

### Geographic Performance

| Region | Transactions | Revenue | AOV |
|--------|--------------|---------|-----|
| UK | 6,912 | £133,133 (22.6%) | £19.26 |
| International | 3,087 | £456,556 (77.4%) | £147.91 |
| Germany | 146 | £68,234 | £467.36 |
| France | 101 | £52,118 | £516.02 |

### Top Products

| Product | Orders | Revenue |
|---------|--------|---------|
| White Hanging Heart T-Light Holder | 58 | £2,847 |
| Jumbo Bag Red Retrospot | 52 | £1,014 |
| Paper Chain Kit 50's Christmas | 48 | £1,416 |

### Return Analysis

| Metric | Value |
|--------|-------|
| Return Rate | 22.1% (vs 8-10% industry) |
| Return Transactions | 2,214 |
| Return Value | £292,150 |
| Potential Savings | £146,075 (if reduced to 10%) |

---

## Analysis Suggestions

| Analysis | Purpose |
|----------|---------|
| RFM Segmentation | Customer behavior classification |
| Cohort Analysis | Retention tracking |
| Market Basket | Cross-sell opportunities |
| Churn Prediction | Identify at-risk customers |
| Seasonal Forecasting | Demand prediction |

---

## Data Integrity Summary

### Quality Metrics

| Check | Raw | Cleaned | Action |
|-------|-----|---------|--------|
| Total Records | 1,067,371 | 17,494 | Filtered |
| Missing Customer IDs | 135,080 | 0 | Removed |
| Duplicates | 156 | 0 | Removed |
| Invalid Prices | 34 | 0 | Corrected |
| Negative Quantities | 8,905 | 2,214 | Flagged |
| Completeness | 87.3% | 100% | Cleaned |

### Cleaning Steps

| Step | Records Affected |
|------|------------------|
| Remove missing Customer IDs | 135,080 |
| Flag return transactions | 2,214 |
| Remove duplicates | 156 |
| Standardize countries | 89 |
| Validate prices | 34 |
| Calculate Total_Value | 17,494 |

---

## Team Information

**Project:** Strategic Customer Retention Analysis  
**Team ID:** Section A - Group 14  
**Sector:** E-Commerce Retail  
**Period:** 2024-2025

---

**Version:** 1.0  
**Status:** Final Submission
