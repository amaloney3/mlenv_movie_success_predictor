# Can We Forecast Film Success? Cinema and Machine-Learning

## Topic
Everyone loves movies -- or, at least has an opinion about them. And since cinema has recently been reshaped by the rise of streaming and the onset of the COVID-19 pandemic, we've set out anew to understand what makes them work. Using data-wrangling skills in Python, and machine-learning skills from packages such as scikit-learn, we plan to answer: What makes movies successful? And how should success be defined?

## Data
We plan to use multiple datasets to aid our inquiry, from sources such as The International Movie Database (IMDb) and The Movies Database (TMDB). The former has compiled data on movie plots, critic and user reviews and ratings, and awards; the latter includes variables such as cast and crew, budgets and box office returns. Additional data, from from sources such as Kaggle, will also be included.

## Communication Protocols
Each member of the team is accessible via Slack, both individually and via a group channel named "the_clever_crew." We've stayed in relatively frequent touch in and out of class, and have planned video calls outside of class.

## Team members and roles for Segment 1:
* Maggie Allen - Presentation
* Andrew Malony - GitHub
* Kathy Morrissey - Machine Learning Model
* Rose Baumann - Database

## Overview of Machine Learning and Movie Analysis 

### My role as Database responsible for provisional Database:

I worked with my team to research and find three databases
- IMDb movies.csv
- movies_metadata.csv
- awards.csv

We decided to concentrate on the 'IMDb movies.csv' and 'movies_metadata.csv' as a starting point.

The role of being responsible for the Database, I concentrated on trying some initial 'ETL' which means: extract, transform and load:  

1) I loaded the 'IMDb movies.csv' and did preprocessing for the following:
- movies that had a year greater than 1989
- movies that were produced in "USA'
- updated column name from 'IMDb_movies_df.rename(columns={'imdb_title_id':'imdb_id'}, inplace=True)' so that I could do merge
with the 'movies_metadata.csv'

2) I then loaded the 'movies_metadata.csv' and did similar processing:
- movies that had a year greater than 1989
- movies that were produced in "US'

## Database Results:
The dataset is smaller than expected, so may look at using movies from 1970 and greater and also including movies from UK and India rather than just US based movies.

## Data Model

Objective: Predict whether or not a movie will be successful. Success can be measured in various ways, such as: profit = revenue - budget, voter ratings, and awards won. As we learn more about the quality and characteristics of the input and output variables we will refine these metics.

We will build a deep learning model, but our first pass will be a simple neural network with one hidden layer. The output variable will be based on the probability of (average voter rating > 5). (Ratings are on a scale of 0-10) Probability greater than 50% is considered a successful movie.

Although the dataset will ultimately be a mashup of three datasets, our initial demonstration of the model will use data from one source input as a csv file. This will be replaced later by a cloud-based database, but this does not impact the model demonstration.

To support the incremental use of additional hidden layers, and allow visualization with tensorflow, we use the Keras sequential model with one hidden layer containing 10 nodes. The ReLU activation function will be used in the expectation there are nonlinear relationships in the data. The output layer will use the sigmoid activation function and one neuron to produce a probability.

The dataset comes from the The Movies Database in Kaggle. It has been filtered to movies produced in the US and released after 1989. The years 2018 forward are sparse. There are 12,906 movies.

The features dataset contains 7 variables:
* movie runtime in minutes, numeric
* release year, numeric
* movie has a website
* movies does not have a website
* movie is part of a collection
* movie is not part of a collection

This model was trained and tested. After 50 epochs, the model produced loss=54% and accuracy=74%
