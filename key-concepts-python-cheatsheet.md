# Key Concepts: Predictions with Python

Here is a summary of today's learnings 📚

**Machine Learning**

The domain of Data Science that deals with a computer's or program's ability to learn patterns and formula without explicitly being programmed.

Machine Learning includes a lot of programming tools and techniques that allow a program to look at massive amounts of existing data and find correlations and patterns that can be used to make predictions or gather insights, that a human eye might normally miss.

**Time Series**

When we talk about predictions or forecasting using computers, we talk about the domain of Time Series - the domain of data analytics and data science dealing with data that is occuring at even time intervals - monthly, daily, hourly, etc.

`fbprophet` Python Package

Because of Python's huge community, there are many Python packages that help us work with data much easier. You've already seen `pandas` for reading data from different files, `seaborn` for data visualization and, of course `fbprophet` that is designed specifically for working with Time Series data.

**Modelling steps**

1. Creating the model

We first create an empty Prophet model, by using `Prophet()`. At this point this is just an empty "shell" ready to look at data and learn it's patterns.

2. Training the model

We then train (or `fit`) the model, by giving it existing historical data (like car sales or stock prices) to look at and identify patterns and a formula that can be used for future predictions.

3. Predicting

After the model has learned, we can generate a `DataFrame` of future dates using `make_future_dataframe()` method given to us the Prophet package, which can be any number of days or months into the future. We can then run `model.predict(new_dates)` to get a predicted value - also called `target` - for these future dates.

**In-sample Prediction**

Using the `model` to predict on already existing dates. This is usually the first step, as this allows us to quickly test models performance. If what the model predicts - `yhat` - is similar to the actual values for those dates - `y` - we can continue with this model to predict the future!

**Out-of-sample Prediction**

Using the `model` to predict on unseen dates. This is the real prediction of totally new values, where we we look at dates that do not exist in our original data.

**Evaluating the model**

We can't just do a few predictions and take them for granted. One good way to evaluate the model is to do cross-validation - a technique that allows us to split our Time Series data into periods and run `model.predict()` multiple times across these different time periods. After we get many (20+) combinations of predictions, we can start looking at some performance metrics.

The metric we saw today was Mean Absolute Error. `Mean` means average, and absolute means that we don't care if the number is positive or negative, we look only at the distance (the error) that it is off from the real number. Because the mean of `100 and -100` is 0, but the mean absolute of `100 and -100` is 100. And if, for example, our stock prediction is constantly wrong by either +10USD or -10USD, our average error is 10, not 0.

Good luck on your learning journey! Hope to see you again! 🙌