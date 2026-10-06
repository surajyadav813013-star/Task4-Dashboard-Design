# Task 4: Dashboard Design | Elevate Labs Data Analyst Internship

## Objective
Design an interactive Power BI dashboard that helps business stakeholders track Sales, Profit, and Growth.

## Tools
Power BI Desktop, DAX, Excel

## Dataset
Sample Superstore (Kaggle): https://www.kaggle.com/datasets/vivek468/superstore-dataset-final
Rows: 9,994 | Period: 2014-2017 | Key columns: Order Date, Region, Category, Sales, Profit, Quantity

## Dashboard Features
- **KPI Cards:** Total Sales, Total Profit, Profit Margin %, Total Orders
- **Time-Series Analysis:** Monthly sales and profit trend with YoY growth
- **Slicers/Filters:** Year, Region, Category
- **Visuals:** Sales by Category, Profit by Region, Top 10 Products
- **Navigation Menu:** Page buttons (Overview, Trends, Products)
- **Consistent Theme:** Navy/blue palette across all pages

## DAX Measures
```DAX
Total Sales = SUM(Sales[Sales])
Total Profit = SUM(Sales[Profit])
Profit Margin % = DIVIDE([Total Profit], [Total Sales])
YoY Growth % =
VAR PrevSales = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date]))
RETURN DIVIDE([Total Sales] - PrevSales, PrevSales)
```

## Key Insights
1. West is the top region by sales and profit; Technology is the top profit category
2. Furniture has the lowest margin (about 2.5%) despite high sales
3. Sales grew about 20% in 2017, with a consistent Q4 peak

## Repository Structure
```
├── Task4_Dashboard.pbix
├── Task4_Summary.pptx
├── dataset/
├── screenshots/
└── README.md
```

## Screenshots
![Overview](screenshots/overview.png)
![Trends](screenshots/trends.png)

## Interview Questions

**1. What are the key elements of a dashboard?**
KPI cards, charts, slicers/filters, consistent layout and theme, and clear titles.

**2. What is a KPI?**
A measurable value that shows progress toward a business goal, such as Profit Margin %.

**3. What are slicers in Power BI?**
Visual filters that let users filter all visuals on a page with a click.

**4. Difference between Power BI and Tableau?**
Power BI is cheaper, integrates with Microsoft tools, and uses DAX. Tableau has stronger visual customization and handles complex visuals well.

**5. How do you make a dashboard interactive?**
Slicers, cross-filtering, drill-through, tooltips, bookmarks, and navigation buttons.

**6. How do you deal with large datasets in dashboards?**
Import mode with aggregations, remove unused columns, use a star schema, and use incremental refresh.

**7. What chart types do you use for trend analysis?**
Line chart, area chart, and combo chart (bars plus line).

## Author
Suraj Yadav | [GitHub](https://github.com/surajyadav813013-star)
