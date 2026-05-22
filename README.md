# Bike-Sales-Time-Series-Project-
a project looking at the bike sales of a company for sales on bikes and bike parts in different parts of the world.

This project was part of a Bootcamp exercise looking at training models in time series data. I downloaded the dataset from Kaggle on this link: https://www.kaggle.com/datasets/sadiqshah/bike-sales-in-europe?resource=download
The dataset contains bike sales in European countries and each state of their countries.

This dataset has 18 columns (main column is sales). The columns have the value bale and meaningful insight from it sales according to the gender of each client and the number of each product and its sales and so on. This dataset is very interesting in the various insights that can be drawn from it. The data covers sales from 2011 t0 2016.

In this time series project, I wanted to see how the various models would perform in this dataset. These models include; ARIMA, Facebook Prophet, and Machine Learning models (specifically Linear Regression, Random Forest Regression, and XGBoost).

I first cleaned and wrangled the data to prepare the dataset for ARIMA forecasting. This involved trimming the dataset down to the date column and the target variable, Order Quantity. I was interested in looking at how the sales have been doing over the years. I also trimmed the data to only cover 2013 to 2016. I did this because, from the graph plot, it seemed like there was a brand or strategy change in 2013 that created a trend in the sales.

I also changed the new dataframe into a series, split the training and testing sets and ran the dataset through a baseline ARIMA model. The performance seemed lacking and tuned the p, d, q parameters. There was no significant change in performance. The model seems to mostly note the direction of the trend, but not following it particularly. The confidence interval is too wide. I also tried to run a one-day-at-a-time forecast, but the code ran for too long (I commented out the code for future analysis)

Looking at the Facebook Prophet, we can easily see the trends in the years, months and weeks. From these visualizations, we can see that the yearly trend shows a rise, a fall, and another rise beginning in 2015. If the trend stays true, we expect the sales to peek in 2016 and then fall again towards 2017. We can also see a rising and falling trend in the monthly sales, with the peek at August, when most sales are made. The lowest sales are in February. There does also seem to be a weekly trend, with most of the positive trend happening in most weekdays except Friday, and a negative trend in the weekend.

The Facebook Prophet models performance was however worse compared to the ARIMA models.

The next step was looking into how the Machine Learning models would perform. I started off preparing a dataframe from the series. This allowed the addition of columns needed to create lag features and rolling mean features to the dataset. This exercise creates the Machine Learning analog of AR terms.

After hot encoding the 'day' and 'month' columns so that the values are treated as categorical variables by the machine learning models, next was splitting the data into training and testing sets, and instantilizing Linear Regression. I then fit the training set into the model and looked at the Mean Absolute Error of the test set. I repeated the process with Random Forest and XGBoost.

On comparing the Mean Absolute Error of each model, the linear regression model had the best performance with a score of 7.36(truncated). Tuning the models can yeild even better results especially for Random Forest and XGBoost. 
