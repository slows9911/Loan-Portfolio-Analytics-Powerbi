# Loan Portfolio Analytics Dashboard — Power BI

End-to-end Power BI analytics solution for a multi-year loan portfolio, featuring a star-schema data model, DAX-driven KPIs, and executive dashboards for loan performance, delinquency, and collections tracking.

[Dashboard Overview]
<img width="1031" height="586" alt="Screenshot 2026-07-24 at 2 34 13 PM" src="https://github.com/user-attachments/assets/da8a3986-211b-4716-acd8-7d047d00d8eb" />
)
<img width="1020" height="551" alt="Screenshot 2026-07-24 at 2 30 24 PM" src="https://github.com/user-attachments/assets/dcc69610-630e-4b45-b582-782bb30d8818" />
<img width="999" height="548" alt="Screenshot 2026-07-24 at 2 30 09 PM" src="https://github.com/user-attachments/assets/6890235f-a069-44a3-beef-f2ddfa38f73a" />
<img width="988" height="547" alt="Screenshot 2026-07-24 at 2 29 52 PM" src="https://github.com/user-attachments/assets/36e68500-9b5e-44c9-b097-2b4ec08d6751" />
<img width="1002" height="550" alt="Screenshot 2026-07-24 at 2 29 35 PM" src="https://github.com/user-attachments/assets/881bb1d0-a820-4175-b41d-465ce536d379" />
<img width="235" height="168" alt="Screenshot 2026-07-24 at 2 29 25 PM" src="https://github.com/user-attachments/assets/d950acb2-3d5b-41aa-ac3d-340b9860e1dd" />





## Business Problem

Loan portfolio managers and executives lacked a unified, interactive view of loan performance, collections activity, delinquency risk, and branch-level trends across a multi-year loan book. This dashboard consolidates fragmented reporting into a single governed analytics layer, giving leadership real-time visibility into portfolio health and customer credit quality.

## Data Model

Built on a star-schema dimensional model to optimize performance and ensure accurate cross-filtering across all report pages.

**Fact Table**
- `Loans` — loan-level transactional data

**Dimension Tables**
- `Customers` — borrower profile and credit attributes
- `Payments` — payment history and transaction detail
- `Collections` — collections activity and outcomes
- `Branches` — branch/location attributes
- `Date` — standard date dimension for time intelligence

![Data Model View]

<img width="999" height="542" alt="Screenshot 2026-07-24 at 2 37 12 PM" src="https://github.com/user-attachments/assets/8b42404f-2996-4598-8738-93f4f716711b" />

## Key Metrics & DAX Measures

Core KPIs built using advanced DAX, including dynamic time-intelligence calculations:

- **Total Loan Balance**
- **Active Loans**
- **Total Collections**
- **Delinquency Rate**
- **Average Credit Score**
- **Year-over-Year (YoY) Trends**

Example measure:

```dax
Delinquency Rate = 
DIVIDE(
    CALCULATE([Active Loans], Loans[Status] = "Delinquent"),
    [Active Loans],
    0
)
```

```dax
Loan Balance YoY % = 
VAR CurrentBalance = [Total Loan Balance]
VAR PriorYearBalance = CALCULATE([Total Loan Balance], SAMEPERIODLASTYEAR('Date'[Date]))
RETURN
DIVIDE(CurrentBalance - PriorYearBalance, PriorYearBalance, 0)
```

## Features

- Interactive drill-through pages for loan-level and branch-level detail
- Dynamic filtering and slicers across all report pages
- KPI scorecards with conditional formatting for at-a-glance risk flags
- Executive-level summary visualizations for leadership reporting
- Reusable, optimized DAX measures for consistent logic across pages

![Drill-Through Page]
<img width="1032" height="589" alt="Screenshot 2026-07-24 at 2 39 32 PM" src="https://github.com/user-attachments/assets/ac3fe59e-0575-4e48-a2e2-3321f7f57176" />

## Tools Used

- Power BI Desktop
- DAX (Data Analysis Expressions)
- Power Query
- Star Schema / Dimensional Modeling

## How to Explore This Project

1. Download '(https://github.com/slows9911/Loan-Portfolio-Analytics-Powerbi/blob/Master/Portforlio.pbix)' from this repository
2. Open it in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
4. Explore the report pages, drill-throughs, and data model via the Model view

## Data Disclaimer

All data used in this project is sample/synthetic and does not represent real customer, loan, or financial records.

---

**Author:** Joseph Oyebade
**Connect:** [LinkedIn](www.linkedin.com/in/joseph-oyebade) | [GitHub](https://github.com/slows9911)
