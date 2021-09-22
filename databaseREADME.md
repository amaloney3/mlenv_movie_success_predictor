### Database responsibilities for Database part 2:

Worked with team to finalize two databases with possibility of using a third:
- IMDb movies.csv
- movies_metadata.csv
- awards.csv which we have decided not to use

We are to concentrating on the 'IMDb movies.csv' and 'movies_metadata.csv' as a starting point.
- 'genres' was broken out into separate columns
- 'writers' column was dropped as it correlated to 'director' as we were concerned with over-fitting
- 'actors' column was dropped as it was to unweildy 


For the second database segment:  

1) We loaded the 'IMDb_main.csv' and TMDB_main.csv to postgres using the AWS_main_posgres.ipynb:
- movies that had a year greater than 1969
- movies that were produced in "USA'

2) We joined the IMDb_main and TMDB_main files from postres to joined_tables which was written to postgres:

## Database Results:
- We are ready to start digging into the machine learning.