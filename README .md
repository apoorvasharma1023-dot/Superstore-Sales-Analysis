# Superstore Sales Analysis --- EDA & Visualization

## Project Overview

This project analyzes a Superstore-style sales dataset using Python,
pandas, Matplotlib, and Seaborn.

The goal was to practice a repeatable exploratory data analysis and
visualization workflow:

**Understand → Clean → Explore → Visualize → Interpret → Communicate**

The project focuses on turning visualizations into business insights
rather than simply creating charts.

## Dataset

-   **Rows:** 9,800
-   **Columns:** 18
-   **Date range:** 2015-01-03 to 2018-12-30
-   **Main metric:** Sales

Important fields include Order ID, Order Date, Ship Mode, Segment,
Region, Category, Sub-Category, Product Name, and Sales.

## Tools

-   Python
-   Pandas
-   Matplotlib
-   Seaborn
-   Jupyter Notebook
-   Excel

## Analysis Performed

### 1. Data Understanding

We inspected the dataset shape, columns, data types, categorical
variables, and date information.

Repeated Order IDs were not treated as duplicate rows because one order
can contain multiple order lines.

### 2. Data Cleaning

-   Checked completely duplicated rows: **0**
-   Checked missing values.
-   `Postal Code` had **11 missing values (\~0.11%)**.
-   The missing postal-code rows were retained because the missingness
    was extremely small and the column was not required for the main
    sales analysis.
-   Converted `Order Date` to datetime.
-   Converted `Postal Code` to a nullable integer type.

### 3. Sales Distribution

We used a histogram and boxplot to understand Sales.

**Insight:** Sales are strongly right-skewed. Most transactions have
relatively low sales values, while a smaller number of transactions have
very high values.

### 4. Category Analysis

We compared order counts and total sales by Category.

**Insight:** Office Supplies has the highest order-line volume, while
Technology generates strong total sales despite having fewer order
lines.

This demonstrates that **order frequency and revenue answer different
business questions**.

### 5. Sub-Category Analysis

We compared both order counts and total sales by Sub-Category.

**Insights:** - Binders has the highest order-line count. - Phones has
the highest total sales. - Fasteners has the lowest total sales. -
Copiers has one of the lowest order counts.

This shows why frequency alone should not be used to judge business
performance.

### 6. Regional Analysis

We compared total sales across the four regions.

**Insight:** West has the strongest overall sales performance, while
South has the lowest.

This led to follow-up questions about product mix, category performance,
and customer segments by region.

### 7. Category × Region Analysis

A pivot table and heatmap were used to compare categories across
regions.

**Key insights:** - Technology + East was the strongest combination at
approximately **₹263K**. - Furniture + South was the weakest combination
at approximately **₹117K**.

The visualization shows the difference, but not its cause. Possible
explanations such as regional demand or product mix would need further
analysis.

### 8. Time-Series Analysis

We analyzed daily, monthly, and yearly sales.

**Insights:** - Sales showed an overall upward trend from 2015 to
2018. - 2018 had the highest annual sales. - Monthly and year-month
analysis was used to compare sales patterns across time. -
Year-over-year growth was calculated using `pct_change()`.

Important analytical distinction:

**A trend shows what happened over time; it does not automatically
explain why it happened.**

### 9. Outlier Analysis

We used the IQR method to identify unusually high Sales values.

-   Upper IQR boundary: **₹500.64**
-   Observations above the boundary: **1,145**

These were treated as potential high-value outliers, not automatically
as errors.

Some of the highest individual transactions were associated with
expensive Technology products.

**Key lesson: Outlier ≠ Error.**

High-value transactions should be investigated before being removed.

## Key Business Insights

1.  Sales are strongly right-skewed, with a long upper tail created by
    high-value transactions.
2.  Office Supplies has the highest order-line volume, but high
    frequency does not automatically mean the highest revenue.
3.  Phones is the strongest sub-category by total sales, while Fasteners
    is the weakest.
4.  West has the strongest overall sales performance, while South has
    the lowest.
5.  Technology in the East is the strongest category-region combination,
    while Furniture in the South is the weakest.
6.  Sales increased over the 2015--2018 period, with 2018 having the
    highest annual sales.
7.  Many observations are unusually high according to the IQR rule, but
    unusual does not automatically mean incorrect.
8.  Choosing the right business question before choosing a visualization
    is critical.

## Visualization Workflow

The project followed this repeatable process:

1.  Ask a question.
2.  Understand the data shape.
3.  Choose the appropriate chart.
4.  Prepare the data with pandas.
5.  Build the visualization.
6.  Read and quantify the result.
7.  Check and polish the visualization.
8.  Convert the result into a business insight.

Charts used included:

-   Histograms
-   Boxplots
-   Bar charts
-   Horizontal bar charts
-   Line charts
-   Pivot tables
-   Heatmaps

## Storytelling & Interview Practice

We practiced explaining charts using a 30-second framework:

1.  **Orient** --- What is the chart showing?
2.  **Read & Quantify** --- What is the main pattern and what number
    supports it?
3.  **Explain Carefully** --- What might explain the pattern, and what
    should be checked?
4.  **So What?** --- Why does the finding matter and what should happen
    next?

This turns chart reading into business-oriented communication.

## Conclusion

The main learning from this project was not a particular Python function
or chart type. It was learning how to move from:

**Question → Data → Analysis → Visualization → Insight → Business
Action**

The project reinforced that:

-   A visualization should answer a question.
-   Counts, totals, averages, and percentages answer different
    questions.
-   Unusual observations are not automatically errors.
-   A visualization can show a pattern without proving its cause.
-   Strong analysis connects every important chart to an insight and a
    useful follow-up question.

## Project Status

-   EDA & Visualization: **Completed**
-   Storytelling / Interview Practice: **Completed**
-   README: **Included**
-   GitHub publication: **Ready**
