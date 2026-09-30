# Cars24 Used-Car Price: EDA and Data Preparation

Exploratory data analysis and feature engineering on ~14K Cars24 used-car listings, to understand what drives selling price.

## Dataset

- **File:** `train-cars24-car-price.csv`
- **Size:** 13,986 listings, 11 columns
- **Columns:** name, year, seller type, km driven, fuel type, transmission, mileage, engine, max power, seats, selling price (in lakhs)

## What Was Done

- **Data checks:** shape, dtypes, missing values, summary statistics
- **Outliers:**
  - Capped extreme prices
  - Dropped invalid mileage = 0 rows for petrol and diesel cars
  - Kept electric cars, where kmpl may not apply
- **Categorical analysis:** fuel type, transmission, seller type, make (41 brands), seats
- **Feature engineering:**
  - `age` from year
  - `make` and `model` from the car name
  - One-hot and frequency encoding
  - MinMax scaling
- **Correlation analysis** to identify price drivers

## Key Findings

- **Strongest drivers:**
  - Positive: max power, engine size, brand
  - Negative: manual transmission, age, mileage
- Diesel cars sell for more than petrol cars.
- Seller type and km driven show little linear relationship with price.
- Price is right-skewed, so a log transform suits modelling.
- Median-price encoding of make and model leaks the target and inflates their correlations. A modelling step should split the data first.

## Tools

Python, pandas, NumPy, Matplotlib, Seaborn, scikit-learn
