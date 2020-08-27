# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Model Prediction of Sale Price

### By Alexis Lim, DSI-16

## Executive Summary

When it comes to housing prices, we often have access to extensive past data around housing features and the eventual sale price. Being able to predict future sale prices within a reasonable margin would be incredibly useful to many stakeholders, including housing agents, governing bodies and even residents themselves.

In this project, we process the Ames train and test datasets obtained via the [Kaggle competition](https://www.kaggle.com/c/dsi-us-6-project-2-regression-challenge) hosted by General Assembly to find a robust model based on 25-30 variables for prediction of house sale price. We look at which features affect sale price the most through data cleaning and exploratory data analysis, and build and refine our model using various regression techniques.

## Problem Statement

What features of a house contribute most significantly to its eventual sale price, and with knowledge of these features, how can we predict future sale price?

We approach this question from the POV of a consultancy in Ames, Iowa, who is interested in an algorithm for housing sale prices that can take in the features in the dataset and return a predicted sale price. This model can then be marketed to both governing bodies and housing agents who would be interested in such a tool.


### Contents:
- Train Data Import and Cleaning
- Exploratory Data Analysis
- Model Fit and Testing
- Feature Engineering
- Test Data Processing
- Model Iteration
- Test Data Prediction & Output
- Conclusion & Recommendations


## Data Dictionary [Final Model]
The data documentation for the original dataset can be viewed [here](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt). Below is the data dictionary of variables used in the final model.

|Feature|Variable type|Description|
|:------|:-------|:-----|
|bsmtfin_type_1|Ordinal|Rating of basement finished area|
|garage_finish|Ordinal|Interior finish of the garage|
|fireplaces|Discrete|Number of fireplaces|
|garage_cars|Discrete|Size of garage in car capacity|
|bsmtfin_sf_1|Continuous|Type 1 finished square feet|
|total_sf|Interaction|Combines 1st floor sf, 2nd floor sf and total bsmt sf |
|combined_deck_sf|Interaction|Combines wood deck sf, open porch sf and screen porch sf |
|overall_qual mas_vnr_area|Interaction|Combines overall qual and mas vnr area |
|overall_qual total_bath|Interaction|Combines overall qual and total bath |
|overall_qual total_sf|Interaction|Combines overall qual and total sf |
|exter_qual bsmtfin_type_1|Interaction|Combines exter qual and total sf |
|exter_qual mas_vnr_area|Interaction | Combines exter_qual mas_vnr_area|I
|exter_qual bsmtfin_sf_1|Interaction | Combines exter_qual bsmtfin_sf_1|
|bsmt_qual kitchen_qual|Interaction | Combines bsmt_qual kitchen_qual|
|bsmt_qual total_sf|Interaction | Combines bsmt_qual total_sf|
|kitchen_qual garage_cars|Interaction | Combines kitchen_qual garage_cars|
|kitchen_qual total_sf|Interaction | Combines kitchen_qual total_sf|
|garage_finish garage_qual|Interaction | Combines garage_finish garage_qual|
|garage_qual garage_cars|Interaction | Combines garage_qual garage_cars|
|garage_qual mas_vnr_area|Interaction | Combines garage_qual mas_vnr_area|
|paved_drive mas_vnr_area|Interaction | Combines paved_drive mas_vnr_area|
|totrms_abvgrd mas_vnr_area|Interaction | Combines totrms_abvgrd mas_vnr_area|
|fireplaces lot_area_log|Interaction | Combines fireplaces lot_area_log|
|mas_vnr_area liv_garage_area|Interaction | Combines mas_vnr_area liv_garage_area|
|bsmtfin_sf_1 total_sf|Interaction | Combines bsmtfin_sf_1 total_sf|
|total_bath liv_garage_area|Interaction | Combines total_bath liv_garage_area|
|liv_garage_area total_sf|Interaction | Combines liv_garage_area total_sf|
|total_sf lot_area_log|Interaction | Combines total_sf lot_area_log|
|total_sf combined_deck_sf|Interaction | Combines total_sf combined_deck_sf|
|lot_area_log combined_deck_sf|Interaction | Combines lot_area_log combined_deck_sf|


## Conclusion & Recommendations

We have successfully built a model with a relatively good RMSE based on the training dataset provided, and our examination has indicated that while the top influencing factor appears to be area (total square feet of the house and individual areas), variables across different aspects of the house were also picked out by the model to be significant.

*Recommendations*

Although the model generated was relatively successful, we should also note the following:

- The model is likely to have significant predictive power only within Iowa, Ames given that the city often has a large impact on price and may cause the features to interact in a different way. Hence, the use of the model is limited to one area and perhaps neighboring areas.

- The final model leverages quite a few interaction variables from a dataset that is already extremely comprehensive as it was collected by the Ames Assessor’s Office. It is likely that users looking to predict sale price may not have details on all of the variables in the training dataset, while variables such as overall_qual and overall_cond are subjective. It may be fruitful to explore a simpler model that leverages on more accessible variables (e.g. lot_area, total_sf, basement type) which may give us a higher error, but can be generalised to more use cases.

- While we are able to process null values in the dataset by leveraging on other variables, an ideal scenario would be to reduce the null values at the collection stage. As many of the null values turned out to be Not Applicable or they were supposed to be zero values, there can be more standardisation in the data collection process.

While we see that the model built has limitations, it is also true that the process of putting together the model is informative and a similar process can be conducted for other datasets in other cities or with different variables collected. Our process is as follows:

- Clean and process data
- Exploratory data analysis
- Feature engineering
- Feature selection (by judgement and RFE and lasso techniques)
- Model iteration and optimisation

The last step should be ongoing if there is a stream of new data. Any model will have its limitations, but with the right set of assumptions and understanding of suitable use cases, we're able to predict meaningfully.
