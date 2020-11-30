# ALPHA-Q-DATA-ANALYTICS-PROJECT
A Team Project for predicting price of used cars on craiglist using various ML models .
TEAM MEMBERS:
SUMUKH R R    - PES2201800078
K RAHUL REDDY - PES2201800267
PRAMATH R RAO - PES2201800364
N SAI CHARAN  - PES2201800281                                                                  

Step1- Run the Datapreprocessing.ipynb file.
The dataset was taken from kaggle which scraped from craiglist by austin reese
Link for Dataset:https://www.kaggle.com/austinreese/craigslist-carstrucks-data?select=vehicles.csv
In this we have used various preprocessing techniques like to fill the null values and also to fill the missing values.
The unwanted columns were discarded and the rows for which missing values cant be interpreted were dropped and the ffill method was used for many of them.
Estimated the score on the entire dataset by filling missing values by 4 different iterative imputer which are as follows:
Estimating BayesianRidge,
Estimating DecisionTreeRegressor,
Estimating ExtraTreesRegressor,
Estimating KNeighborsRegressor,
Estimated the score on the entire dataset by filling missing values by mean and median.
We converted categorical data into numerical data to normalize and standardize the data.
We also removed the outliers from the main columns such as Price, year, Odometer.
Finally we acheived dataset with o null values and no outliers and a normalised dataset.
The final dataset is uploaded with code as zip file named VehicleFinal.csv





Step2- Run the Datavisualisation.ipynb file:
We used various visualisation techniques to show the comparison between the main category that is price with  rest of the features of car.
We also implemented a heat map and correlation map at lasy to tell about the correlation of the price with other features like year and Odometer.
we specified how the price changes with the change in features of car respectively.







Step3- Run the ML-Models.ipynb file.
The dataset was scaled and normalised before implenting in models
The dataset was split into training and test set of 90% and 10% respectively.
we have done testing in 8 models which are mentioned as below:

1.	LINEAR REGRESSION:
In statistics, statistical regression may be a linear approach to modelling the link between a scalar response (or dependent variable) and one or more explanatory variables
(or independent variables). rectilinear regression is next step after correlationit is employed after we want to predict the worth of an variable supported the opposite value.
Coefficients: The sign of every coefficient indicates the direction of the connection between a variable and therefore the response variable.
A positive sign indicates that because the variable quantity increases, the response variable also increases.
A negative sign indicates that because the variable quantity increases, the response variable decreases.
Considering the figure given in code which is got after performing the model on dataset, simple regression suggests that year, cylinder, transmission, fuel, odometer these five variables are the foremost important.


2.	RIDGE REGRESSION:
Ridge Regression may well be a way for analyzing statistical method data that suffer from multicollinearity. When multicollinearity occurs, method estimates are unbiased, but their variances are large so they may even be aloof from actuality value.
Considering the figure in code which is results of performing model on the dataset, Ridge regression suggests that year, cylinder, transmission, fuel, odometer these five variables are the foremost important.
Linear and Ridge regression during this give same output 

3.	LASSO REGRESSION:
Lasso regression is type of regression that uses Shrinkage. The goal of lasso regression is to urge the subset of predictors that minimizes prediction error for a quantitative response variable. The lasso does this by imposing a constraint on the model parameters that causes regression coefficients for some variables to shrink toward zero.But for this dataset, there is no need for lasso regression as there no much difference in error.
The results of lasso regression is additionally same as other 2 because the foremost variables determined by all three models are same and so the shrinkage doesn’t give much difference. 

4.	KNN-REGRESSOR:
KNN regression can be a non-parametric method that, in an intuitive manner, approximates the association between independent variables and so the continual outcome by averaging the observations within the identical neighbourhood.k-NN may be a kind of instance based learning, or lazy learning, where the function is just approximated locally and each one computation is deferred until function evaluation.From the model and graph given in code, for k=5 KNN give the tiniest amount error. So dataset is trained using n_neighbors=5 and metric=’euclidean’.
The performance KNN is healthier and error is decreasing with increased accuracy 

5.	RANDOM FOREST:
A random forest may well be a meta estimator that matches type of classifying decision trees on various sub-samples of the dataset and uses averaging to boost the predictive accuracy and control over-fitting. In our model, 180 decisions are created with max_features 0.5.
From this model we are ready to infer that year is that the foremost significant feature of a car then comes Odometer.

6.	BAGGING REGRESSOR:
A Bagging regressor is an ensemble meta-estimator that matches base regressors each on random subsets of the primary dataset and then aggregates their predictions (either by voting or by averaging) to form a final prediction.Such a meta-estimator can typically be used as a way to cut back the variance of a black-box estimator (e.g., a choice tree), by introducing randomization into its construction procedure then making an ensemble out of it.
In our model, we used Decision tree regressor because the estimator with max_depth=20 which creates 50 decision trees .from this we will infer The performance of Random Forest is far better than Bagging regressor.

7.	ADABOOST REGRESSOR:
AdaBoost is also accustomed boost the performance of any machine learning algorithm. Adaboost helps you combine multiple “weak classifiers” into one “strong classifier”.
This model and plot given in code tells us that year is that the most vital feature of a car then odometer.
In our model, DecisionTreeRegressor is utilized as an estimator with 24 max_depth and creates 200 trees & learning the model with 0.6 learning_rate

8.	XG BOOST REGRESSOR:
XGBoost is an ensemble learning method.XGBoost is an implementation of gradient boosted decision trees designed for speed and performance. the sweetness of this powerful algorithm lies in its scalability, which drives fast learning through parallel and distributed computing and offers efficient memory usage. Plot given in code is usually the easy bar plot in descending of importance which illustrates that which feature may be a crucial feature of a car is more important.According to XGBoost, Odometer may be a important feature whereas from the previous models year could be a crucial feature.
In this model,200 decision trees are created of 24 max depth and also the model is learning the parameter with a 0.4 learning rate.
So keeping all the models in mind we will conclude that both year and odometer are impoertant features of used car.

MODELS ACCURACY AND PERFORMANCE:
From the table given in code of all accuracy we can see that XG Boost regressor has the very best accuracy of 89.6623% and random forest stands second with 87.5979% accuracy.


From this project we can conclude that the XG Booster Regressor is best for predicting the price of the used cars and this project can be kept as reference by sellers and buyers while looking for the used cars.



