# Final Project: Machine Learning and Movie Analysis 
### 20 Part One; My role as 'Database'

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


## Results:
The dataset is smaller than expected, so may look at using movies from 1970 and greater and also including movies from UK and India rather than just US based movies.

