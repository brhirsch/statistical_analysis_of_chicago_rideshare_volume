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

Using Louvain Clustering, I identified 4 underlying community structures. Clustering 800+ nodes into 4 clusters also allowed me to easily test each forecasting method against 4 time-series datasets, as opposed to having to test and validate against 800 time-series. 

![Network 3](https://github.com/brhirsch/Forecasting-Chicago-Rideshare-Volume-/blob/master/images/network3.PNG)


### Time-Series Forecasting Models

In order to identify which method to use to forecast hourly rideshare volume in every neighborhood in Chicago, I tested various statistical methods on aggregated data based on the clusters in the network analysis. 

The methods I tested using walk-forward-validation were SARIMA, TBATS, and Facebook's Prophet. 



```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.




