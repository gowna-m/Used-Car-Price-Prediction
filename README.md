# Used-Car-Price-Prediction

The dataset contained information on 3 million used cars. The provided dataset contains information on 426K cars to ensure speed of processing. I had to analyze what factors make a car more or less expensive. The results provide clear recommendations to the client -- a used car dealership -- as to what consumers value in a used car.

The market for used cars has progressed significantly as more people choose personal vehicles. The second-hand automobile market has significantly grown after the covid had struck due to reduction in the cash flow and economic crisis and semiconductor chip shortages that to a mass reduction in the vehicle production which made people look for afforable second-hand vehicles instead of the brand-new ones.

To enable consumers to know the actual worth of their car or desired
car, by simply providing the program with a set of attributes from the desired car to predict the car price.
The purpose of this study is to understand and evaluate used car prices, and to develop a strategy
that utilizes Machine Learning techniques to predict used car prices.

1. Almost every column has missing values. So first we have to do the imputations.
2. Drop the columns `VIN` and `State` as they are not relevant for price prediction.
3. Identify `Numerical` and `Categorical` Columns and label encode the categorical features. There are two numerical features, Year and Odometer, rest are categorical.
4. `Label Encode` the Categorical Features, namely: region, manufacturer, model, condition, cylinders, fuel, title_status, transmission, drive, size, type & paint_color.
5. After encoding, we first impute the Categorical Data using simple imputations of `Mean` and `Median` and testing them on `Bayesian Ridge estimator` one by one. We save the scores of 6 fold `cross validation` in another dataframe.
6. Now we impute the data using IterativeImputer on 4 estimators - 

    1. `BayesianRidge`
    
    2. `DecisionTreeRegressor`
    
    3. `ExtraTreesRegressor`
    
    4. `KNeighborsRegressor`

9. `IterativeImputer` using `Bayesian Ridge estimator` to impute the missing values of categorical features.
10. Impute the missing values in `Numerical Features` using `ExtraTreesRegressor` as estimator in IterativeImputation.
11. Convert the Target Variable to its log values, so that we get a `normalized target`.
12. We find out the outliers for numerical variables and target and drop the outlier data points.
