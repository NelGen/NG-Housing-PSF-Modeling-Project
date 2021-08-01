# Housing Price Per Square Foot Analysis

## Business Case:
* Analyze the affects of various home features on price per square foot (PSF)

## Goals:
* Discover what features have a significant effect on PSF along with the magnitude using linear regression modeling 

## Sources:
* The provided 2015 Kings County data
* Google Maps for geographical/location data

## Strategies:
* Feature Engineering:
    1. PSF - My target variable is engineered as a ratio of Price to Square Feet Above Ground from the provided data set
    2. Living to Lot Ratio - The ratio of total size of the home to total area of the lot its on.  The larger the ratio, the larger the        house in comparison to the lot
    3. Recent Renovations - Records whether a home was renovated within the last 27 years.  Any renovations older than 27 years likely to require an update
    4. Basement - Records whether a home has a basement or not
    
* Exploring Feature Distributions and Linearity Checks Against PSF:
    1. How normally distributed are the features?
    2. How linearly related are these features to PSF?
    3. Want to keep as many features and data points as possible

* Linear Regression Modeling
    1. Applying transformations to features to obtain strongest linear relationship to PSF
    2. Removing any insignificant features from the model
    3. Finding the highest R-Squared and lowest RMSE values along with smallest difference between train/test results
    4. Validating the remaining normality and homoscedasticity assumptions for linear regression models

# Findings

## Location
* Location has the largest impact on PSF.
    1. Zip Codes
        a. Using 98001 as a baseline.  Similar homes located in 98004, 98039, 98109 or 98119 can be valued upwards of 146% to 240% more per square foot
    2. Waterfront
        a. Homes with a waterfront have 97% higher PSF than similar homes without
    3. Living to Lot Ratio
        a. Every 1 unit increase to the ratio of living square feet to lot size leads to a 10% decrease in PSF for similar homes
        
        
This is a map with the top 5 highest PSF zip codes in lighter color and 5 lowest PSF zip codes in darker.
![Highest PSF Zipcodes](https://github.com/NelGen/NG-Housing-PSF-Modeling-Project/blob/main/data/high_zips.PNG)

For comparison, the more expensive arears are located in northern Kings County near the heart of the city and the cheaper zip codes are to the south.  To note, some of these cheaper zipcodes also contain airports.
![Geography](https://github.com/NelGen/NG-Housing-PSF-Modeling-Project/blob/main/data/kings_county_map.PNG)  
   

## Other Home Features
* Although not as significant as location, these features have an impact on PSF as well:
    4. Bedrooms
        a. Every additional bedroom lowers PSF by 6% for similar homes
    5. Floors
        a. Every additional floor lowers PSF by 11% for similar homes

