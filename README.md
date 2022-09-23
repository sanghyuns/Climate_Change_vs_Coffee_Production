# Project 4: Climate Change and the Future of Coffee


## Contents:
- [Introduction](#Introduction)
- [Problem Statement](#Problem-Statement)
- [Software Requirements](#Software-Requirements)
- [Executive Summary](#Executive-Summary)
- [Recommendations & Conclusions](#Reccomendations-&-Conclusions)
- [Limitations & Future Prospect](#Limitations-&-Future-Prospect)
- [Data Dictionary](#Data-Dictionary)

## Introduction

With its inviting aroma and caffeine content, millions of people around the world start their day off with a cup of joe. More than 2 billion cups of coffee are consumed per day around the globe. Our team has been invited by marketing teams from several coffee brands to investigate the feasibility of continuation of coffee sales. With what seems to be a nonstop global warming and increase in climate variability, the companies seek to confirm the effects of climate change on coffee production in 4 countries that produce the most coffee in the world.

According to the International Coffee Organization, in the last 30 years, growing demand for coffee has led to a 60% increase in production. In addition, high climate variability is said to be the main factor responsible for fluctuations in coffee yield year to year in the world. The leading contribution toward climate variability comes from global warming, and it is expected to result in shifts in location and the way coffee may be produced in the future. Coffee is also the 2nd largest traded commodity in the world and drastic changes to its production and distribution could lead to much larger scale problems around the globe.

There is a continuation of growth in interest in lab grown coffee, led by Finland. They have successfully produced coffee cells in an attempt to eliminate the need for deforestation and lower the water footpring, but is limited to steep funding required to pursue more aggressively.

## Problem Statement

Does climate change impact coffee production and retail price of coffee?

## Software requirements
- 

## Executive Summary

Two logistic regression models are used to predict
- Whether or not the year is before or after 2005
- Whether the price of coffee is above or below the mean price of coffee (1990-2020)

Using features associated with change in temperature, production/harvest levels of a country and more, both models accurately predict each respective target. The hypothesis that as temperature increases retail price of coffee does as well, is proven to be true.

In addition, five linear regression models used.
1. Temperatures from all 4 countries to predict USA retail price
2. Temperatures from all 4 countries to predict production
3. Production from all 4 countries to predict USA retail price
4. Production from Brazil to predict USA retail price
5. Production from Indonesia to predict USA retail price


The first logistic regression model, predicting the year to be before or after 2005, has a training accuracy of 0.869 (87%) and a testing accuracy of 0.875 (88%) Indicative that the model is performing relatively well with no indication of over/under-fitting. Additionally this model has a precision score of 100%. When predicting the year as before 2005 the model did not misclassify any predictions. A recall of 80% demonstrates that of all predictions past the year 2005, the model was correct 80% of the time. This model performs better when predicting years prior to 2006. Earlier years in this data appear to be more consistent in terms of data representation for modeling.

The second logistic regression model, predicting the price to be above or below the mean of the price, has a training accuracy of 0.78 (78%) and a testing accuracy of 0.75 (75%). These scores indicate that the model is slightly overfit however is performing relatively well. This model has a precision score of 100%. When predicting the U.S retail price to fall below the target, the model did not misclassify any predictions. A recall of 83% demonstrates that of all predictions made above the target, the model was correct 83% of the time. This model performs better when predicting the price of coffee to fall below the mean than above it, reinforcing values associated with earlier years in this data are more consistent.

In terms of the linear regression models,Average temperatures from all 4 countries used to predict USA retail price of coffee and production. Temperature does not seem to affect coffee production levels or USA retail price as there was was no correlation for either model.

However production rate did seem to have an affect on USA retail price, as all counties production rates had a training accuracy of 0.443 (44%) and testing accuracy of 0.459 (46%). Although this is not the highest scoring model, there is no overfitting as the test score is slightly higher than the train score. This would give us confidence in using this model for a larger dataset to predict correctly about 45% of the time. If we were to gather more data features to try and improve accuracy, this would be a model we would add to.

As there was no overfitting in the model with production predicting USA retail price, we decided to break that model down into individual countries. Brazil was the highest producing country by almost 100 million lbs (128 million total in 2019). This led us to believe that Brazil would be the best indiviual predictor of USA retail price, as they're the largest contributor. That turned out to not be the case, with Indonesia was the best individual predictor. Brazil had a training score of 0.289 (29%) and testing score of 0.344 (34%) while Indonesia had a training score of 0.353 (35%) and a testing score of  0.534 (53%). This was suprising as Indonesia produced 25 million lbs of coffee in 2019, over 100 million lbs less than Brazil, meaning they contributed far less than Brazil to the world's coffee supply. We looked production levels back to 1990 for both counties to see if Indonesia had been a higher producer in the past. This would possibly explain why Indonesia was a better predictor. This was not the case either as Brazil has always (since 1990) had higher produciton levels.

## Recommendations/Conclusions

We recommend the following to the marketing teams:
    - There seems to be a growing interest in lab grown coffee in Finland. It would be ideal to  allocate more resources into research so that coffee production isn't as reliant on climate as it currently is. 
    - Promote sustainability by offering steeper discounts. Since the 
    - Robusta coffee is more temperature tolerable, but comes with a bitter taste
    
## Limitations/Future Prospect



## Data Dictionary

| Name                           | Type     | Description |                    
|--------------------------------|----------|-------------|
| year                           | int64    | Years from 1990-2019
| b_prod_lbs                     | float64  | Brazil production in lbs
| ind_annual_calcsius_change     | float64  | Annual change in temperature in Indonesia
| ind_avg_temp_celsius           | float64  | Average temperature in Indonesia
| ind_prod_lbs                   | float64  | Indonesia production in lbs
| b_hectares_harvested           | float64  | Area of land where coffee is harvested
| b_hectograms_per_hectare_yield | int64    | Amount of coffee produced per hectare
| b_tonnes_produced              | int64    | Amount of coffee produced in Brazil
| usa_retail_price               | float64  | Retail price of coffee in USD per lb
| b_annual_avg_temp              | float64  | Average temperature in Brazil
| col_production_lbs             | float64  | Columbia production in lbs
| col_annual_celsius_change      | float64  | Change in temperature in Columbia
| global_change_in_celsius       | float64  | Global change in temperature
| e_prod                         | float64  | Ethiopia production in lbs
| e_temp_change                  | float64  | Ethiopia temperature change
| e_export                       | float64  | Ethiopia export
| e_consumption                  | float64  | Ethiopia consumption of coffee
| us_consumption_lbs             | float64  | United States consumption of coffee
| col_avg_temp_celsius           | float64  | Average temperature of Columbia
| b_annual_celsius_change        | float64  | Annual change in temperature in Brazil
| e_avg_temp                     | float64  | Average temperature in Ethiopia

#### notes
- 2 main coffee plants - coffea arabica(~80%), Coffea canephora, known as Robusta coffee (~20%) 
     - arabica tastes better, but robusta has higher caffeine content
http://www.coffeeresearch.org/agriculture/coffeeplant.htm

- Seems like the average temperature across the countries we explored are still in the ideal range of temperature to grow coffee successfully - might want to include in the presentation our prediction on which year the temperature will start to be out of that range using the temp change column

- A warming climate could also exacerbate pests. A 2011 study reported that the coffee berry borer, Hypothenemus hampei, appeared to be thriving under warming conditions.
https://www.climate.gov/news-features/climate-and/climate-coffee

- In the last 30 years, growing demand for coffee has led to a 60% increase in production, according to the International Coffee Organization.

- Continuous exposure to temperatures up to and just over 86°F (30°C) can severely damage coffee plants, stunting growth, yellowing leaves, even spawning stem tumors.
