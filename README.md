# Regression_problem_Istanbul_Airbnb

### Explanatory data analysis: 

This dataset is a collection of various Airbnb service offers in Istanbul. It consists of the following variables: 
- <b>id</b> - a variable with a unique identifier of the proposed housing 
- <b>name</b> - the name of the accommodation on the Airbnb service 
- <b>host_id<b> - unique identifier of the host 
- <b>neighbourhood_group<b> - a group of the area in which the housing is located 
- <b>neighbourhood</b> - the area where the housing is located 
- <b>latitude</b> - part of the coordinates of the housing 
- <b>longitude</b> - part of the coordinates of housing 
- <b>room_type</b> - type of room 
- <b>housing price</b> - cost of housing 
- <b>minimum_nights<b> - the minimum number of nights available for selection in this accommodation 
- <b>number_of_reviews_last_review </b>
- <b>reviews_per_month</b> 
- <b>calculated_host_listings_count</b>
- <b>availability_365</b> - housing availability during the year. 

To begin with, it is necessary to determine outliers for predicting the cost of housing using a box-plot graph that reflects the distribution of housing prices in the dataset and defines outliers. 
Based on this schedule, we concluded that all rental offers with a value above 800 conventional units are outliers, so we do not need to consider them in the future.

<br/>
<img src="https://imgur.com/F9AiQ2v.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<br />

After we have selected the necessary offers by removing outliers by cost, we start a new variable: <b>distance_from_the_center_km</b>, which reflects the distance calculated from the coordinates to the city center (We assume that the center of Istanbul will be Taksim Square). 
After that, even at the stage of data preprocessing, after we have made sure that there are no gaps in the data, we smear the necessary variables and reindex the data. Based on the correlation matrix, we get the necessary relationships between variables. 
The last stage of preprocessing is Label encoding, which allows you to write the desired text variables in their numerical display. 
After completing the preprocessing, the necessary transformations in the data and finding out that the housing cost data we are interested in is normally distributed, we can apply models of various regressions for this dataset. 
Implementation of the models: 

### Ordinary least squares (OLS) : 

The first model used is the classical OLS model for regression algorithms. 
Ordinary Least Squares regression <b>(OLS)</b> is a common technique for estimating the coefficient of linear regression equations which describe the relationship between one or more independent quantitative variables and a dependent variable. 

### Ridge model : 

Then we apply the Ridge model. 
Ridge regression is a method of estimating the coefficients of both single and multiple-regression models in scenarios where the independent variables are highly correlated. 
Of course, in our case there is no strong correlation between the variables, but in the future it will turn out that this model will show relatively high score among all applicable to these models. 

### Lasso regression : 

The next model we applied to the data was the Lasso model. 
LASSO (at least absolute shrinkage and selection operator) is a regression analysis method that performs both variable selection and regulation in order to enhance the prediction accuracy and interpretation of the resulting statistical model. 

### Bayesian model : 

The last model I applied to the data was the Bayesian model. Bayesian linear regression is a type of conditional modelling in which the mean of one variable is described by a linear combination of other variables, with the goal of obtaining the posterior probability of the regression coefficient. 
After applying these models, it is necessary to find out about their effectiveness on the data using the following criteria: Explained Variation Score (explains the variance of errors of a given dataset) and R^2 score (the proportion of the variation in the dependent variable that is predictable from the independent variables). 
In our case we choose R^2 and EVS scores because in this case they seem to be the most understandable and definable.  
As follows final R^2 and EVS scores for the applied models are: 

<br/>
<img src="https://imgur.com/swbGIvE.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<br />
 
It can be seen that these results are not good for the data, which means that regression models do not work well on these data, however, it can also be concluded that most likely, the proposed parameters are not fundamental for determining the cost of housing, because the cost of real estate is also affected by seasonality, subjective assessment of the owner, good repairs and even the floor on which the proposed housing is located. 

### Improving scores: 

In order to finally make sure that for regression models, the market is not good enough to predict the cost of housing, we try to apply more complex models in order to increase the scores of the applied model. 
The results of different scores are shown below, which confirm the fact that the regression model of none of the many types is suitable for the proposed data set, since even improving hyper-parameters does not give the desired result and only slightly improves the score of the R^2 and Explained variation indicators. 

### Result: 

Summing up, we can say that of all the indicators demonstrating relatively poor model performance. The Gradient boosting model showed the best result. The indicators of this model are as follows: 

<br/>
<img src="https://imgur.com/NrvsAJe.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<br />
