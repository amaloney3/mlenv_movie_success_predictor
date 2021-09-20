### Database responsibilities for Database part 2:

Worked with team to finalize two databases with possibility of using a third:
- IMDb movies.csv
- movies_metadata.csv
- awards.csv

We decided to concentrate on the 'IMDb movies.csv' and 'movies_metadata.csv' as a starting point.
- 'genres' was broken out into separate columns
- 'writers' column was dropped as it correlated to 'director' as we were concerned with over-fitting
- 'actors' column was dropped as it was to unweildy 


For the database segment, we concentrated on some initial 'ETL' which means: extract, transform and load:  

1) We loaded the 'IMDb movies.csv' and did preprocessing for the following:
- movies that had a year greater than 1989
- movies that were produced in "USA'
- updated column name from 'IMDb_movies_df.rename(columns={'imdb_title_id':'imdb_id'}, inplace=True)' so that I could do merge
with the 'movies_metadata.csv'

2) We then loaded the 'movies_metadata.csv' and did similar processing:
- movies that had a year greater than 1969
- movies that were produced in "US'

## Database Results:
- We have increased the number of records in our dataset by making movies we are looking at greater then 1969 instead of 1989.
- We dropped fields that were too difficult to manipulate due to too difficult data, ie actors and writers.