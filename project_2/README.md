# Project 2: Predicting Housing Prices in Ames, Iowa

#### Problem Statement

To predict the sales price of houses in Ames using a Ridge regression model by understanding the relationships between the different aspects of a home and its price.

The model can be used to guide the valuation of homes by buyers and sellers alike. Potential limitations of the model could be due the lack of ability to study past trends and economic conditions. The success of the model is evaluated through r-squared and RMSE, which is in line with the scoring in Kaggle.

---

#### Executive Summary

Data cleaning, visualisation and pre-processing was done before running three regression models to predict house prices in Ames, Iowa. The major issues in data cleaning were missing values, which were imputed and some outliers. Features were also combined and some of the variables were dropped to prevent multicollinearity. The three models used were linear, ridge and lasso regressions, of which ridge was in the end chosen as the production model. 

The model found that above grade (ground) living area square feet, overall quality of the homes and two of the neighbourhoods are the biggest contribution factors to sale price. Size, quality and location have always been the most important factors in home purchase. To increase sale price, home owners can focus on improving overall quality and exterior quality of their homes. 

To generalise this model to other cities, we need information on the tastes and preferences of people in other cities by getting hold of data on population demography - age, income, race, etc. 

---

#### Business Overview and Process

The Ames Housing Dataset is a detailed dataset with over 70 columns of different features relating to houses.

The goal of this regression model is to help buyers purchase a home that is good for investment (i.e. potentially underpriced) or to purchase at a 'correct' price. Besides, this model should also help sellers price their homes accurately.  

---

#### Datasets

Train and test sets on Ames, Iowa housing prices. The train set contains the target variable, the sale price. The test set does not have the target variable.  

#### EDA and Data Cleaning

1. Imputed missing values with mean, mode and 0's.
2. Identified outliers
3. Combined features such as porch area, bathrooms, garage. The original features are dropped to prevent multicollinearity.

---

#### Exploratory Visualisations

Low variance:
There numerical features that have low/no variance, which is not helpful for machine learning.
Dropped 'BsmtFinSF1' and 'BsmtFinSF2', 'LowQualFinSF', 'MiscVal' and 'PoolArea'.

Normal distribution:
Some variables have a lot of outliers and are not normally distributed. Addressed them by taking log.

#### Pre-processing

Ordinal variables:

'ExterQual','ExterCond','KitchenQual','BsmtQual','HeatingQC','FireplaceQu','GarageQual','GarageCond','BsmtCond','PoolQC, 'BsmtExposure', 'BsmtFinType1', 'BsmtFinType2', 'Fence', 'Utilities', 'LotShape', 'LandSlope', 'GarageFinish', 'CentralAir', 'Functional'

They are assigned values to represent their quality/ rank.

Categorical variables:
'SaleType', 'MSZoning', 'Street', 'Alley', 'LotConfig', 'LandContour', 'Condition', 'BldgType', 'HouseStyle', 'RoofStyle', 'RoofMatl', 'MasVnrType', 'Foundation', 'Heating', 'CentralAir', 'GarageType', 'MiscFeature',
'MSSubClass', 'Neighborhood', 'Exterior1st', 'Exterior2nd', 'PavedDrive', 'Electrical'

They are given dummies so that they can be included in the regression models.

#### Modelling

RMSE and r-squared are used for scoring.

The baseline RMSE is 79167.69 which functions as a gauge to show us how well the machine learning models work.

Choice of model:
Ridge regression is chosen among the three models because it allows for the shrinking of coefficients and gives the lowest RMSE. This is particularly helpful in this context because of the huge number of variables we have in the dataset.

Ridge Regression avoids over-fitting by adding a penalty to models that have too large coefficients. This means that the estimated coefficients are pushed towards 0, to make them work better on new data-sets. In other words, ridge is optimised for prediction, unlike the linear regression model.

---

#### Conclusions and Recommendations

Some important variables picked out:
|S/N|Variable|Coefficient|
|---|---|---|
|1|GrLivArea|9193.53|
|2|OverallQual|8898.81|
|3|Neighborhood_NridgeHt|7639.64|
|4|Neighborhood_StoneBr|6696.98|
|5|ExterQual|5875.12|
|6|TotalBath|5839.59|

The features that add the greatest value to homes are ground living area, which is the above grade (ground) living area square feet, overall quality of the homes and two of the neighbourhoods.
This makes sense because living area and quality of homes and neighbourhoods are important considerations in home purchases.

As we have seen that neighbourhoods play an important role in increasing sales prices, they also play an equally important role in reducing sales prices. So, the neighbourhoods that are good to ensure that prices are high, are North Ridge Heights and Stone Bridge. However, it is difficult to tell whether the prices will rise after purchase since the current price is already high.

In order to ensure that the value of homes can be increased, homeowners can look into improving the overall quality of the homes and the quality of the material on the exterior. The exterior quality surprisingly increases the value of the home a lot, which probably means that first impressions count a lot in attracting higher bids for homes.

This model is able to help sellers price their homes and to help buyers purchase homes at the 'correct' price. However, in order to be able to help buyers predict investment value, it would be good to have a time-series data to see the patterns of change so that we can more accurately predict changes moving forward. Other data including economic conditions (e.g. business cycles, interest rates) are also important in determining house prices.

Overall, looking at the variables that have the highest coefficients, it seems that the model could be generalised to other cities. The reasons for variables such as square feet and overall quality of homes are quite self-explanatory and is generalisable throughout the world. However, to be able to weigh the importance of the finer details like preference for lot shape, porch space, garage and fireplace, we need information on their tastes and preferences by getting hold of data on population demography - age, income, race, etc.

---
