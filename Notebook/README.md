
# Notebook

This folder contains the analysis notebook for the AtliQ Grands hospitality project.

## `hospitality_project.ipynb`

End-to-end analysis covering:

1. **Data Exploration** — initial inspection of bookings, hotels, rooms, and date data
2. **Data Cleaning** — removing invalid records, handling outliers (3-standard-deviation rule), imputing missing values (median substitution)
3. **Data Transformation** — engineering the occupancy rate metric (`successful_bookings / capacity`) and merging dimension tables
4. **Insights Generation** — answering business questions on occupancy by room category, city, weekday/weekend, and monthly trends, plus revenue analysis by city and month

## How to Run

1. Make sure the `data/` folder (containing all 6 CSV files) sits at the same level as this `notebook/` folder — the notebook reads paths relative to the project root:
   ```
   AtliQ-Grands-Hospitality-Analytics/
   ├── data/
   └── notebook/
       └── hospitality_project.ipynb
   ```
2. Install dependencies:
   ```
   pip install pandas matplotlib jupyter
   ```
3. Launch Jupyter and run all cells:
   ```
   jupyter notebook hospitality_project.ipynb
   ```
   Then: Kernel → Restart & Run All

## Libraries Used

Pandas · Matplotlib
