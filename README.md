
# Seoul-Bike-Sharing-Prediction

![wde](https://user-images.githubusercontent.com/102940106/183284562-01561a10-94a2-488b-9103-cbcfcda0a70d.jpg)

The objective of this work is to predict the trip duration of rental bikes in the Seoul Bike sharing system. The data used include weather information (Temperature, Humidity, Windspeed, Visibility, Dewpoint, Solar radiation, Snowfall, Rainfall), the number of bikes rented per hour and date information.

Currently Rental bikes are introduced in many urban cities for the enhancement of mobility comfort. It is important to make the rental bike available and accessible to the public at the right time as it lessens the waiting time. Eventually, providing the city with a stable supply of rental bikes becomes a major concern. The crucial part is the prediction of bike count required at each hour for the stable supply of rental bikes. The main objective is to make a predictive model, which could help them in predicting the bike demands proactively. This will help them in stable supply of bike wherever needed.

Feature engineering is done to extract additional features from the data. Four statistical models are used to predict the trip duration. 
* (a) Linear regression 
* (b) Decision Tree 
* (c) Random Forest (RF). 
* (d) Gradient boosting machines 
* (e) Extreme Gradient Boosting (XGBoost)

Methodology
EDA
The dataset exploration and visualization resulted in very important insights about the data, including:
1- Boxplot of weather features shows minimal outliers in some features.
2- Data distribution using Histogram shows that 'Visibility', 'Solar radiation', 'Rainfall', and 'Snowfall' are skewed
3-

Boxplot for 'Hour' shows that the rental demand witness significant increase from 7 to 9 AM and then from 17 to 20 PM, which are the working hours in seoul.
Boxplot for 'Seasons' shows that hot seasons (summer & Spring) have more rental rates.
Creating some additional features from the date/time variable like 'day of weak', 'month', 'year' and 'weak of year'
4-

Boxplot for 'month' supports what we get from seasons that summer months (June, July) have the most rental rate.
'Day of weak' and 'Holiday' boxplot assure that the rental rate increases at working days.
5- Pearson linear correlation shows a multicolinearity between Temperature and Dew point temperature.
Preprocessing
All preprocessing steps and feature engineering are combined and implemented in the DataPrep() function with comments explanation for each step.
1- Renaming features with unknown characters.
2- Convert Date column type to datetime type.
3- Feature engineering:

Add Day, month, year and weak of year features.
Add 'RentDemand' feature for high (1) and low (0) working hours.\
Grouping day hours into 4 ranges 'night','morning','afternoon' & 'evening'.\
Grouping continous features Rainfall into 3 groups:
0 --> low
0-5 --> middle
above 5 --> high
Grouping continous features Snowfall into 3 groups:
0 --> low
0-1.2 --> middle
above 1.2 --> high
As Hours, days, months and seasons are cyclic features i.e. hr23 and 0 are very close, we want the model to understand this cycle.get their sin and cos components.
Adding interaction features.
Adding column of total solar radiation per day.
Adding column to identify days where there is no rain and snow combined and days of any.
Adding K-means clustering column of temperature and dew point temp cols.
Applying K-means clustering on the dataset but after scaling.

4- Categorical features encoding:
Binary encode 'Functioning Day' and 'Holiday' features.
Target-based encoding for 'dow', 'month', 'Seasons' and 'Hour' columns.

5- Feature Scaling:
Based on the data distribution we noticed that some features follow normal distribution, some are left or right skewed, so we will apply different scaling techniques based on the feature nature and by several trials these scaling techniques gave best results:
Min-Max scaling left skewed cols (Snowfall and Rainfall).
Log transform wind speed, humidity and Solar radiation.
Reciprocal transformation for Visibility feature.
Calculate Average Rent per hour and day with log-transformation for training data only and then MAP the values to the test set according to each hour or day.
Model Training
The data is splitted to train and validation sets with 90%-10% ratio.
Due to multicolinearity after adding several features, 'Snowfall','Hour' and 'Dew point temperature' are dropped and this improved the model.
XGBoost and CatBoost models are both trained on the dataset and the average of the their predictions is considered as the final prediction.
Results
The used metrics are RMSLE, RMSE and R2-score.



# Conclusion
Predicting the number of bikes rented per hour in Seoul, South Korea.
Performed EDA on the dataset and found features 'Hour', 'Temp.' and 'Season' to be most important. Also performed Feature Engineering to extract some features.
Used many regression algorithms for predicting the number of bikes like Linear Regression, Decision Tree, Random Forest and XGBoost etc.
Also performed hyperparameter tuning on models to improve them further.
Best performing models after tuning, R2-score of Random Forest: 92.25%, XGBoost: 94.53%, CatBoost: 94.46%.

The analysis is done with Seoul Bike data. Six regression techniques Linear Regression, Polynomial regression, Decision Tree, Random Forest, Gradient Boosting, XGB are used to predict the trip duration.This statistical data analysis shows interesting outcomes in prediction methods and also in an exploratory analysis.

The experimental results prove that the XGB model predicts best the trip duration with the highest R2 and with less error rate compared to Linear Regression, Decision Tree, Random Forest, Gradient Boosting.
