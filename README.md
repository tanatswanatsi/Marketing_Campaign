# Marketing_Campaign
Interactive Excel dashboard analyzing a customer marketing campaign dataset (2,240 customers) with PivotTables, PivotCharts, and slicers. Explores campaign response, spending by education and marital status. Key finding: PhD holders had a 20.8% response rate — over 5x higher than customers with only Basic education (3.7%).

# Customer Marketing Campaign Dashboard

## Overview
An interactive Excel dashboard analyzing a customer personality and marketing campaign 
dataset (2,240 customers), built with PivotTables, PivotCharts, and slicers to explore 
campaign response, spending behavior, and demographics.

## Dataset
Customer-level data including demographics (education, marital status, income, 
household composition), purchase history across 6 product categories (wine, fruit, 
meat, fish, sweets, gold), purchase channel (web, catalog, store, deals), and whether 
the customer accepted the most recent marketing campaign offer.

## Process

### Data Cleaning
- Verified no duplicate rows or duplicate customer IDs
- Converted enrollment date (`Dt_Customer`) to a true date value
- Recoded 7 non-standard entries ("YOLO," "Absurd," "Alone") in Marital Status to "Single"
- Found and corrected 3 impossible birth years (1893, 1899, 1900 — would imply ages over 
  115) by setting them to blank rather than guessing a replacement value
- Found and corrected one extreme income outlier ($666,666) by setting it to blank
- Added two helper columns: `Age` (derived from birth year) and `TotalSpend` 
  (sum across all 6 product categories)
- **Data quality lesson learned mid-project:** an earlier version of this workbook had 
  explanatory text notes placed just below the data table, which got accidentally pulled 
  into PivotTables built from a full-column selection, creating phantom "(blank)" entries. 
  Fixed by rebuilding PivotTables from the exact bounded table range.

### Exploratory Analysis — PivotTables & Charts
1. **Response Overview** — overall campaign acceptance rate
2. **Income & Spend by Education** — average income and spending by education level
3. **Spending by Marital Status** — average total spend by relationship status
4. **Response by Education** — campaign acceptance rate by education level

## Key Insights

**Only 14.9% of customers accepted the campaign offer** (334 of 2,240) — the large 
majority of the customer base did not respond to this marketing push.

**Education level is a strong predictor of both income and spend.** PhD holders had 
both the highest average income ($56,145) and the highest average total spend ($672), 
while customers with only "Basic" education had dramatically lower figures on both — 
average income of $20,306 (less than half of every other group) and average spend of 
just $82, roughly 8x lower than any other education tier.

**Education also strongly predicts campaign response.** PhD holders accepted the 
campaign at nearly 21% — more than 5x the acceptance rate of Basic-education customers 
(3.7%), and meaningfully ahead of every other group. Response rate tracks education 
level almost perfectly: PhD (20.8%) > Master (15.4%) > Graduation (13.5%) > 2n Cycle 
(10.8%) > Basic (3.7%).

**Widowed customers spend the most, not married ones.** Despite being the smallest 
marital-status group by far (77 customers vs. 864 Married), Widowed customers had the 
highest average spend ($739) — notably higher than every other group, including 
Married, which came in lowest ($591) despite being the largest segment.

**Household composition has a major impact on spend.** Customers with no children at 
home spent an average of $901 — more than 4x the $205 average for customers with one 
child, and over 6x the $145 average for those with two children. Having kids at home 
appears to be one of the single strongest spending-suppression factors in this dataset.

**Store remains the dominant purchase channel.** Of all recorded purchases, Store 
accounted for 12,970 — more than Web (9,150), Catalog (5,963), and Deals-driven 
purchases (5,208) combined is close but store still leads clearly as the single 
largest channel.

## Recommendations

- **Target future campaigns toward higher-education segments**, particularly PhD and 
  Master's-level customers, who show both higher spend and dramatically higher response 
  rates — the current 14.9% blanket acceptance rate could likely be improved by 
  segmenting campaign offers rather than treating all education levels the same.
- **Investigate the Basic-education segment separately before marketing to them the 
  same way.** Their income, spend, and response rate are all dramatically lower than 
  every other group — a different offer structure (lower price point, different 
  product focus) may be more effective than repeating the standard campaign.
- **Build a retention/loyalty focus around Widowed customers.** Despite being a small 
  segment, they're the highest spenders per customer — worth understanding what's 
  driving this and whether it can inform offers to other segments.
- **Consider family-targeted bundles or value offers for customers with children at 
  home.** The sharp spend drop-off with each additional child suggests budget 
  constraints are a major factor — product bundles or value-tier offers could re-engage 
  this large, currently under-spending segment.
- **Continue investing in the Store channel while growing Web.** Store leads all 
  channels, but Web is a strong second — worth examining whether specific products or 
  segments are more Web-oriented, to guide channel-specific promotion.

## Tools Used
Microsoft Excel — PivotTables, PivotCharts, Slicers, COUNTIFS/AVERAGEIFS/SUMIFS formulas

## How to Use
Download the file and open in Excel. Use the slicers (Education, Marital Status, 
Response) to filter the entire dashboard interactively.
