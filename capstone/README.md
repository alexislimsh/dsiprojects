# DSI Capstone

### By Alexis Lim, DSI-16

# Executive Summary

This project folder contains my capstone project for the General Assembly DSI-16 course. It leverages an e-commerce dataset provided by the Brazilian company Olist, available on [Kaggle](https://www.kaggle.com/olistbr/brazilian-ecommerce).

The focus of the project was to build a sales prediction model for Olist sellers. We also perform NLP on the reviews in Portuguese to determine dominant topics in reviews.

The project is split up into two notebooks as follows:

**Project Notebooks**
- Notebook 1: Cleaning and EDA
- Notebook 2: Sales Estimate Prediction & Topic Modeling

# Background

We are a team of data scientists at Olist, an online e-commerce company that connects small businesses from all over Brazil to large online e-commerce marketplaces such as [Mercado Livre](https://www.mercadolivre.com.br/) and [Americanas](https://www.americanas.com.br/).

By listing their products on Olist Store, small business owners are able to sell their products to customers on these marketplaces without the prohibitive costs of maintaining a vendor presence there.

We have been given access to a number of datasets that include the following:

- Olist Orders: A sample of 100K orders across 2016 and 2018
- Order Items: Individual items purchased within each order (customer id, product id and order id may be duplicated)
- Order Payments: Payments by order, including payment type and number of instalments
- Products: Products dataset with product ID and category
- Translation: English translation for product category name
- Geolocation: Location of customers
- Reviews: Reviews submitted by order id
- Sellers: Unique seller ids and seller details

For this assignment, we want to focus on how we can use the data to increase the number of sellers and provide recommendations to them. Having a wide variety of sellers is incredibly important to us at Olist, and we are always looking for new ways to get new leads and onboard sellers onto our platform.

# Problem Statement
Based on the data we've gathered from the sales and reviews on the platform, we have been tasked to estimate the sales that a seller can get based on factors such as their product category, average product price and location.

Additionally, we also want to take a look at the reviews to give potential sellers advice on how to increase customer satisfaction.

Our guiding questions are:
- How much can a seller expect to earn on the platform?
- What steps can a seller take to increase their sales?
- What are the prominent topics that feature in our customer reviews?

# Data Dictionary

The final data leveraged by the sales estimator model included:

|Feature|Datatype|Description|
|-------|--------|-----------|
|most_common_cat|String|Dominant product category of the seller (one-hot encoded in final model)|
|number_of_product_categories|Int|Number of product categories|
|num_products_stock|Int|Number of unique products in stock|
|average_product_price|Float|Average price of product|
|average_products_per_month|Float|Average products per month|
|state|String|State of the seller (one-hot encoded in final model)|
|min_price|float|Minimum product price
|max_price|float|Maximum product price|

# Conclusion and Insights

We were able to build a predictive model for predicting seller performance with around R$200 of root mean squared error and an adjusted R2 score of 0.93. However, as the data is not completely comprehensive, the model will require additional training on more data to be sufficiently robust and to evaluate its reproducibility.

The model predicts seller performances by taking in the following information:

- Product Category
- State
- Min, Max, Average Product Price
- Number of Products they can sell in a month
- Number of Unique Products

Average products they can sell in a month turned out to be the most predictive factor, along with the minimum, maximum and average product prices. With more data and potentially more inputs from the seller like the size of their company, length of seller relationship to Olist, we may want to also try predicting optimal product volume that can be sold instead, in the long run.
