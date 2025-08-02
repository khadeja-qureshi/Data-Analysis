# Olympics-medals-prediction

This project uses historical Olympic team data to predict the number of medals a country will win in future events using a linear regression model.

## Project Overview
The goal was to build a regression model that predicts the number of medals a country might win based on features such as:

- Number of athletes
- Number of events participated in
- Number of medals won in the previous Olympics
- Medals won in the previous 3 Olympics


## Dataset

The dataset (`teams.csv`) contains:
- Olympic team statistics from various years and countries
- Features like year, number of athletes, average age, height, weight, previous medal counts, etc.

**Shape:** `2144 rows × 11 columns`

## Data Cleaning

- Removed rows with missing values in `prev_medals` and `prev_3_medals`
- Split the dataset:
  - `train`: Years before 2012
  - `test`: Years 2012 and beyond

##  Exploratory Data Analysis

Visualized correlations and relationships using:
- `sns.scatterplot` for numerical features vs medals
- `sns.barplot` for `year` vs `medals`
- `.corr()` to check correlations:
  - `athletes` and `medals`: **0.84**
  - `events` and `medals`: **0.77**
  - `prev_medals` and `medals`: **0.92**

These features showed a strong correlation with medal counts.

##  Model

- **Algorithm:** `LinearRegression` from `sklearn`
- **Features used:**  
  - `athletes`  
  - `prev_medals`  
  - `events`
- **Target:** `medals`


