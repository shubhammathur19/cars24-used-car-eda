Cars24 Used-Car Price: EDA and Data Preparation
Exploratory data analysis and feature engineering on ~14K Cars24 used-car listings, to understand what drives selling price.
Dataset
`train-cars24-car-price.csv`: 13,986 listings, 11 columns (name, year, seller type, km driven, fuel type, transmission, mileage, engine, max power, seats, selling price in lakhs).
What was done
Data checks: shape, dtypes, missing values, summary statistics
Outliers: capped extreme prices; found and dropped invalid mileage = 0 rows; kept valid electric-car mileage values
Categorical analysis: fuel type, transmission, seller type, make (41 brands), seats
Feature engineering: `age` from year, `make` and `model` from name, one-hot and frequency encoding, MinMax scaling
Correlation analysis to identify price drivers
Key findings
Strongest drivers: max power, engine size and brand (positive); manual transmission, age and mileage (negative)
Diesel cars sell for more than petrol; seller type and km driven show little linear relationship with price
Price is right-skewed, so a log transform suits modelling
Median-price encoding of make/model leaks the target and inflates their correlations; a modelling step should split first
Python, pandas, NumPy, Matplotlib, Seaborn, scikit-learn
