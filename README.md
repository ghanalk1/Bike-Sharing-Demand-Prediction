# **Bike Sharing Demand Prediction**
## *Problem Description*
### Public rental bike sharing system has been gaining popularity in the recent times.Currently,this system has been introduced in many major cities for enhancement of mobility comfort.It is also a great step towards environmental sustainability and social welfare.
### In order to run this system successfully,it is important to ensure that the rental bikes are available and accessible to the public at the right time,since this reduces the waiting time.Providing the city with a stable supply of rental bikes could become a serious challenge,eventually.Forecasting the number of bikes required at each hour can greatly help in ensuring that there's a stable supply of rental bikes.
### Our objective here,is to predict the Count of Rental bikes required on an hourly basis and to also identify the features which influences the hourly demand for Rental bikes.
![12211](https://user-images.githubusercontent.com/65157529/182558628-f2aaaf75-bf65-4b61-81ba-1fbf97251a1e.jpg)



## *Introduction*
### The Dataset asks a simple question: “prediction of bike count required at each hour for the stable supply of rental bikes”. It is important to make the rental bike available and accessible to the public at the right time as it lessens the waiting time.
### The Dataset contains the following information:
> * Date: year-month-day
> * Rented Bike count: count of bikes rented each hour
> * Hour: hour of the day
> * Temperature: temperature in Celsius
> * Humidity: %
> * Wind speed: m/s
> * Visibility: 10m
> * Dew point temperature: in Celsius
> * Solar Radiation: MJ/m^2
> * Rainfall: mm
> * Snowfall: cm
> * Seasons: Winter, Spring, Summer, Autumn
> * Holiday: holiday/no holiday
> * Functional Day: NoFunc(nonfunctional hours)/Func(functional hours)

## *Steps Involved*
### 1. EDA
### After importing the dataset, our first task is to gain insights from the data. We plot various charts like bar graph, histogram, heat map, line graph etc. for univariate and bivariate analysis. This process helped us figuring out various aspects and relationships among the dependent and the independent variables.
### Conclusions from EDA:
> * In all seasons, demand for bikes is high in morning (8 a.m.) and highest in the evening (around 6p.m.).
> * The demand based on season peaks in summer and is minimum in winter i.e. showing temperature dependence.
> * Demand reduces during weekend.
> * The bike count is highly correlated with Temperature and Hour.
> * Temperature and Dew point Temperature are highly correlated.

### 2. Feature Engineering
### Feature Engineering involves the following steps:
> * The dtype of Date column will not be easy to interpret for the ML model, therefore we decided to extract some features from it. The new columns formed from Date column are Day, Month, Year, Weekday and Weekend. In the end, we drop the Date column.
> * Checking the magnitude of multicollinearity of all the numeric features. It is found that Dew point and Year are causing high multicollinearity, so we decide to drop them.
> * There are many categorical features in our dataset, so we decide to dummify them. After dummification, all the features present are numeric.
> * In the final step, we separate independent, target variables, and perform train-test split.


### 3. Training Models and Hyper parameter Tuning
### Tried Baseline Linear Regression and it did not work great on the data. Eventually XGBoost gave us the best performance of 94.53% (after tuning).
