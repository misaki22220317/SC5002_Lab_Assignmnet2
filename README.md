# SC5002_Lab_Assignmnet2
 ### Lab Assigment 2 for SC5002
 #### Project Overview 
 Our project aims at analyzing the factors that influence the CO2 emissions of different types of ships travelling in Nigerian waterways and understanding characteristics and potential improvements of linear regression and ridge regression with this real-world example. 
 
 #### Dataset
 Apart from the emission amount and ship type, our dataset also shows information such as route taken, distance travelled, weather condition, and engine efficiency of corresponding ships. After removing irrelevant feature, we encode the selected categorical variables using One-Hot Encoding and perform the ‘train-test split’. 
 
 #### Steps taken
 We then use the handled categorical features, along with continuous numerical variables, to build and train our models of linear regression and ridge regression. MSE, MAE, and R-squared values are used to evaluate our models, while (mean) cross validation scores are also calculated. 
 
 #### Insights
 Interestingly, the best alpha value, which indicates optimal penalty for large coefficients in ridge regression, turns out to be zero correcting to 1 decimal place. As a result, both linear and ridge regression models have same performance with same values for all evaluation parameters. However, by using VIF, we manage to find that most variables are of moderate multicollinearity with other predictors since their VIFs are slightly larger than 1, while ‘distance’ (VIF>13) and ‘fuel _consumption’ (VIF>17) showed high multicollinearity to other predictors. From the heatmap of correlation matrix and the highly correlated pair output, it can be said that 'distance' and 'fuel_consumption' are highly collerated to each other. From the results, it can be observed that although ridge regression is better than linear regression for many situations due to the regularization factor alpha that prevents overfitting, both models are suitable for our case because of relatively low or implicit multicollinearity that implies low risk of overfitting.
