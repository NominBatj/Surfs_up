# Surfs up

Weather analysis with Python, SQLite, SQLAlchemy, and Flask

## Overview of the Analysis

The purpose of this analysis is to examine weather trends (precipitation, temperature) in June and December on Oahu, Hawaii. An investor wants to determine if the surf shop and ice cream shop business is sustainable year-round. The main problem for the investor is rainfall, which forces the store to close too often. To analyze Hawaii weather data, SQLAlchemy were used to query the SQLite database.

For the analysis we:
- accessed to meteorological data in a SQLite file;
- wrote queries to examine temperature data collected in June and December;
- calculated summary statistics (especially collected minimum, maximum and average temperatures).
## Results
Following are the results for June and December:

![June Temps](https://user-images.githubusercontent.com/66500222/175759242-d7d504a8-bc4b-4ece-8c15-d0eaefacde06.png)


![Dec Temps](https://user-images.githubusercontent.com/66500222/175759289-d8550d64-fcfc-4667-8bb5-ee267737d893.png)

- The mean temperature of 75°F for June is higher than the mean temperature of 71°F for December. Average summer and winter temperatures differ by less than 4 degrees. This shows that year-round weather isn't very changeable and it's rarely too cold for surfers and tourists visit the island.
- Maximum temperatures of 85°F for June and 83°F for December are also remarkably similar.
- Minimum temperatures of 56°F (December) and 64°F (June) show the most variance and reflect a much lower temperature level in December, which may not be conducive to surfing.

## Summary

In conclusion of our analysis, we have included two queries to help the investor to make decision whether to open the surf shop in Oahu. 

#### Number of stations from which the precipitation data is being collected  
```
session.query(func.count(Station.station)).all()
```

#### Query that retrieves precipitation scores
```
dec_prep =  session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 6 ).all()
print(dec_prep)
```
