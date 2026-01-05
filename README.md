# Vehicle Sales Data Analysis

A beginner data analysis project exploring 558,837 vehicle auction records from 2014-2015 to understand pricing patterns, sales trends, and market dynamics in the US automotive industry.

## About This Project

This is my hands-on data analysis project where I clean, explore, and visualize a real-world dataset of car auction sales. The goal was to practice essential data analysis skills: handling messy data, asking good questions, creating meaningful visualizations, and telling a story with numbers.

### What I Learned
- Dealing with missing data (numerical vs. categorical approaches)
- Creating time-based features from datetime columns
- Building visualizations that actually answer questions
- Feature engineering for future forecasting models
- Working with a dataset that's large enough to feel real

## Dataset

**Source**: Car auction sales data  
**Records**: 558,837 vehicles sold  
**Time Period**: December 2014 - July 2015  
**Columns**: 16 features including make, model, year, price, condition, mileage, location, colors, and sale date

The data comes from real auction transactions and includes everything from the vehicle details (make, model, year, mileage, condition) to sale information (price, date, state) and market benchmarks (MMR - Manheim Market Report value).

## Getting Started

### Requirements
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Running the Analysis
1. Clone this repository
2. Make sure `car_prices.csv` is in the project folder
3. Open the notebook: `jupyter notebook vehicle_sales_data_cleaning.ipynb`
4. Run the cells in order

### Outputs
The notebook generates:
- `car_prices_cleaned.csv` - Dataset after cleaning
- `car_prices_processed_for_forecasting.csv` - Dataset with engineered features
- 13 visualization PNG files showing different analysis perspectives

## What's in the Analysis

### 1. Data Cleaning
- Handled ~45,000 missing values in odometer readings (filled with mean)
- Dealt with missing condition scores, colors, and other categorical fields
- Standardized body types (converted variations like "Sedan 4D" → "Sedan")
- Parsed complex datetime strings with timezone info

### 2. Exploratory Data Analysis

I explored the data through multiple angles:

**Sales Trends Over Time**
- Which months/days had the highest sales volume?
- How did revenue change throughout the time period?
- Were there any noticeable weekly patterns?

**Body Type Analysis**
- Which vehicle types (Sedan, SUV, Truck, etc.) sold most?
- How do average prices compare across body types?
- What's the market share distribution?

**Pricing Patterns**
- What's the typical price range?
- How do auction prices compare to MMR values?
- Which factors correlate most with selling price?

**Make & Model Insights**
- Who are the top manufacturers by volume and revenue?
- Which specific models appear most frequently?
- Are luxury brands consistently priced higher?

**Geographic Distribution**
- Which states have the most sales activity?
- Do certain regions prefer certain vehicle types?

**Vehicle Characteristics**
- How does mileage affect price?
- Do newer cars command higher prices?
- What condition scores are most common?
- Which colors are most popular?
- Automatic vs. manual transmission preferences?

**Correlation Analysis**
- Which numeric features relate to selling price?
- Are odometer and condition score related?
- Does vehicle age correlate with condition?

**Seasonal Patterns**
- Monthly trends (Q4 vs. Q1 vs. Q2/Q3)
- Day of week patterns
- Hour of day patterns (auction timing)

### 3. Feature Engineering

Created new columns for future forecasting work:
- Time features: `sale_year`, `sale_month`, `sale_quarter`, `sale_day`, `sale_dayofweek`, `sale_hour`
- Vehicle age: `vehicle_age` (calculated from model year and sale date)
- Price metrics: `price_difference` and `price_difference_pct` (comparing sale price to MMR)
- Efficiency metric: `price_per_mile`
- Categorical bins: `price_category`, `age_category`, `odometer_category`

## Key Findings

### Sales Volume
- **558,837** total vehicles sold in ~8 months
- Average of **~2,200 sales per day**
- Peak activity in certain months (visible in visualizations)

### Pricing
- **Average price**: ~$13,000
- **Median price**: ~$12,000 (close to mean, suggesting normal distribution)
- Most vehicles sold within $5,000-$20,000 range
- Some luxury vehicles exceeded $60,000

### Popular Vehicles
- **Sedans** dominated sales volume
- **Ford**, **Chevrolet**, and **Nissan** were top brands by count
- **SUVs** had higher average prices than sedans
- Certain states (like CA, TX, FL) had significantly more transactions

### Condition & Mileage
- Most vehicles had condition scores of 3-5 (out of 5)
- Average odometer reading: ~70,000 miles
- Clear negative correlation between mileage and price

### Colors
- **Black**, **white**, and **silver** were most common
- Some niche colors commanded slightly higher average prices
- Interior colors showed similar patterns

## Project Structure

```
Vehicle-Sales-Data-Analysis/
├── vehicle_sales_data_cleaning.ipynb    # Main analysis notebook
├── car_prices.csv                       # Raw data (558K records)
├── car_prices_cleaned.csv               # After missing value handling
├── car_prices_processed_for_forecasting.csv  # With engineered features
├── README.md                            # This file
├── .gitignore                           # Git exclusions
└── *.png                                # 13 visualization outputs
```

## Visualizations

The notebook creates 13 charts:
1. Sales trends over time (daily/monthly)
2. Seasonal patterns (by month, day, hour, quarter)
3. Body type distribution and average prices
4. Price distribution histogram
5. Top makes by volume and revenue
6. Top models by sales count
7. State-by-state sales volume
8. Condition vs. age scatter plot
9. Odometer distribution and price relationship
10. Correlation heatmap
11. Color popularity and pricing
12. Transmission type breakdown
13. Year-over-year comparison (2014 vs. 2015)

## What's Next

Ideas for extending this project:
- Build a price prediction model using the engineered features
- Try time series forecasting to predict future sales volume
- Perform more advanced statistical tests (ANOVA, chi-square)
- Create an interactive dashboard with Plotly or Dash
- Analyze depreciation curves for different makes/models
- Investigate regional preferences in more detail

## Tools Used

- **Python 3.8+**
- **Pandas** - Data manipulation and cleaning
- **NumPy** - Numerical operations
- **Matplotlib & Seaborn** - Visualizations
- **Jupyter Notebook** - Interactive development

## Author

Shalin Vachheta  
[LinkedIn](https://www.linkedin.com/in/shalin-vachheta/) | [GitHub](https://github.com/ShalinVachheta017)

