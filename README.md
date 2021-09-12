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

### Machine Learning provisional output

* Initial output from the machine learning:
Please referene : model_draft_1.ipynb

## Results:
The dataset is smaller than expected, so may look at using movies from 1970 and greater and also including movies from UK and India rather than just US based movies.
