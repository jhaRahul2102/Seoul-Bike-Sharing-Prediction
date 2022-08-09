
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


# Conclusion
Predicting the number of bikes rented per hour in Seoul, South Korea.
Performed EDA on the dataset and found features 'Hour', 'Temp.' and 'Season' to be most important. Also performed Feature Engineering to extract some features.
Used many regression algorithms for predicting the number of bikes like Linear Regression, Decision Tree, Random Forest and XGBoost etc.
Also performed hyperparameter tuning on models to improve them further.
Best performing models after tuning, R2-score of Random Forest: 92.25%, XGBoost: 94.53%, CatBoost: 94.46%.

The analysis is done with Seoul Bike data. Six regression techniques Linear Regression, Polynomial regression, Decision Tree, Random Forest, Gradient Boosting, XGB are used to predict the trip duration.This statistical data analysis shows interesting outcomes in prediction methods and also in an exploratory analysis.

The experimental results prove that the XGB model predicts best the trip duration with the highest R2 and with less error rate compared to Linear Regression, Decision Tree, Random Forest, Gradient Boosting.
