### Sales-Predictions
#Table of content :
1) Business Understanding
2) Data Understanding
3) Data Preparation
4) Modeling
5) Evaluation
6) Deployment
### 1) Business Understanding
*Our stakeholders are:

-Bakery owner .

*Their primary goal is:

-Increase the sales of their products .

*They plan to:

-Figure out the best products based on our analysis.

*What do they need/expect?

-Actionable insights/recommendations for which product they can make more to increase the income of their sales .
### 2) Data Understanding
The file had 8,523 rows and 12 columns.

There is a mixture of datatypes:

4 float
1 int
7 object
There is 0 duplicated rows and only two columns with missing data .
Item_Weight : we are going to impute with the median .
Outlet_Size : we are going to impute with the most frequent .
We don't have any constant or a quasi-constant feauture.
### 3) Data Preparation
# Numeric Features
The following features were processed as numeric features:

'Item_Weight', 'Item_Visibility', 'Item_MRP',
       'Outlet_Establishment_Year', 'Item_Outlet_Sales'
Missing values were imputed with the median.
The data was sacled using StandardScaler.

# Ordinal Features
The following features were processed as ordinal features:
'Outlet_Size'
The missing values were imputed withe the most frequent.
The ordinal categories is :'Small','Medium','High' and were encoded using OrdinalEncoder.
The ordinally-encoded features were then scaled using StandardScaler.

# Categorical (Nominal) Features
The following features were processed as categorical features:
'Item_Fat_Content', 'Item_Type', 'Outlet_Identifier',
       'Outlet_Location_Type', 'Outlet_Type'
The features were then encoded with OneHotEncoder.
### 4) Modeling
# Linear regression 

------------------------------------------------------------
Regression Metrics: Training Data
------------------------------------------------------------
- MAE = 847.131
- MSE = 1,297,556.865
- RMSE = 1,139.104
- R^2 = 0.562
------------------------------------------------------------
Regression Metrics: Test Data
------------------------------------------------------------
- MAE = 804.089
- MSE = 1,194,326.602
- RMSE = 1,092.853
- R^2 = 0.567

- # Decision Tree Regression 
------------------------------------------------------------
Regression Metrics: Training Data
------------------------------------------------------------
- MAE = 902.862
- MSE = 1,541,281.829
- RMSE = 1,241.484
- R^2 = 0.479
------------------------------------------------------------
Regression Metrics: Test Data
------------------------------------------------------------
- MAE = 855.204
- MSE = 1,399,345.579
- RMSE = 1,182.939
- R^2 = 0.493

- ### 5) Evaluation
- For the Linear Regression model the r2=0.562 for the trainig set and r2= 0.567 for the testing set . the RMSE for both training an testing set : 1139.104  /1092.853 .

For the Decision Tree Regression model the r2=0.479 for the trainig set and r2=0.493 for the testing set the RMSE for both training and testing set : 1241.48 4 /1182.939 

I don't recommend any model of them due to their poor performance .

 ### 6) Deployment
Item MRP is the column with the biggest correlation with the target .
They have a positive correlation (0.57) so with higher MRP we found a higher oultelt sales.

The item visibility is one of the columns that are correlated negativly with the target .
The less is better in this case .

the regular fat is having more sales than the low fat and for the size of the outlet the medium is the one with the more sales .
