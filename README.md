# AirbnbListing Price Prediction 

## Overview
### Purpose
The purpose of this project is to predict the price of Airbnb listings in major U.S. cities. 


### Features
Important features for this dataset are:
* id: Record identifier
* log_price: log(price)
More information regarding the dataset can be found [here](https://www.kaggle.com/rudymizrahi/airbnb-listings-in-major-us-cities-deloitte-ml) 

### Evaluation
The evaluation metric for the competition was Root Mean Squared Error (RMSE) score


## Project
### Data Cleaning
* Made sure correct datatypes are used for the features of the dataset (ie. datetime, float/integer). 
* Missing data within numerical columns were handled by replacing the values by its medians. 
* Formatting issues (ie. % signs) were fixed with a simple `replace()`
* Missing data for the Zipcode column were filled using python's `uszipcode` API through the data points' latitude and longitude coordinates
* Text data columns were converted to categorical data and converted to numbers (categorical codes) for ML training

### Model Creation
* Tried `Ridge` regression then `RandomForestRegressor`. `RandomForestRegressor` received a much higher score than Ridge regression

### Hyperparameter Tuning 
* Used `RandomSearchCV` to find the best parameters for the model then further improved the model by using `GridSearchCV`

### Evaluation Metrics
* **Mean Absolute Error (MAE)** was improved from 0.289 to 0.285 to 0.284
* **Root Mean Squared Error (RMSE)** was improved from 0.397 to 0.393 to 0.392
* **R-Squared** was improved from 0.693 to 0.699 to finally, 0.70
* Improvements to the model weren't very significant, but could be improved with longer training time
![modelComparison](https://github.com/daniel8691/AirbnbListing_ML/blob/main/Project_Images/model_comparison.png)


## Result 
* Price predictions for the Airbnb Listings can be found through [this link](https://github.com/daniel8691/AirbnbListing_ML/blob/main/airbnb_prediction.csv)
* Codes for the project can be found through [this link](https://nbviewer.jupyter.org/github/daniel8691/AirbnbListing_ML/blob/main/Airbnb_prediction_ML.ipynb)
* The trained model used to make the predictions can be found through [this link](https://github.com/daniel8691/AirbnbListing_ML/tree/main/ML_Model_joblib)

## Feature Importance
This graph below shows the most important features that made the most impact to the model
![feature_importance](https://github.com/daniel8691/AirbnbListing_ML/blob/main/Project_Images/feature_importance.png)
* Room type seems to contribute to the price of Airbnb listing the most, much more than the number of bedrooms within the rental unit. Airbnb unit owners could consider looking into the most profitable room types that travelers are looking for. 
* The number of bedrooms/bathrooms/accomodates to no suprise, affects Airbnb prices significantly. However, these features are more difficult to control as units with higher number of bedrooms/bathrooms/accomodates tend to be more expensive to purchase.
* Zipcode/Latitude/Longitude also affect Airbnb listing prices, so further analysis could be done on which locations are the most profitable

