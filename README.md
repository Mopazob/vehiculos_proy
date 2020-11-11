# Vehicles price estimator project: Overview
* This is my first project :D
* Estimates the vehicles prices in USA with MAE~ .
* Data from Kaggle platform.
* Predictions by three models: Multiple Regression, Random Forest and K-nearest Neighbors Regression.

## Code and Libraries Used
**Version Python:** 3.8  
**Libraries:** pandas, numpy, sklearn, matplotlib, seaborn

## Data
**Datos from:** https://www.kaggle.com/austinreese/craigslist-carstrucks-data

## Data Cleaning
The data had so many NaN values and inconsistencies, so i made the following changes:
* Dropping unnecessary columns: county, url, region_url, region, lat, long, image_url and vin
* Transform cylinders columns to a numerical one
* Dropping entries with less than 1000usd price and more than 60000 price
* Dropping entries below 2000 and above than 2021 in the year variable
* Dropping entries that have "other" in the following columns: transmission, fuel and type
* Imputing NaN values with "NoEspecifiado" in the variables condition, drive and type
* Filling up cylinders variable NaN's with the median of it
* Dropping paint color columns, since has no influence in the vehicle price
* Dropping variables size and title_status becase have more than 35% of NaN values
* Fill NaN values in the odometer column with the mean
* Created a new column with de lenght of the description of the vehicle
* Created an vehicle age, miles per year and price per mile columns 

## EDA

## Model Building

## Model Performance
