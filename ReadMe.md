# Can We Forecast Film Success? Cinema and Machine-Learning

## Topic
Everyone loves movies -- or, at least has an opinion about them. And since cinema has recently been reshaped by the rise of streaming and the onset of the COVID-19 pandemic, we've set out anew to understand what makes them work. Using data-wrangling skills in Python, and machine-learning skills from packages such as scikit-learn, we plan to answer: What makes movies successful? And how should success be defined?

## Data
We plan to use multiple datasets to aid our inquiry, from sources such as The International Movie Database (IMDb) and The Movies Database (TMDB). The former has compiled data on movie plots, critic and user reviews and ratings, and awards; the latter includes variables such as cast and crew, budgets and box office returns. Additional data, from sources such as Kaggle, will also be included.

## Communication Protocols
Each member of the team is accessible via Slack, both individually and via a group channel named "the_clever_crew." We've stayed in relatively frequent touch in and out of class, and have planned video calls outside of class.

## Team members and roles for Segment 1
* Maggie Allen - Presentation
* Andrew Malony - GitHub
* Kathy Morrissey - Machine Learning Model
* Rose Baumann - Database

## Overview of Machine Learning and Movie Analysis 

### Database responsibilities for provisional Database

Worked with team to research and find three databases
- IMDb movies.csv
- movies_metadata.csv
- awards.csv

We decided to concentrate on the 'IMDb movies.csv' and 'movies_metadata.csv' as a starting point.

For the database segment, we concentrated on some initial 'ETL' which means: extract, transform and load:  

1) We loaded the 'IMDb movies.csv' and did preprocessing for the following:
- movies that had a year greater than 1989
- movies that were produced in "USA'
- updated column name from 'IMDb_movies_df.rename(columns={'imdb_title_id':'imdb_id'}, inplace=True)' so that we could do merge
with the 'movies_metadata.csv'

2) We then loaded the 'movies_metadata.csv' and did similar processing:
- movies that had a year greater than 1989
- movies that were produced in "US'

## Database Results
The dataset is smaller than expected, so we may look at using movies from 1970 and greater and also including movies from UK and India rather than just US based movies.

## Data Model

Objective: Predict whether or not a movie will be successful. Success can be measured in various ways, such as: profit = revenue - budget, voter ratings, and awards won. As we learn more about the quality and characteristics of the input and output variables we will refine these metrics.

We will build a deep learning model, but our first pass will be a simple neural network with one hidden layer. The output variable will be based on the probability of (average voter rating > 5). (Ratings are on a scale of 0-10) Probability greater than 50% is considered a successful movie.

Although the dataset will ultimately be a mashup of three datasets, our initial demonstration of the model will use data from one source input as a csv file. This will be replaced later by a cloud-based database, but this does not impact the model demonstration.

To support the incremental use of additional hidden layers, and allow visualization with tensorflow, we use the Keras sequential model with one hidden layer containing 10 nodes. The ReLU activation function will be used in the expectation there are nonlinear relationships in the data. The output layer will use the sigmoid activation function and one neuron to produce a probability.

The dataset comes from The Movies Database in Kaggle. It has been filtered to movies produced in the US and released after 1989. The years 2018 forward are sparse. There are 12,906 movies.

The features dataset contains 7 variables:
* movie runtime in minutes, numeric
* release year, numeric
* movie has a website
* movies does not have a website
* movie is part of a collection
* movie is not part of a collection

This model was trained and tested. After 50 epochs, the model produced loss=54% and accuracy=74%

## Team members and roles for Segment 2
* Maggie Allen - Presentation/GitHub
* Andrew Malony - Presentation/Exploratory Data Analysis
* Kathy Morrissey - Data Cleaning/Analysis/Machine Learning
* Rose Baumann - Database

## Clean-up And Exploratory Data Analysis
We determined the most useful datasets for our prediction model will come from the International Movie Database (IMDb) and The Movies Database (TMDB). As indicated earlier, the filenames are 'IMDb movies.csv' and 'movies_metadata.csv.' A separate dataset containing information about film awards was deemed impractical for this project, but potentially ripe for further analysis down the road. 

Both datasets contained missing values, mismatched datatypes and other challenges for our analysis, with clean-up detailed in several Jupyter notebooks. But the datasets were successfully merged and contain more than 70,000 observations.

## Database
For the database segment, we updated our preprocessing steps on the 'IMDb movies.csv' file by:
- including movies that had a year greater than 1969
- movies that were produced in "USA'
- updated column name from 'IMDb_movies_df.rename(columns={'imdb_title_id':'imdb_id'}, inplace=True)' so that we could do a merge
with the 'tmdb_main.csv'

2) We pivoted from using Google Colab to using Jupyter notebooks to 'talk to AWS.'

## Database Results
- We have increased the number of records in our dataset by making movies we are looking at greater then 1969 instead of 1989.
- We dropped fields that were difficult to manipulate and not clearly beneficial for a prediction model, such as certain actors and writers.

## Stakeholder Update
We imagine multiple stakeholders will be interested in our movie predictions, but their definitions of "movie success" could vary. From Hollywood studio executives to Big Tech streaming companies and the moviegoing public more generally. While we haven't finalized our conclusions, we can say we've tackled arguably the most difficult part of any data science project -- choosing the data, and cleaning and analyzing it to prepare for the prediction stage.

## Presentation Blueprint
Our final presentation blueprint is a first draft at our final presentation with the format and style of the presentation determined. Also, the overall flow has been defined, starting with introduction to our topic and the reason we selected it, followed by a listing of the team members and roles, an explanation of the question(s) we are looking to answer, and an introduction to fictional stakeholders who would benefit from our good work. 

For the time being, our presentation has the beginnings of our story regarding the data clean-up effort involved in this work. Unfortunately, our dataset required far more effort to prepare it for use in further data analysis and thus, we have not yet identified many of our analysis conclusions. However, we have started a dashboard blueprint to help tell the story of the clean-up involved and how we were able to extract, transform and prepare the data for loading into the database. 

Our next steps for the presentation will be to continue to develop the visuals and add our conclusions in parallel with the creation of an interactive dashboard. Currently, the presentation is in Google Slides format, which does not readily reside on GitHub as it is web based. It had quite a few iterations in Google Slides before I was able to add some PDF exports to GitHub until I finally discovered the ability to download as a PowerPoint that could be loaded to my Presentation_MA repository. 

## Dashboard Blueprint
We created the blueprint draft of our interactive dashboard. Using the Pandas "ProfileReport" package, we were able to better grasp the data, highlight several charts and place them throughout our dashboard. We called out which of these are good candidates for creating Tableau interactive graphs and have prepared our blueprint in Google Slides format so that we can determine how to best transition in the upcoming segment to a Tableau version.

We also mocked up multiple Tableau graphics, including a visualization of User Movie Reviews and IMDb Metascore by year.
