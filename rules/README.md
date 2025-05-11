Homework 1:  Rules

In this homework you will build rules to predict the movement of stock.  You are given data for a particular stock.
The data spans 200 consecutive market days.  On each day, you are given the opening price for the stock, the high price
for the stock, the low price for the stock, the closing price for the stock, the volume (number) of shares traded on that day,
whether dividends were announced and how much, whether a stock split was announced, 
and a series of features: EMA_08, EMA_12, EMA_20,  RSI_05, RSI_09, and RSI_14.
(What these features are exactly are not important for now).

From these data, you must predict if the *OPENING PRICE OF THE NEXT DAY WILL BE GREATER THAN THE CLOSING PRICE OF THE CURRENT DAY*.

The data are provided in the form of two files:

"Training200.csv"
and
"Validation65.csv".

Training200.csv consists of the data for 200 consecutive days and comprises your training data.
Validation65.csv consists of data for the next 65 days and comprises your validation data.

Note that the csv files don't actually directly give you the value of the variable to predict (namely whether the opening stock
value of the next day will be greater than the current day's closing value).  This must be inferred from the file.  Since the
training data only includes 200 lines, you will not be able to determine this for the 200th day.  The true answer for the 200th
day is "YES" (i.e. the price did go up).

You must use the training data to build rules and optimize/test them on the validation data.

You must submit the following:
a) A file with the rules
b) A python program that reads in your rules and also accepts a csv file just like Validation65.csv and outputs
predictions for each line of the file.
c) A brief writeup describing your solution.

We have retained a third file -- a test file -- that we have not released with this set.  We will test the accuracy of your 
code on this file. You will be graded on the accuracy you get on this file, and your writeup.

Please write your own code.  You may only assume that scipy, numpy and pandas are available. These packages should be sufficient
for this problem.