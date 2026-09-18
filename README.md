# AtliQ Grands — Hospitality Data Analysis

Data cleaning, transformation, and occupancy/revenue analysis for AtliQ Grands, a hotel chain, using Python and Pandas. The project takes raw, messy booking data across multiple hotel properties and turns it into clean, analysis-ready datasets to answer real business questions about occupancy trends and revenue performance.

## Problem Statement

AtliQ Grands' revenue management team needed a clear view of how their properties were performing — which room categories and cities had the strongest occupancy, whether weekdays or weekends performed better, and how revenue moved month over month. The raw data (multiple CSVs with data quality issues) made this hard to answer directly.

## Datasets

| File | Description |
|---|---|
| `dim_hotels.csv` | Hotel property details — city, category |
| `dim_date.csv` | Calendar dimension — date, day type (weekday/weekend), month-year |
| `dim_rooms.csv` | Room category and room class mapping |
| `fact_bookings.csv` | Individual booking-level transactions — guests, revenue, platform, room category |
| `fact_aggregated_bookings.csv` | Daily aggregated bookings and capacity per property |
| `new_data_august.csv` | New booking data (August) merged in to extend the analysis period |

## What I Did

**Data Cleaning**
- Removed invalid booking records with zero or negative guest counts
- Detected and removed revenue outliers using the 3-standard-deviation rule (values beyond mean ± 3σ)
- Identified and imputed missing `capacity` values in the aggregated bookings data using median substitution
- Validated for and filtered out records where successful bookings exceeded property capacity

**Data Transformation**
- Engineered an **occupancy rate** metric: `successful_bookings / capacity`, converted to a percentage
- Merged booking, room, hotel, and date dimension tables into unified analysis-ready views
- Combined the new August data with the existing dataset to extend the analysis window

**Analysis & Insights**
- Average occupancy rate by room category and room class
- Average occupancy rate by city
- Weekday vs. weekend occupancy comparison
- City-level occupancy breakdown for a specific month (June)
- Total revenue realized by city
- Month-over-month revenue trend

## Tools & Libraries

Python · Pandas · Matplotlib

## Key Questions Answered

1. What is the average occupancy rate in each room category?
2. What is the average occupancy rate per city?
3. Is occupancy better on weekdays or weekends?
4. How does occupancy vary by city within a given month?
5. What is total revenue realized by city?
6. How does revenue trend month over month?

## How to Run

1. Clone this repository
2. Ensure all CSV files are in the same directory as the notebook
3. Install dependencies: `pip install pandas matplotlib`
4. Open `hospitality_project.ipynb` in Jupyter Notebook/Lab and run all cells

## Author

Sachin Gangwar
[LinkedIn](https://www.linkedin.com/in/sachin-gangwar-68980b330/) · [GitHub](https://github.com/sachingangwar0307)
