# covid-19-analysis
COVID-19's effect on the entire world is apparent as we are struggling to fight this deadly virus. 
The first COVID-19 case was reported on December 31, 2019 in Wuhan, China. 
On January 21, 2020, the CDC (Center for Disease Control) confirmed the first COVID-19 case in the U.S. ("A Timeline of Covid-19 Developments in 2020"). 

Since then, cases have risen exponentially and numerous precautionary measures have been taken to prevent the spread of the virus. By May 26, 2021, there were 168 million cases around the world with 3.49 million deaths. AI, machine learning, and data science allows us to analyze the spread of COVID-19 to better understand the virus. It also allows us to help inform the world of new discoveries around COVID-19. 

![download](https://user-images.githubusercontent.com/75640165/119728300-2691f100-be28-11eb-9dcd-3a74360577aa.jpg)
## Download Data
The data for this repo comes from kaggle. You can visit the dataset here: https://www.kaggle.com/imdevskp/corona-virus-report 

Note: The data used for this project includes cases from January 2020 to July 2020. The data is not very recent. 

## Data Specifics
4 csv files were used:
- [full_grouped.csv](https://github.com/anyaiyer/covid-19-analysis/blob/main/full_grouped.csv) : day to day country wise number of cases (also includes county/state/province)
- [country_wise_latest.csv](https://github.com/anyaiyer/covid-19-analysis/blob/main/country_wise_latest.csv) : latest number of cases in each country
- [worldometer_data.csv](https://github.com/anyaiyer/covid-19-analysis/blob/main/worldometer_data.csv) :  latest data from https://www.worldometers.info/
- [day_wise.csv](https://github.com/anyaiyer/covid-19-analysis/blob/main/day_wise.csv) : day wise number of cases without country level data

(all information on the csv files is from the [kaggle dataset](https://www.kaggle.com/imdevskp/corona-virus-report))
## Model
Predictions for confirmed cases, recovered, and deaths are based on the dataset. To make these predictions, I used Prophet.
[Prophet](https://facebook.github.io/prophet/#:~:text=Prophet%20is%20a%20procedure%20for,daily%20seasonality%2C%20plus%20holiday%20effects.&text=Prophet%20is%20open%20source%20software,download%20on%20CRAN%20and%20PyPI.) is a forecasting tool from Facebook that predicts time series data. It gives a future trend to the data instead of just predictions. 
Prophet makes forecasts based on irregular holidays and year, weekly, and daily seasonality. It automatically detects changes in trends by selecting points from the data. 

## Prophet vs. Neural Networks
In this project, Prophet was easier to work with than Neural Networks and had better results.

Prophet's trend for confirmed, recovered, and death cases matched up accurately with the true values. 
Values from the dataset are indicated with the black dots and the predicted trend is represented through the blue line. 

Confirmed:

<img width="768" alt="Screen Shot 2021-05-27 at 5 27 35 PM" src="https://user-images.githubusercontent.com/75640165/119912907-44875080-bf11-11eb-9f91-a8ca69fde643.png">

Deaths:

<img width="781" alt="Screen Shot 2021-05-27 at 5 27 44 PM" src="https://user-images.githubusercontent.com/75640165/119913340-8e246b00-bf12-11eb-80e0-bb325b5d6522.png">

Recovered: 

<img width="770" alt="Screen Shot 2021-05-27 at 5 28 09 PM" src="https://user-images.githubusercontent.com/75640165/119913361-9bd9f080-bf12-11eb-8825-3f5a173ecfec.png">



My Neural Network model appeared to be converging to the minimum, but the root mean squared error and mean absolute error were very high. Mean absolute percentage error and explained variance score was okay. This might be because the dataset (day_temp) only has 188 entries, affecting MSE and MAE. 

| Type | Root Mean Squared Error (RMSE)| Mean Absolute Error (MAE)| Explained Variance score| Mean Absolute Percentage Error (MAPE)|
|--|--|--|--|--|
| Neural Network | ~ 2580990.190 | ~ 1830224.206|  ~ 0.745|~14.928|

Model Loss Plot:

<img width="723" alt="Screen Shot 2021-06-03 at 4 46 39 PM" src="https://user-images.githubusercontent.com/75640165/120725653-4d38d300-c48b-11eb-9d36-1af9998e654d.png">

Though both models had good performances, the Prophet model ultimately did better.



## Use
[Covid-19 EDA](https://github.com/anyaiyer/covid-19-analysis/blob/main/Covid-19%20EDA.ipynb) contains all plots and visualizations.

[Covid-19 Models](https://github.com/anyaiyer/covid-19-analysis/blob/main/Covid-19%20Models.ipynb) contains the code for the models.

To view all the interactive plots, visit my [kaggle notebook](https://www.kaggle.com/anyaiyer/covid-19-visualization-predictions-prophet).

Use of matplotlib, pandas, numpy, seaborn, scikit learn, tensorflow, fbprophet, and plotly is needed. Update to Python 3.8 is recommended.
