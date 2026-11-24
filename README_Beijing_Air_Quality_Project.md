# Beijing Multi-Site Air Quality Analysis & PM₂.₅ Prediction

An end-to-end data analysis and machine learning project using Beijing's
multi-site air-quality dataset to explore pollution patterns and predict
PM₂.₅ concentrations with Stochastic Gradient Descent (SGD) regression.

## Project Overview

This project combines exploratory data analysis (EDA), data
preprocessing, statistical analysis and regression modelling on hourly
air-quality observations collected from 12 monitoring stations in
Beijing, China, between March 2013 and February 2017.

**Objective:** Analyse air-quality patterns and develop a regression
model to estimate PM₂.₅ levels using pollutant measurements,
meteorological variables and station information.

## Dataset

-   **Source:** [UCI Machine Learning Repository -- Beijing Multi-Site
    Air Quality
    Data](https://archive.ics.uci.edu/dataset/501/beijing+multi+site+air+quality+data)
-   **Original dataset:** 420,768 hourly observations from 12 monitoring
    stations.
-   **Coverage:** March 2013 -- February 2017.
-   **Target variable:** PM₂.₅
-   **Predictor information:** PM₁₀, SO₂, NO₂, CO, O₃, pressure,
    dew-point temperature, wind direction, wind speed, date/time and
    monitoring station.

## Technologies

-   **Programming:** Python
-   **Data analysis:** Pandas, NumPy
-   **Visualisation:** Matplotlib, Seaborn
-   **Statistical analysis:** Correlation analysis, Variance Inflation
    Factor (VIF), Interquartile Range (IQR)
-   **Machine learning:** Scikit-learn, SGDRegressor

## Project Workflow

### 1. Data Preparation

-   Combined the 12 station-level datasets into a unified dataset.
-   Standardised column names and removed the redundant record-number
    column.
-   Examined missing values and removed incomplete records for the
    analysis.
-   Selected a station-balanced 10% sample for model development,
    containing 3,564 observations per station.

### 2. Exploratory Data Analysis

-   Examined PM₂.₅ distributions and descriptive statistics.
-   Analysed monthly and hourly pollution patterns.
-   Compared pollution trends across years.
-   Used correlation analysis and VIF to examine relationships among
    predictor variables.
-   Applied the IQR method to identify and filter PM₂.₅ outliers in the
    modelling sample.

### 3. Feature Preparation

-   Selected PM₂.₅ as the prediction target.
-   Removed highly correlated features identified during the analysis.
-   Encoded categorical variables, including monitoring station and wind
    direction.
-   Standardised input features before model training.
-   Split the modelling data into training and test sets using an 80:20
    split, stratified by station.

### 4. Model Development

-   Developed a baseline **Stochastic Gradient Descent Regressor
    (SGDRegressor)**.
-   Tuned the model using:
    -   Epsilon-insensitive loss
    -   L1 regularisation
    -   Adaptive learning rate
    -   Learning-rate and iteration parameters

## Model Evaluation

The model was evaluated using R², Mean Absolute Error (MAE) and Mean
Squared Error (MSE).

  Metric       Baseline SGDRegressor   Tuned SGDRegressor
  ---------- ----------------------- --------------------
  Test R²                     0.7816               0.7771
  Test MAE                     18.79                18.10
  Test MSE                    748.02               763.41

The tuned model reduced test MAE from **18.79 to 18.10**. The baseline
model recorded a slightly higher test R², while the tuned model achieved
a lower MAE.

## Key Analysis Areas

-   Hourly and monthly PM₂.₅ variation
-   Air-pollutant relationships and multicollinearity
-   Meteorological features associated with PM₂.₅
-   Station-level representation in model sampling
-   Regression model performance and error evaluation

## Repository Contents

-   `Bijing_Air _Quality_Data.ipynb` -- Data preparation, exploratory
    analysis, visualisation and statistical analysis.
-   `-Beijing-Multi-Site-Air-Quality-Data SGD regressor-.ipynb` --
    Sampling, preprocessing, feature preparation, SGD regression and
    model evaluation.

## How to Run

1.  Download the dataset from the [UCI
    repository](https://archive.ics.uci.edu/dataset/501/beijing+multi+site+air+quality+data).
2.  Place the station CSV files in the project data directory.
3.  Update the dataset paths in the notebooks to match your local
    directory.
4.  Install the required Python libraries.
5.  Run the exploratory analysis notebook, followed by the SGD
    regression notebook.

``` bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels jupyter
```



------------------------------------------------------------------------
