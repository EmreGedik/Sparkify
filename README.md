# Capstone Project: Sparkify


### Medium Blog Post
Here is the Medium blog post I have written regarding the project:https://medium.com/@emrebilgehangedik/sparkify-project-bb136e94b678


### Project Motivation
The project focuses on churn problem of companies. Churn happens when a customer cancels his/her membership, or sometimes downgrades his/her services. Churn basically decreases a company's number of subscribed users so has a negative effect in terms of profit. Companies try to detect the customers who have a potential to churn and give additional offers to these customers. This is why it is important to have a precise model for detecting churn. In the project I define churn, extract features from the dataset and train some alternative classification models.

In the data exploration process I also try to answer the following questions:
“Who are the most popular artists and what are the most popular songs in the dataset?”
"In which hours in a day, the most number of songs are listened to?"


### Libraries
I use Python3. Here are the libraries I used in my Jupyter Notebook:
1. pyspark.sql
2. seaborn
3. matplotlib.pyplot
4. datetime


### Summary of The Analysis
At the beginning of the project, I read the dataset into a Spark dataframe. Before making any exploratory analysis, I checked the structure of the the dataframe. I found the number of rows, number of columns and the column names. Here I started the “Data Cleaning” part. I had to check if there were any missing values in any part of the dataset. Since this is a churn problem that I am expected to model, I had to mark the users that churned. Because of this, I removed the rows that had missing values in userId column.
When I check the dataset, I found that there are 225 users in the dataset in total. There are 52 users who had “Cancellation Confirmation” and 154 users who has “Downgrade”. I did not prefer to add “Downgrade” users to Churn because then the majority of users would be flagged as Churn user. That is why I considered Churn as the users who has “Cancellation Confirmation” in the dataset.

After “Data Cleaning” part, I started to look deeper into the dataset and tried to understand the details of the dataset. This is the “Exploratory Data Analysis” part. Here I focused on answering some questions like the gender distribution of churn users, number of songs listened to by churn and no-churn users etc. But the main point here was to find some features that might be used for the churn model.

After “Exploratory Data Analysis” part, I started the “Feature Engineering” part. Here I found the “page” column was very helpful, as this column was giving information about the actions of the user while using the Sparkify service. For a churn model, I think it is important to understand the actions and behavior of different users. I also extracted some information about the gender, the level (free or paid subscription) and the duration of membership of each user. After finding the features I would like to use, I vectorized and scaled the features, I also extracted the churn label. (The users who had “Cancellation Confirmation” in the dataset.)

Finally I used four different classification algorithms for churn model:

⦁ Random Forest Classification
⦁ Logistic Classification
⦁ Gradient-Boosted Tree Classification
⦁ Linear SVC Classification

The worst model (Linear SVC Classification) had an f1-score around 55 percent. But other three models have better performances and the highest performance is from logistic classification and random forest classification with an f1-score of around 76 percent.


### File Descriptions
1. sparkify.ipynb
This Jupyter Notebook file contains the Python code that loads the dataset, cleans the data, make explatory analysis. The notebook also contains feature extraction process and training different models with classification algorithms.


### Acknowledgement and References
The project and dataset belong to Udacity.
