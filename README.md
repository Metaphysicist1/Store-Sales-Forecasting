# Project Solution

## Overview

This project aims to predict sales for various product families sold at Favorita stores in Ecuador. By leveraging historical sales data and additional contextual information, we develop a predictive model to forecast future sales accurately. The solution involves analyzing time-series data, incorporating external factors such as promotions, holidays, and economic indicators to enhance prediction accuracy.

[Kaggle Competition Page](https://www.kaggle.com/competitions/store-sales-time-series-forecasting/data?select=holidays_events.csv)

## File Descriptions and Data Field Information

### train.csv
The training data, comprising time series of features `store_nbr`, `family`, and `onpromotion` as well as the target `sales`.
- `store_nbr`: Identifies the store at which the products are sold.
- `family`: Identifies the type of product sold.
- `sales`: Gives the total sales for a product family at a particular store at a given date. Fractional values are possible since products can be sold in fractional units (e.g., 1.5 kg of cheese, as opposed to 1 bag of chips).
- `onpromotion`: Gives the total number of items in a product family that were being promoted at a store at a given date.

### test.csv
The test data, having the same features as the training data. You will predict the target `sales` for the dates in this file.
- The dates in the test data are for the 15 days after the last date in the training data.

### sample_submission.csv
A sample submission file in the correct format.

### stores.csv
Store metadata, including city, state, type, and cluster.
- `cluster`: A grouping of similar stores.

### oil.csv
Daily oil price. Includes values during both the train and test data timeframes. (Ecuador is an oil-dependent country and its economic health is highly vulnerable to shocks in oil prices.)

### holidays_events.csv
Holidays and Events, with metadata.
- **NOTE**: Pay special attention to the `transferred` column. A holiday that is transferred officially falls on that calendar day but was moved to another date by the government. A transferred day is more like a normal day than a holiday. To find the day that it was actually celebrated, look for the corresponding row where `type` is `Transfer`. For example, the holiday "Independencia de Guayaquil" was transferred from 2012-10-09 to 2012-10-12, which means it was celebrated on 2012-10-12. Days that are `type Bridge` are extra days that are added to a holiday (e.g., to extend the break across a long weekend). These are frequently made up by the `type Work Day`, which is a day not normally scheduled for work (e.g., Saturday) that is meant to pay back the Bridge.

## Additional Notes
- Wages in the public sector are paid every two weeks on the 15th and on the last day of the month. Supermarket sales could be affected by this.
- A magnitude 7.8 earthquake struck Ecuador on April 16, 2016. People rallied in relief efforts donating water and other first-need products, which greatly affected supermarket sales for several weeks after the earthquake.
