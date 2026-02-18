# Restaurant Business Performance & Operational Optimization Analysis

## 1. Project Overview

This project analyzes restaurant transactional sales data to evaluate revenue structure, operational efficiency, customer satisfaction, and strategic growth opportunities.

The objective was not only to calculate performance metrics but to assess the structural health of the revenue model and identify high-impact optimization levers.

Time Period Analyzed: 2022–2023  
Total Transactions Analyzed: 9,015  
Total Revenue: $180,124.5  

---

## 2. Business Problem Statement

Although the restaurant generates significant revenue, management lacks clarity on:

- Revenue concentration risks
- Channel performance imbalance
- Customer satisfaction trends
- Sensitivity of revenue to operational changes
- Strategic levers for sustainable growth

This analysis transforms raw transaction data into structured decision insights.

---

## 3. Dataset Description

Source: Kaggle – Restaurant Sales Dirty Dataset  
Structure: Row-level transactional dataset  

### Columns:

- Order ID
- Customer ID
- Category
- Item
- Price (In $)
- Quantity
- Order Total (In $)
- Order Date
- Payment Method
- Rating
- Order Type

---

## 4. Data Quality Assessment (Raw Data)

Before cleaning:

- Missing Item values detected
- Missing Payment Method entries
- Missing Rating entries
- Missing Order Type entries
- Numeric columns stored as text
- Inconsistent capitalization in text fields

Raw data was preserved in the `RawDataset` folder.

---

## 5. Data Cleaning & Transformation Methodology

All cleaning was performed using formula-driven transformations to preserve auditability.

### 5.1 Missing Value Handling

- Rows with missing Item were removed (non-recoverable key field).
- Payment Method blanks replaced using Mode.
- Rating blanks replaced using Median (3).
- Order Type blanks replaced using Mode.

### 5.2 Data Type Standardization

- Numeric columns converted using VALUE().
- Text standardized using PROPER(TRIM()).
- Date formatted consistently for time-series analysis.

### 5.3 Derived Features

- Month-Year column created using:
  TEXT(OrderDate, "MMM-YYYY")

- This enabled monthly trend analysis.

---

## 6. KPI Framework & Definitions

The following KPIs were defined to assess performance:

### Financial KPIs

- Total Revenue = SUM(Order Total)
- Total Transactions = COUNT(Order ID)
- Average Order Value (AOV) = Total Revenue / Total Transactions
- Highest Order Value = MAX(Order Total)

### Operational KPIs

- Revenue by Category
- Revenue by Order Type
- Revenue by Payment Method
- Quantity Sold per Item
- Revenue per Customer

### Customer KPIs

- Average Rating = AVERAGE(Rating)
- Most Valuable Customer = Customer with highest cumulative revenue
- Most Ordered Item = Item with highest total quantity sold

---

## 7. KPI Analysis & Insights

### 7.1 Revenue Overview

- Total Revenue: $180,124.5
- Average Order Value: $19.98
- Total Orders: 9,015

Revenue generation is stable but shows limited organic growth momentum.

---

### 7.2 Revenue by Category

- Main Dishes contribute 47% of total revenue.
- Revenue concentration indicates moderate dependency risk.
- Diversification strategy recommended.

---

### 7.3 Revenue by Order Type

- Takeaway contributes 49.43% of revenue.
- Delivery and Dine-In show balanced but secondary contribution.
- Channel dependency suggests operational leverage risk.

---

### 7.4 Payment Method Analysis

- Cash accounts for highest share.
- Digital and Card are nearly balanced.
- Opportunity to promote digital payment incentives.

---

### 7.5 Customer & Product Insights

- Revenue moderately concentrated among repeat customers.
- Pasta Alfredo identified as top revenue-generating item.
- Item-level performance analysis reveals sales imbalance.

---

### 7.6 Customer Satisfaction

- Average Rating: 2.98/5
- Rating below industry benchmark.
- Indicates service quality or experience gap.
- Long-term retention risk exists.

---

## 8. Advanced Analytical Insights

### 8.1 Revenue Concentration Risk

Top categories and items drive disproportionate revenue share, increasing vulnerability to demand shifts.

---

### 8.2 Revenue Sensitivity Modeling

Scenario Simulations:

- $1 decline in AOV → ~$9,015 annual revenue impact.
- 10% decline in Main Dish revenue → ~$8,517 impact.

This demonstrates operational leverage sensitivity.

---

## 9. Strategic Recommendations

1. Improve Customer Experience to raise rating above 4.0.
2. Increase AOV through bundle pricing and cross-selling.
3. Diversify revenue streams across categories.
4. Optimize Takeaway efficiency.
5. Strengthen POS validation for improved data reliability.

---

## 10. Dashboard Architecture

The Dashboard includes:

- KPI Summary Cards
- Revenue by Category
- Revenue by Order Type
- Revenue by Payment Method
- Monthly Revenue Trend
- Quantity Sold per Item
- Revenue per Customer
- Average Rating by Category

The dashboard dynamically updates when new data is added to Clean_data.

---

## 11. Limitations

- No cost or profit data available.
- No customer demographic data.
- No repeat visit tracking.
- Analysis limited to revenue-level insights.

---

## 12. Repository Structure

RawDataset/  
Cleaned/  
Calculations_Pivots/  
Dashboard/  

Root Files:
- Documentation.pdf
- Presentation.pdf
- README.md

---

## 13. Team Contribution

All team members contributed across:

- Dataset sourcing
- Cleaning & transformation
- KPI framework development
- Pivot table construction
- Dashboard design
- Strategic analysis
- Report preparation
- Presentation development
