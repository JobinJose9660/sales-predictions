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
![](https://github.com/JobinJose9660/sales-predictions/blob/main/1.PNG)

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











##**Libraries**

1.pandas

 2.matplotlib
 
3.seaborn

4.scikit-learn

##Algorithms

6.Linear Regression

7.Decision Tree

8.Random Forest

9.KnNeighbors



