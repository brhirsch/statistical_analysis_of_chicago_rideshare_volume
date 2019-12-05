# Forecasting Chicago Rideshare Volume

The goal of this project was to take open source rideshare data collected by the city of Chicago, and apply machine learning techniques for analysis. In this project I perform a network analysis to visualize the data geographically, utilize louvain clustering to identify underlying community structures, and test performance of various time-series forecasting methods.

## Data Collection

All data was downloaded using the city of Chicago's Open Data Portal.

The data used included 65M+ rides from November to April 2019

Link: https://data.cityofchicago.org/Transportation/Transportation-Network-Providers-Trips/m6dm-c72p

### Network Analysis

To take advantage of the geolocation features in the dataset, I created a network using pickup/dropoff census tracts as nodes, and overall ride volume as edges.

![Network 1](https://github.com/brhirsch/Forecasting-Chicago-Rideshare-Volume-/blob/master/images/network1.PNG)


Plotting over a map of Chicago and changing the size of each node to reflect relative rideshare volume lets you easily see where rides are concentrated.

![Network 2](https://github.com/brhirsch/Forecasting-Chicago-Rideshare-Volume-/blob/master/images/network2.PNG)

<img src="https://github.com/brhirsch/Forecasting-Chicago-Rideshare-Volume-/blob/master/images/network1.PNG" width="1300" height="500">


Using Louvain Clustering, I identified 4 underlying community structures. Clustering 800+ nodes into 4 clusters also allowed me to easily test each forecasting method against 4 time-series datasets, as opposed to having to test and validate against 800 time-series. 

![Network 3](https://github.com/brhirsch/Forecasting-Chicago-Rideshare-Volume-/blob/master/images/network3.PNG)


### Time-Series Forecasting Models

In order to identify which method to use to forecast hourly rideshare volume in every neighborhood in Chicago, I tested various statistical methods on aggregated data based on the clusters in the network analysis. 

The methods I tested using walk-forward-validation were SARIMA, TBATS, and Facebook's Prophet. Overall, Prophet performed the best and was used to create forecasts for the 800+ census tract locations. 

![Results](https://github.com/brhirsch/Forecasting-Chicago-Rideshare-Volume-/blob/master/images/model_results.PNG)


## Tableau Dashboard 

I connected US Census data using census tract identification numbers, and created an interactive Tableau dashboard to showcase the results of the project.

Link: https://public.tableau.com/profile/brandin2738#!/vizhome/ChicagoRideshareForecastDashboard/Dashboard1

![Results](https://github.com/brhirsch/Forecasting-Chicago-Rideshare-Volume-/blob/master/images/dashboard.PNG)
