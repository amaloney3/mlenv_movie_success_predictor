# Machine Learning Model Segment 2

## Preliminary Data Processing

Three datasets were found in Kaggle and reviewed for viability:

1 - source: IMDb Movies Extensive Dataset

    https://www.kaggle.com/stefanoleone992/imdb-extensive-dataset

    file: https://www.kaggle.com/stefanoleone992/imdb-extensive-dataset/download

    Contains metadata scraped from IMDB movies with at least 100 votes as of 1/1/2020

2 - The Movies Dataset

    source: https://www.kaggle.com/rounakbanik/the-movies-dataset?select=movies_metadata.csv

    file: https://www.kaggle.com/rounakbanik/the-movies-dataset/download

    Contains metadata from the Full MovieLens Dataset for movies released on or before July 2017.

3 - Film Awards (IMDB)

    source: https://www.kaggle.com/iwooloowi/film-awards-imdb

    Last updated 3/25/2020

The datasets are not well-documented so an extensive data analysis and cleaning process evaluated each variable to determine it's contents and viability as a data element in the model. Where data was available from two sources for comparison, additional validation established their similiarity and differences. Data elements were spot-checked against the source websites to ensure data was correctly captured and interpreted.

Some common issues in cleaning the data had to be overcome, including:
* Strings of data that appeared to be in json format were not and had to be processed through string evaluation to extract the contents
* Mixed data types within a data element that had to be identified and properly converted to the same data type
* Currency abbreviations attached to numbers that casued the inferred data types to be rendered as strings 
* Raw data scraped from websites is generally prone to inconsistency in data structures, inconsistency in data encoding and data entry errors. This variability in data elements places great importance on discerning the actual meaning of values, matching strings to identify dictinct categories, and devising appropriate transformations for use in machine learning models

The datasets were cleaned separately to handle their specific data issues and then merged on IMDB ID number for comparisons and creation of the final input dataset.

Although machine learning models can handle some "messy" data, cleaning and standardizing data in an appropriate fashion before inputting to the model development should result in a model that requires less training and tuning

## Preliminary feature engineering and preliminary feature selection, including decision-making process

Preliminary feature engineering and selection focused on identifying cleanliness and presence of data elements, as well as the ability to transform the data element into a meaningful and useful model variable. As a group, the team reviewed the data elements and made decisions on individual variables. Some variables were discarded due to the difficulty and time required to process. For example, there are over 19,000 production companies, and some movies had 10 or more production companies involved. Similarly, the number of countries in production and the number of actors for each movie produce an overwhelming number of possible combinations. Other variables were discarded due to the the high number of missing values and inability to impute missing values. 

In comparing the IMDB and the TMDB meta data it became clear the two datasets agreed very well in their contents, but the IMDB data was more current, containing many more movies. As a result, IMDB data is the main source, supplemented as possible by TMDB data. Model evaluation will determine whether the resulting missing values can be used. 

The awards dataset contained over 2 million records covering more than 16,000 different awards for the years 1970 to 2020. Again, the time and effort required to clean and transform the data made this dataset unuseable in the project time frame.

Source code for cleaning datasets:

IMDB data:
* notebook: IMDB_database_cleanup.ipynb
* output file: imdb_main.csv

TMDB data:
* notebook: TMDB_database_cleanup.ipynb
* output file: tmdb_main.csv

Awards data:
* notebook: Merging_IMDB_Awards
* file: N/A

Merged IMDB and TMDB:
* notebook: Merging_IMDB_Awards
* output file: merged_movies.csv

## How data was split for training and testing sets

Train, test amd validation datasets were created. Stratified sampling waas done to ensure representativeness of success outcome in all samples. Valdation dataset was set at 30% of the sample and used in loss and accuracy graphs to aid in assessing model fit.

## Explanation of model choice, including limitations and benefits

Objective: Predict whether or not a movie will be successful. 

The possible metrics of success identified apriori included : profit = revenue - budget, voter ratings, and awards won. As we learned more about the input datasets, we found budget and revenue numbers were sparsely populated, rendering them unusable as the predicted value. Awards data, though available, was too unwieldy to be of use in our timeframe. Thus, ratings data elements are currently the only viable option.

The dataset contains various rating variables:
* vote average  - this is not an unweighted average across all IMDB users. This is a weighted average based on an undisclosed IMDB propietary algorithm. Scores range from 1 to 10.
* number of votes from IMDB users
* number of reviews from critics
* numner of reviews from IMDB users

The final measure of success will be determined as the model undergoes development. As a placeholder, this current model uses IMDB score >= 7 to define success. The IMDB score ranges between 1 and 10.

The current model has two hidden layers utilizing the tanh activation function. Tanh is a better fit to the zero-centered scaled data than relu, because tanh accommodates negative values. The output variable will be based on the probability of (IMDB score >= 7), so the output layer has one node with a sigmoid activation function.

This week will focus on improving the features data and tuning this model. Additionally, other models such as a random forest classification model will be exploed and compared.

notebook: Machine_Learning_Model_Segment_2.ipynb

