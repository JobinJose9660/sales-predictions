# sales-predictions
![](https://github.com/JobinJose9660/sales-predictions/blob/main/sales-prediction-social-media.png)

 # Sales Prediction Analysis - Regression
  In this project I'm aiming to predict the outlet sales using some feartures ,also explaining which the best machine learning model for the prediction and why?
 
 
 
 
#**Dataset Information**
 
 
1.Item_Identifier    -	Unique product ID

2.Item_Weight         -	Weight of product

3.Item_Fat_Content 	    Whether the product is low fat or not

3.Item_Visibility      -	The % of total display area of all products in a store allocated to the particular product

4.Item_Type -	The category to which the product belongs

5.Item_MRP -	Maximum Retail Price (list price) of the product

6.Outlet_Identifier -	Unique store ID

7.Outlet_Establishment_Year -	The year in which store was established

8.Outlet_Size -	The size of the store in terms of ground area covered

9.Outlet_Location_Type -	The type of city in which the store is located

10.Outlet_Type -	Whether the outlet is just a grocery store or some sort of supermarket

12.tem_Outlet_Sales -	Sales of the product in the particulat store. This is the outcome variable to be predicted
## Libraries

1.pandas

2.matplotlib

3.seaborn

4.scikit-learn
## Algorithms

6.Linear Regression

7.Decision Tree

8.Random Forest

9.KnNeighbors

# DATA TYPES 
1.RangeIndex: 8523 entries, 0 to 8522
2 .Data columns (total 12 columns):
 #Column                     Non-Null Count  Dtype  
---  ------                     --------------  -----  
 1.  Item_Identifier         -   8523 - non-null   object 
 3.  Item_Weight             -   7060 -  non-null   float64
 4.  Item_Fat_Content         -  8523 -  non-null   object 
 5.  Item_Visibility            8523 -  non-null   float64
 6.   Item_Type                  8523 -  non-null   object 
 7.   Item_MRP                   8523 -  non-null   float64
 8.  Outlet_Identifier          8523-  non-null   object 
 9.  Outlet_Establishment_Year  852 -  non-null   int64  
 10.   Outlet_Size                6113 - non-null   object 
 11.  Outlet_Location_Type       8523 - non-null   object 
 12.  Outlet_Type                8523 - non-null   object 
 12 Item_Outlet_Sales          8523 - non-null   float64

Data contains 8523 rows with 12 columns 
'Target column is 'Item_Outlet_Sales

# UNIVARIATE ANALYSIS - Analysis of features

## Distribution of Outlet_Sales
![](https://github.com/JobinJose9660/sales-predictions/blob/main/22.PNG)

1.Above Histogram explains Most of the Outlet sales are in are happening in between 100 to 2000 dollars  in which 
There is no sales over 8000 dollars 
## Stastical Summary of Outlet_Sales
![](https://github.com/JobinJose9660/sales-predictions/blob/main/1.PNG)
1.We can see that average sales of the Items are 1794.3 , maximum Price of the Item is 13086.6,Minimum Price is 33.2 
also there are outliers above 10000 and two above 12000 

## Corelation Analysis
![](https://github.com/JobinJose9660/sales-predictions/blob/main/2.PNG)
1.We can see outlet sales is highly corelated to Item MRP, that means Item MRP plays great role in  predicting sales price , Features such as Item Visibility ,Item Year have negative correlation with sales 
## How Item_MRP related to Outlet Sales
![](https://github.com/JobinJose9660/sales-predictions/blob/main/3.PNG)
1.The scatter plot clearly explains Positive correlation, which means when Item MRP increases Outlet sales increases
## Analysis of Outlet_sales and Outlet Stores
![](https://github.com/JobinJose9660/sales-predictions/blob/main/6.PNG)
1. we can see supermarket Type 3 has more sales than all other type of stores

# Trian Test split
1. Date has been seperated into feature columsn and Target columns('Outlet_Sales)
2. Tp prevent data leakage train test split has been done


# Preprocessing
## Missing Values
1 . Missing values in categorical columns are filled using SimpleImputer with 'Most- Frequent' Statergy
2. Missing values in numerica columns are filled using SimpleImputer with 'Mean'statergy

## Ordinal columns
1. Column 'OutleT-Size' values small , medium and High are changed to 0,1,2 respectively 
## Nominal columns
1.Nominal columns are converted using Onehot encoder () function
## Scaling
1. Scaling of numerical values are done with Standarscalar() funciton
![](https://github.com/JobinJose9660/sales-predictions/blob/main/9.PNG)

# Prediction using Machine learning Model (Which model is best for prediction)
## Error calculation matrixes
 1. mae = mean_absolute_error(y_true, y_pred)
 2. mse = mean_squared_error(y_true, y_pred)
  3. rmse = np.sqrt(mean_squared_error(y_true, y_pred))
  4. r2 = r2_score(y_true, y_pred)

 ## Linear Regresssion
    ## Train Scores
1. scores: MAE: 739.5459094493116, 
2. MSE: 975956.8800610695, 
3. RMSE: 987.9052991360404,   
4. R2: 0.6702241974534979
## Testing Scores
1. scores: MAE: 4399928590710320.0, 
2. MSE: 3.186132127612579e+31, 
3. RMSE: 5644583357177551.0,   
4. R2: -1.1548236158716282e+25

1. Here we can see that there is huge difference between R2 scores of test and train score data, so we can say that the model has High Bias and Variance

## Prediction and modeling using Dummy Regressor
  ## Training Scores
1. scores: MAE: 1360.2184410159132, 
2. MSE: 2959455.7045265585, 
3. RMSE: 1720.306863477141,   
4. R2: 0.0
## Testing Scores
1. scores: MAE: 1326.121044678208, 
2. MSE: 2772144.4627103633, 
3. RMSE: 1664.9758144520788,   
4. R2: -0.004772483978719766

## Regularization and Tuning the model using KnnRegressor by finding the best value of K-Neigbors 
![](https://github.com/JobinJose9660/sales-predictions/blob/main/10.PNG)
1.The best value of K-Neigbors = 19
## Training Scores
1. scores: MAE: 771.9520539094922, 
2. MSE: 1161051.0387542255, 
3. RMSE: 1077.5207834442106,   
4. R2: 0.6076808863946266
## Testing Scores
1. scores: MAE: 767.5310794684976, 
2. MSE: 1189002.6418443376, 
3. RMSE: 1090.4139772785095,   
4. R2: 0.5690422508734834
5. When I used KNeighborsRegressor method  with best K-N neighbor to tune the data we can see scores changed become closer
![](https://github.com/JobinJose9660/sales-predictions/blob/main/11.PNG)

# Modeling using Simple Regression Tree Model - DecisionTreeRegressor
## Training Scores
1. scores: MAE: 1.2005415435245748e-16, 
2. MSE: 2.4643264323299693e-29, 
3. RMSE: 4.96419825584149e-15,   
4. R2: 1.0
## Testing Scores
1. scores: MAE: 984.5860397935243, 
2. MSE: 2095277.1810810468, 
3. RMSE: 1447.5072300617524,   
4. R2: 0.24056019223457958

When we analysing the metrics in DecisionTreeRegressor we can see there see Highvariance(overfit) of the model, so let's tune the model by finding the best Max_depth
![](https://github.com/JobinJose9660/sales-predictions/blob/main/12.PNG)

Best Max_depth is 5
## Predicting using Max_depth 5
## Training Scores
1. scores: MAE: 761.9784955008363, 
2. MSE: 1171332.784431318, 
3. RMSE: 1082.281287111312,   
4. R2: 0.6042066848171654
## Testing Scores
1.scores: MAE: 736.8796499354125, 
2.MSE: 1114471.1152767404, 
3.RMSE: 1055.6851402178304,   
4.R2: 0.5960564372160062


We can see that test and train score become closer so these model is compartively good fit than linear regression and Knnregressor
![](https://github.com/JobinJose9660/sales-predictions/blob/main/13.PNG)

We can see from the scatterplot the prediction are highly showing positive correlation to features in after tuning 

# Conclusion
1. Analyses  of Outlet Sales prediction with different features has been done 
2. Sales prediction is highly related to Item MRP feature.
3. Prediction's are done using Linear Regression model DecisonTreeRegressor Model
4. Evaluation of both models are done using performance metrics, and tuning methods are also used
5. We can see performance metrics DecisonTreeRegressor model resulted as Good Fit compared to Linear Regression 
6. So I’m recommending DecisonTreeRegressor Over Linear Regression
7. DecisionTreeRegressor Model will be more useful for predicting Sales 



























