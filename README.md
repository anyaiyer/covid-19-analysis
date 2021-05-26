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
- full_grouped.csv : day to day country wise number of cases (also includes county/state/province)
- country_wise_latest.csv : latest number of cases in each country
- worldometer_data.csv :  latest data from https://www.worldometers.info/
- day_wise.csv : day wise number of cases without country level data

(all information on the csv files is from the [kaggle dataset](https://www.kaggle.com/imdevskp/corona-virus-report))
## Model
Predictions for confirmed cases, recovered, deaths, and were made based on the dataset. To make these predictions, I used Prophet.
[Prophet](https://facebook.github.io/prophet/#:~:text=Prophet%20is%20a%20procedure%20for,daily%20seasonality%2C%20plus%20holiday%20effects.&text=Prophet%20is%20open%20source%20software,download%20on%20CRAN%20and%20PyPI.) is a forecasting tool from Facebook that uses data to predict future behavoir. Prophet gives a future trend to the data instead of just predictions.
It makes forecasts based on irregular holidays and year, weekly, and daily seasonality.

