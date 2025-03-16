# SC5002_Lab_Assignmnet2
 ## Lab Assigment 2 for SC5002 (Written by Misaki and Tom (Wenbo))
 ### Project Overview 
 Our project aims at prediction of CO2 emissions by ships travelling in Nigerian and understanding the use cases of linear regression and ridge regression with this real-world example. 
 
 ### Dataset
 Our dataset consists of 10 different variables. "ship_id", "ship_type", "route_id",  "month", "fuel_type" and "weather_conditions" are categorical variables. "distance", "fuel_consumption", "CO2_emissions" and "engine_efficiency" are numerical variable. "CO2_emission" is the target variable in this project.
 
 ### Steps taken:
 #### 1. Data cleaning
 From the result of df.describe(), it is said that this dataset does not have any missing values. Therefore, handling missing values is not required.

 #### 2. Drop "ship_id"
 By observing the variables, it is noticable that "ship_id" is irrelavent data since the unique identifications of ships will not contribute to the prediction of CO2 emission by a ship. Therfore, "ship_id" is dropped from the dataframe. Other data can be considered relavent for CO2 emissions. 

 #### 3. Split data into inputs and output, and One-hot encoding
 Before one-hot encode the categorical variable, the data is splitted into inputs and output. Then, one-hot encoding is performed to convert categorical variables into binary (0/1) for the model to be able to process the categorical variables. 

 #### 4. Split inputs and output into traning and testing sets, and standard scalling
 The inputs and output are splitted into traning and testing set in the ratio of 8 to 2. Then, the splitted inputs are scaled using StandardScaler. The purpose of scaling after splitting the inputs is to ensure that the test set is completely unseen. 

 #### 5. Build linear and ridge regression model to train and then use the test set to evaluate
 The both models are trained then evaluated using the test set and regression evaluation metrics: R-squared value, MSE and MAE. Also, using for loop, alpha value of range of 0.0 to 10 with the step of 0.001 is used one by one to find out the best alpha value in the range. The best alpha value is determined by the maximum R-squared value. k-fold Cross-Validation is also implemented to evalueate both models and reduce variance in performance estimate. In addition to all, Graphs of True value vs Predicted value are protted to visually see how well the models perform. 
 
 #### 6. Check for multicollinearity using VIF (Variance Inflation Factor) and correlation coefficient
 Variance Inflation Factor allows us to know how each predictor is collerated to others. Thus, it can be used to identify if multicollinearity, which is a potential cause of overfitting in learn regression model, exists. In addition to this, a heatmap of coefficient matrix is drawn to visually represent which predictor is correlated to another. 

 ### Insights
 Interestingly, the best alpha value, which is the penalty term to cost function penalty for large coefficients, turns out to be zero correcting to 1 decimal place. As a result, both linear and ridge regression models have same performance with same values for all evaluation parameters. However, by using VIF, we manage to find that most variables are of moderate multicollinearity with other predictors since their VIFs are slightly larger than 1, while ‘distance’ (VIF>13) and ‘fuel _consumption’ (VIF>17) showed high multicollinearity to other predictors. From the heatmap of correlation matrix and the highly correlated pair output, it can be said that 'distance' and 'fuel_consumption' are highly collerated to each other. From the results, it can be observed that although ridge regression is better than linear regression for many situations due to the regularization factor alpha that prevents overfitting, both models are suitable for our case because of relatively low or implicit multicollinearity that implies low risk of overfitting.
