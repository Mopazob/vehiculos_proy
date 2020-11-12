# Vehicles price estimator project: Overview
* This is my first project :D
* Estimates the vehicles prices in USA with MAE ~ 2.5k 
* Data from Kaggle platform.
* Predictions by three models: Multiple Regression, Random Forest and K-nearest Neighbors Regression.

## Data, Code and Libraries Used
**Data from:** https://www.kaggle.com/austinreese/craigslist-carstrucks-data
**Python Version:** 3.8  
**Libraries:** pandas, numpy, sklearn, matplotlib, seaborn

## Data Cleaning
The data had so many NaN values and inconsistencies, so i made the following changes:
* Dropping unnecessary columns: county, url, region_url, region, lat, long, image_url and vin
* Transform cylinders columns to a numerical one
* Dropping entries with less than 1000usd price and more than 60000usd price
* Dropping entries before 2000 and after than 2021 in the year variable
* Dropping entries that have "other" in the following columns: transmission, fuel and type
* Imputing NaN values with "NoEspecificado" in the variables condition, drive and type
* Filling up cylinders variable NaN's with the median of it
* Dropping paint color columns, due has no influence in the vehicle price
* Dropping variables size and title_status because have more than 35% of NaN values
* Fill NaN values in the odometer column with the mean
* Created a new column with de length of the description of the vehicle
* Created an vehicle age, miles per year and price per mile columns 

## EDA
I looked at the distributions of the data and some graphics for the variables.

![](https://github.com/Mopazob/vehiculos_proy/blob/main/images/1.png)
![](https://github.com/Mopazob/vehiculos_proy/blob/main/images/2.png)
![](https://github.com/Mopazob/vehiculos_proy/blob/main/images/year.price.fuel.png)



## Model Building
* First, splitted the data into train and tests sets with a test size of 30% for a **Multiple Regression** only with the numerical variables
* Then turned categorical variables into dummy variables for a **second multiple regression**
* Next tried a **KNN Regression**, looked for the best K for this model
* Try two types of **RandomForest**, the first with a super high R2, probably overfitted, then tried to minimize the overfit tuning some parameters for a second RF

## Model Performance
Random Forest models outperformed the results of the other models. Here the MAE of each model:

* Multiple Regression 1: 5465.97
* Multiple Regression 2: 4518.36
* KNN Regression: 8332.87
* Random Forest *overfitted*: 2148.20
* Random Forest (best model): 2479.35

## Conclusions
1. RandomForest clearly perform the best predictions of all with an R2 = 87%, RMSE ~ 4k and a MAE ~ 2.5k
2. Probably an GridSearch will drop better results since improves the parameters of the regression
3. The data was very unclean so maybe with other data cleaning and manipulation the results might be better
4. A project worked up only with the type "Cars" will throw other results, since in this project i worked with all the type of vehicles

![](https://github.com/Mopazob/vehiculos_proy/blob/main/images/mae%20per%20model.png)

Thank you for reading. Sorry if some results are not expected, or some manipulation are incorrect, but this is my first project and i hope to keep improving in the next projects.

MOB.
