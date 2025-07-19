# Weather Data Analysis with Pandas, Matplotlib & Seaborn

This project explores and analyzes historical weather data from the `weatherHistory.csv` dataset using Python libraries such as `pandas`, `numpy`, `matplotlib`, and `seaborn`.

## Dataset

- File: `weatherHistory.csv`
- Rows: 96,453
- Columns: 12
- Time Range: April 1, 2006 to September 9, 2016
- Key Features:
  - `Temperature (C)`
  - `Apparent Temperature (C)`
  - `Humidity`
  - `Wind Speed (km/h)`
  - `Visibility (km)`
  - `Pressure (millibars)` 

## Exploratory Data Analysis (EDA)

###  Correlation with `Temperature (C)`:

| Feature                    | Correlation     |
|---------------------------|-----------------|
| `Humidity`                | **-0.63**        |
| `Visibility (km)`         | 0.39             |
| `Wind Bearing (degrees)`  | 0.03             |
| `Wind Speed (km/h)`       | 0.009            |
| `Pressure (millibars)`    | -0.005           |

 **Insight:** Humidity has the strongest inverse correlation with temperature.


##  Model: Linear Regression

###  Attempt 1: Using Only `Type` Feature
```python
input = weather[['Type']]
target = weather['Temperature (C)']
model = LinearRegression().fit(input, target)
loss = rmse(target, model.predict(input))
# RMSE ≈ 7.91 

## Atempt 2:
input = weather[['Type', 'Humidity','Apparent Temperature (C)',
                 'Wind Bearing (degrees)','Visibility (km)',
                 'Wind Speed (km/h)','Pressure (millibars)']]
# RMSE ≈ 0.95 



