### Database responsibilities for provisional Database:

Worked with team to research and find three databases
- IMDb movies.csv
- movies_metadata.csv
- awards.csv

We decided to concentrate on the 'IMDb movies.csv' and 'movies_metadata.csv' as a starting point.
- genres was broken out into separate columns
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
The dataset is smaller than expected, so we may look at using movies from 1970 and greater and also including movies from UK and India rather than just US based movies.
