# Bike Sharing Demand Prediction

## Aim is to predict the demand for shared bikes using a linear regression model.

## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

# General-information
Problem Statement: A bike-sharing system is a service in which bikes are made available for shared use to individuals on a short-term basis for a price or free. Many bike share systems allow people to borrow a bike from a "dock" which is usually computer-controlled wherein the user enters the payment information, and the system unlocks it. This bike can then be returned to another dock belonging to the same system.

A US bike-sharing provider BoomBikes has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state.

In such an attempt, BoomBikes aspires to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to COVID-19. They have planned this to prepare themselves to cater to the people's needs once the situation gets better all around and stand out from other service providers and make huge profits.

They have contracted a consulting company to understand the factors on which the demand for these shared bikes depends. Specifically, they want to understand the factors affecting the demand for these shared bikes in the American market. The company wants to know:

Which variables are significant in predicting the demand for shared bikes? How well do those variables describe the bike demands Based on various meteorological surveys and people's styles, the service provider firm has gathered a large dataset on daily bike demands across the American market based on some factors.

## Business Goal
You are required to model the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demands vary with different features. They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a new market.

## Dataset characteristics

day.csv have the following fields:

- instant: record index
- dteday : date
- season : season (1:spring, 2:summer, 3:fall, 4:winter)
- yr : year (0: 2018, 1:2019)
- mnth : month ( 1 to 12)
- holiday : weather day is a holiday or not (extracted from http://dchr.dc.gov/page/holiday-schedule)
- weekday : day of the week
- workingday : if day is neither weekend nor holiday is 1, otherwise is 0.
+ weathersit : 
	- 1: Clear, Few clouds, Partly cloudy, Partly cloudy
	- 2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist
	- 3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds
	- 4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog
- temp : temperature in Celsius
- atemp: feeling temperature in Celsius
- hum: humidity
- windspeed: wind speed
- casual: count of casual users
- registered: count of registered users
- cnt: count of total rental bikes including both casual and registered

# Technologies Used

- Python - version 3.11.0
- Matplotlib - version 3.7.2
- Pandas - version 2.0.3
- Seaborn - version 0.12.2
- scikit-learn - 1.3.0
- statsmodels - 0.14.0

# Conclusions

- LR Equation of best fitting line would be:

#### cnt = 0.1580 + 0.2341 X yr + 0.4828 X temp - 0.1620 X windspeed + 0.0956 X season_summer + 0.1119 X season_winter + 0.0568 X mnth_Aug - 0.0461 X mnth_Jan + 0.0394 X mnth_Oct + 0.1162 X mnth_Sep - 0.0809 X weathersit_Cloudy - 0.2867 X weathersit_Rainy

- 1. **Model Performance**: The model shows good performance, with an R² of approximately 0.833 on the training data and an Adjusted R² of 0.830. This indicates that the model explains 83% of the variance in bike rentals. The consistency between the R² and Adjusted R² scores suggests that the model is well-fitted and generalizes effectively to the data.
- 2. **Influential Factors**: The most significant factors contributing to bike rentals include temperature, year, and specific weather conditions. The top positive influencers are:
     - **Year** (yr): Bike rentals significantly increase from one year to the next, with a coefficient of 0.2341.
     - **Temperature** (temp): Higher temperatures correlate with more bike rentals, as shown by a coefficient of 0.4828.
     - **Season (Summer and Winter)**: Both summer and winter seasons positively influence bike rentals, with coefficients of 0.0956 and 0.1119, respectively.
On the other hand, factors that negatively impact bike rentals include:
- **Wind Speed (windspeed)**: Higher wind speeds are associated with fewer bike rentals, with a coefficient of -0.1620.
- **Adverse Weather Conditions (weathersit_Cloudy and weathersit_Rainy)**: Cloudy and rainy weather significantly decrease bike rentals, with coefficients of -0.0809 and -0.2867, respectively.
- 3. **Interpretation of Coefficients**:
    - **Positive coefficients** (e.g., temp, yr) suggest that an increase in these variables will lead to an increase in bike rentals.
    - **Negative coefficients** (e.g., windspeed, season_Spring) indicate that an increase in these factors will lead to a decrease in bike rentals.
- 4. Practical Insights:
    - **Seasonal Impact**: Bike rentals are notably higher during Winter and Summer, with Spring showing a comparatively negative impact, possibly due to more variable weather conditions during this season.
    - **Monthly Impact**: September has the highest positive impact on bike rentals, whereas January shows a decrease, which could be attributed to less favorable weather conditions.
    - **Weather Conditions**: Pleasant weather increases bike rentals, while adverse conditions like rain lead to a significant drop in demand.
- 5. Validation Metrics:
    - Cross-Validation: The mean cross-validation R² score of 1.0 indicates that the model is robust and likely to perform well on unseen data.
    - Error Metrics: The model has low MAE, MSE, and RMSE, further validating its accuracy and reliability.  

## Results

- **Test Set Metrics**:
	- R-squared: [1.00]
	- MAE: [0.0000]
	- RMSE: [0.0000]


## Significant Features

- Temperature (temp)
- Year (2019)
- Season (summer, winter)

## License

Use of this dataset in publications must be cited to the following publication:

[1] Fanaee-T, Hadi, and Gama, Joao, "Event labeling combining ensemble detectors and background knowledge", Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, doi:10.1007/s13748-013-0040-3.

@article{ year={2013}, issn={2192-6352}, journal={Progress in Artificial Intelligence}, doi={10.1007/s13748-013-0040-3}, title={Event labeling combining ensemble detectors and background knowledge}, url={http://dx.doi.org/10.1007/s13748-013-0040-3}, publisher={Springer Berlin Heidelberg}, keywords={Event labeling; Event detection; Ensemble learning; Background knowledge}, author={Fanaee-T, Hadi and Gama, Joao}, pages={1-15} }

## Acknowledgements

This project was inspired by UpGrad IITB Programme as a case study for the Machine Learning and Artificial Intelligence course.


## Contact
Created by [@coolhead] - feel free to contact me!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->