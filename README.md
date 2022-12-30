# Surfs_Up_Analysis
## Overview of the Analysis

To determine the feasibility of a combination ice cream and surf shop in Hawaii, we analyzed historical weather data to see if it's warm enough to keep the shop profitable year round. We picked the months of June and December to represent summer and winter months and filtered our dataset to obtain daily temperature data for both months between 2010 and 2017. We then used these data to calculate summary statistics to paint a picture of the typical weather in Hawaii during both months. 

## Results

Our analysis indicates that weather is pretty homogenous year round in Hawaii.

* Maximum temperature in June was 85* compared to 83* in December
* Minimum temperature in June was 64* compared to 56* in December
* Average tempearture in June was 74.9* compared to 71* in December

## Summary

The temperatures in highway year round are ideal for both ice cream and surfing. This means that our ice cream/surf shop combo has a good chance of being successful! However, it would be a good idea to check how much precipitation Hawaii gets in June and July instead of just looking at temperatures. We can easily query this data from our SQLite dataset with the two following queries:

* june_precip = session.query(Measurement.date, Measurement.prcp).filter(extract('month',Measurement.date) == 6).all()
* december_precip = session.query(Measurement.date, Measurement.prcp).filter(extract('month',Measurement.date) == 12).all()

Once these queries are converted to dataframes and the df.describe() funciton is performed on them, the following summary statistics are displayed: 

![June Precip](https://user-images.githubusercontent.com/104707395/210108900-1677f15d-755a-4a40-996e-118bec98ab76.png)

![December Precip](https://user-images.githubusercontent.com/104707395/210108924-3c918ff2-99e5-4df9-89eb-6dcdf7c23555.png)

On average, there is more precipitation in December than June, which could slow down business some when coupled with the cooler temperatures. However, the business will still have a good chance of being succesful. 
