### Project 5: Group project focused on prediction of fire risk based on meteorological data

### Problem Statement

This project uses weather data in a classification model to determine which of the Western US states are at high risk of large fires, in order to improve local preparedness.

### Summary

Following a record-setting fire season in 2020 which damaged or destroyed 10,488 structures, caused at least 31 fatalities, and burned 4.2 million acres (more than the previous three years combined) in California, and resulted in $195M's worth of damages in Colorado, we decided to investigate the relationship between weather data (precipitation, temperatures, and drought) and the occurrence of fires, and to attempt building a model which would predict fires and help prevent the associated damage.
Following National Wildfire Coordinating Group's convention which groups fires into ranges of fire size based on the number of acres within the final fire perimeter, we chose to set up our model as a a multi-classification where class "A" corresponds to fires smaller than 0.01 acres, "B" - 0.225 acres, "C" - 10 acres, "D" - 100 acres , "E" - 300 acres , "F" - 1000 acres, and "G" - fires larger than that.

### Data

We used two sources of data which were studied through EDA and then combined into a single data frame which informed the modeling phase:
- Meteorological dataset covering 120 years of weather information for the 11 western US states of: AZ, CA, CO, ID, NM, NV, MT, OR, UT, WA, and WY, including metrics and indexes describing precipitation, temperatures, and droughts;
- A spatial database of 1.88 million wildfires that occurred in the United States from 1992 to 2015 and burned 140 million acres burned during the 24-year period, originally generated to support the national Fire Program Analysis (FPA) system and obtainable from Kaggle.com, including: discovery date, final fire size, and a point location (latitude and longitude).

The two datasets were combined by matching weather information and fire data on the combination of month-year-state for each of the fires that burned from 1992 to 2015 in the eleven states of interest.
Because the effects of weather on fire can be delayed, we additionally included in our modeling data trailing 12-, 9-, 6-, and 3-month averages for precipitation, temperature, and two drought indexes.

**GoogleMaps data? Additional NOAA data?

### Key Observations

1. Wildfires are extremely complex phenomena. While the NOAA data offered a set of independent variables which fairly comprehensively described weather history, we were not able to include in our model other important factors which also affect final fire size, such as wind or terrain features (e.g. land cover or incline).
2. Switching our target variable from a continuous one (fire size, in acres) to a multi-class problem improved the score from an R2 of under 10% to accuracy of over 60%. Further, re-defining the problem as a binary classification of "large" vs "small" fires drove accuracy up to 62-77%, depending on the threshold chose to delineate between the two classes.
3. Because our goal was to improve preparedness and help contain damage from wildfires without putting efforts into preventing fires which weren't likely to spread, our ultimate focus was on increasing the recall of our model, and moreover - to increase its recall with regards to large fires.
4. Each of the seven-class classifications requires sklearn's estimators to perform 7 x (7-1) / 2 = 21 separate classifications - fitting some of the estimators we evaluated (e.g. SVM) was very computationally expensive.
5.

### Conclusions and Recommendations

...

---
### Next Steps

...

---
