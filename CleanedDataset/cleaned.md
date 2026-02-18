Date	Action Taken	Rows Affected	Rationale
16/02/2026	Initial Setup	10,000	Created Cleaned_Data sheet and standardized headers.
16/02/2026	Remove Duplicates	0	Removed exact row duplicates to prevent double-counting sales.
16/02/2026	Format Standardization	10,000	Converted Date and Price columns to numeric formats for calculation.
16/02/2026	Guest Segregation	2459	Moved rows with missing customer_id to "Guest" tab. Cannot perform retention analysis on unidentified users.
16/02/2026	Junk Artifact Removal	209	Removed non-product SKUs (Postage, Bank Charges) to ensure product analysis only reflects retail items.
16/02/2026	Feature Engineering	10,000	Created 'total_line_value' (Qty * Price) to calculate Monetary value for RFM.
16/02/2026	Aggregation	2412	Created Pivot Table to aggregate data by Customer ID for RFM analysis.
16/02/2026	Feature Engineering	1384	Calculated 'Recency' as (Reference Date - Last Purchase Date). Reference Date set to 2011-12-10.
16/02/2026	Feature Engineering	1384	Calculated R, F, and M scores (1-5 scale) using Quintile (PercentRank) methodology.
16/02/2026	Segmentation	1384	Applied logic-based rules to group customers into 'Champions', 'Lost', etc. based on R and F scores.
16/02/2026	Visualization	N/A	Created Dashboard with Segment Distribution (Bar), Revenue Share (Pie), and RF Matrix (Scatter) to visualize insights.
16/02/2026	KPI Calculation	All Customers	Calculated high-level metrics: Total Revenue (£151k), Total Customers (1,383), and ARPU (£109) for executive summary.
16/02/2026	Dashboard Construction	N/A	Assembled 'Customer Retention Dashboard' integrating KPI Scorecards, Segmentation Charts, and RFM Matrix.
16/02/2026	Interactivity	N/A	Implemented Slicers on 'Customer_Segment' to allow dynamic filtering of all dashboard visualizations.
16/02/2026	Final Validation	N/A	Cross-referenced Dashboard totals against raw data to ensure accuracy (Checksum validation).