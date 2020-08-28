# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 2: Model Prediction of Sale Price

### By Alexis Lim, DSI-16

## Executive Summary

When it comes to housing prices, we often have access to extensive past data around housing features and the eventual sale price. Being able to predict future sale prices within a reasonable margin would be incredibly useful to many stakeholders, including housing agents, governing bodies and even residents themselves.

In this project, we process the Ames train and test datasets obtained via the [Kaggle competition](https://www.kaggle.com/c/dsi-us-6-project-2-regression-challenge) hosted by General Assembly to find a robust model based on 25-30 variables for prediction of house sale price. We look at which features affect sale price the most through data cleaning and exploratory data analysis, and build and refine our model using various regression techniques.

## Problem Statement

What features of a house contribute most significantly to its eventual sale price, and with knowledge of these features, how can we predict future sale price? Can the model that we build be generalised to other cities, states and countries?

We approach the problem statement from the POV of a team of housing agents in Ames, Iowa, as it’s likely that agents will have access to this level of detail about a property. Having a model will help agents to consistently valuate properties and negotiate better between buyers and sellers. If successful, this model could also then be marketed to both governing bodies and housing agents who would be interested in such a tool.


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

### Recommendations

If we had additional time and resources, we may want to consider the following to improve on and continually iterate on our model:

- The frequency distribution of the log of sale prices follows a normal distribution. By building our linear regression model with the log of sale prices, we can better fit and predict the sale prices of houses in the higher price range.

- For features with many different categories, we can combine and regroup them so that each category becomes more significant. For eg: Neighborhood has 28 categories, we can regroup them into 5 categories based on their mean sale prices.

- We can also look into other external factors affecting housing prices like economic factors and demographic data of the community.

While we see that the model built has limitations, it is also true that the process of putting together the model is informative and a similar process can be conducted for other datasets in other cities or with different variables collected. Our process is as follows:

- Clean and process data
- Exploratory data analysis
- Feature engineering
- Feature selection (by judgement and RFE and lasso techniques)
- Model iteration and optimisation

The last step should be ongoing if there is a stream of new data. Any model will have its limitations, but with the right set of assumptions and understanding of suitable use cases, we're able to predict meaningfully.
