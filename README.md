# Ghana Adventures Business Dashboard

## Project Overview

The **Ghana Adventures Business Dashboard** is a Business Intelligence project developed to analyze booking trends, customer behaviour, revenue performance, and operational efficiency for a travel and tour company. Using Microsoft Excel for data preparation and Power BI for visualization, the dashboard transforms raw booking data into actionable insights that support strategic decision-making.

The dashboard enables stakeholders to monitor business performance, identify high-performing tour packages, evaluate customer retention, and make data-driven decisions to improve revenue and customer satisfaction.

---

# Business Problem

Ghana Adventures operates in the tourism and travel industry, offering domestic and international tour packages, corporate travel services, and adventure tourism experiences.

Despite experiencing consistent customer demand, the company faced several operational challenges:

- Booking volumes fluctuated significantly across different seasons.
- Customer retention remained relatively low, with many customers making only a single booking.
- Certain tour packages generated strong demand while others consistently underperformed.
- Management lacked a centralized reporting system to monitor business performance and support strategic planning.

The objective of this project was to develop an interactive dashboard that provides clear visibility into business performance, enabling management to identify trends, optimize marketing efforts, improve customer loyalty, and support data-driven decision-making.

---

# Dataset Information

**Industry:** Travel & Tourism

### Raw Dataset Fields

- Booking Date
- Customer ID
- Tour Package
- Destination
- Price (GHS)
- Booking Type
- Repeat Customer
- Season
- Booking Channel

---

# Tools Used

- Microsoft Excel
  - Data Cleaning
  - Power Query
- Microsoft Power BI
  - Data Modeling
  - DAX
  - Interactive Dashboard Development

---

# Data Cleaning & Transformation

The raw dataset underwent several preprocessing steps before visualization.

### 1. Removed Missing and Incomplete Records

Rows containing blank booking records, missing customer IDs, or incomplete booking information were identified and removed to improve data integrity.

---

### 2. Removed Duplicate Records

Duplicate bookings were detected using Customer ID, Booking Date, and Tour Package combinations. Duplicate entries were removed to ensure booking counts and revenue calculations remained accurate.

---

### 3. Standardized Data Formats

Data types were validated and corrected to ensure consistency.

Examples included:

- Booking Date converted to Date format
- Price converted to Currency
- Customer ID converted to Whole Number
- Text values standardized to eliminate inconsistent spellings and extra spaces

---

### 4. Created Derived Columns

Additional analytical fields were prepared to support reporting, including:

- Month Name
- Month Number
- Year
- Revenue Category
- Customer Type (New or Repeat)

These fields enabled seasonal analysis, monthly trend reporting, and customer segmentation.

---

# Data Modeling

A simple star-schema model was implemented to improve reporting performance and simplify analytical calculations.

### Fact Table

**Fact_Bookings**

Contains transactional booking records including:

- Booking Date
- Customer ID
- Tour Package
- Price
- Booking Channel
- Booking Type
- Repeat Customer
- Season

### Dimension Tables

**Dim_Date**

- Date
- Month
- Quarter
- Year

**Dim_TourPackage**

- Tour Package
- Destination

**Dim_Customer**

- Customer ID
- Customer Type

Relationships were established between the fact table and dimension tables using primary and foreign keys to support efficient filtering and aggregation.

---

# DAX Measures

### Total Revenue

```DAX
Total Revenue =
SUM(Bookings[Price])
```

Calculates the total revenue generated from all tour bookings.

---

### Repeat Customer Rate

```DAX
Repeat Customer Rate =
DIVIDE(
    CALCULATE(
        COUNT(Bookings[Customer ID]),
        Bookings[Repeat Customer] = "Yes"
    ),
    COUNT(Bookings[Customer ID]),
    0
)
```

Calculates the percentage of customers who made repeat bookings.

---

### Average Booking Value

```DAX
Average Booking Value =
AVERAGE(Bookings[Price])
```

Measures the average revenue generated per booking.

---

# Dashboard KPIs

The dashboard provides key business metrics including:

- Total Bookings
- Total Revenue
- Average Booking Value
- Repeat Customer Rate

---

# Dashboard Analysis

The dashboard includes interactive visualizations covering:

## Booking Performance

- Total Bookings by Season
- Top Booking Tour Packages
- Lowest Performing Tour Packages
- Highest Revenue Tour Packages
- Lowest Revenue Tour Packages
- Booking Channel Performance

---

## Customer Behaviour

- Booking Type Preference
- Total Revenue by Season
- Monthly Booking Trends
- Average Booking Value by Customer Type
- Customer Retention by Booking Channel

---

# Key Insights

### 1. Peak Seasons Generate Higher Demand

Booking volumes and revenue were consistently higher during Peak seasons compared to Off-Peak periods.

**Recommendation**

Introduce targeted promotions, family packages, and seasonal discounts during Off-Peak periods to improve booking consistency throughout the year.

---

### 2. Premium Tour Packages Drive Revenue

Some premium tour packages generated significantly higher revenue despite having fewer bookings, demonstrating that higher-value experiences contribute disproportionately to overall profitability.

**Recommendation**

Increase marketing investment in premium packages while bundling lower-performing tours with popular offerings to improve visibility.

---

### 3. Customer Retention Represents a Growth Opportunity

Repeat customers demonstrated stronger purchasing behaviour and higher average booking values than first-time customers.

**Recommendation**

Implement customer loyalty programmes, referral incentives, and personalised post-trip marketing campaigns to improve long-term customer retention.

---

# Business Value

The dashboard enables management to:

- Monitor booking performance in real time.
- Identify seasonal demand patterns.
- Evaluate tour package profitability.
- Understand customer booking behaviour.
- Improve marketing effectiveness.
- Support strategic planning using data-driven insights.

---

# Future Improvements

Potential enhancements include:

- Predictive demand forecasting using historical booking trends.
- Customer segmentation using RFM analysis.
- Geographic analysis of customer locations.
- Integration with live booking databases.
- Automated dashboard refresh using Power BI Service.

---

# Dashboard Preview

> *(Insert dashboard screenshots here.)*

---

# Author

**Precious Ezekiel Adjei**

Aspiring Data Analyst | Business Intelligence Enthusiast

- Microsoft Excel
- Power BI
- SQL
- Python

---
