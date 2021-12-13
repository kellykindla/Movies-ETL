# Movie- ETL 
## Module 8 

## Purpose of Module 8
The goal of this module was to use Python and Pandas to perform data wrangling by creating an ETL pipeline that transforms data and stores it in a SQL database. We were introduced to regular expressions and utilized them to parse data. We were further introduced to the ETL process and from this module, can extract data from multiple sources with Python, clean data with Pandas, and load data with SQL.   

## Overview of Assignment 
For this assignment, we were working with Amazing Prime to extract and transform movie rating data and save it to a SQL database so it can be utilized by the company for a hackathon.  In this assignment, we refactored our extracted data from Wikipedia and Kaggle and converted the data sets to DataFrames through the use of functions. We then filtered the “wiki_movies” DataFrame to contain the necessary columns with sufficient information and proper data types. We followed a similar cleaning process on the metadata and ratings DataFrames, ensuring they contained necessary information and proper datatypes for each column. With clean data, we initially merged the Wikipedia and metadata DataFrames on the IMDb ID, which was extracted using regular expressions, into “movies_df”. After creating this merged DataFrame, we compared repetitive columns between the Wikipedia data and that from Kaggle. We further cleaned the DataFrame by deleting those redunant columns,  replacing any null values with information from the other data set, and further removing any unncessary columns. We then performed another merge of DataFrames by joining the “movies_df” and ratings data on “kaggle_id” to create our final DataFrame, “movies_with_ratings_df”. This DataFrame was further cleaned by replacing any missing values in each column with zeros. With complete DataFrames, we were able to create a connection string so our database engine can connect to a database and the two DataFrames could be exported to a SQL table. Due to a large ratings file, we printed the elapsed time for the importing to occur. The end result was two tables, “movies” and “ratings” in the “movie_data” database created in SQL which can be used by the company in the hackathon. 

## Resources 
#### Data:
	- Wikipedia 
		- wikipedia-movies.json
	- GroupLens/ MovieLens/Kaggle 
		- ratings.csv
		- movies_metadata.csv

#### Software used: 
	- pgAdmin 4 Version 6.1 
	- PostgreSQL 11.14 Version 6.0
	- Python 3.7.10
	- Anoconda 4.10.1
	- Jupyter Notebook 6.3.0

## Results: 
The following are screenshots of the DataFrames created throughout the assignment. 

#### wiki_movies_df: 
The cleaned wikipedia DataFrame. 

<img width="671" alt="wiki_movies_df" src="https://user-images.githubusercontent.com/92558842/145770280-4110204c-2427-4f52-9bb4-986fb6f050e3.png">


#### movies_df:
The cleaned, merged DataFrame between “wiki_movies_df” and “kaggle_metadata” on “imdb_id”.

<img width="671" alt="movies_df" src="https://user-images.githubusercontent.com/92558842/145770289-ea161d26-4499-4323-9f3c-e449d7e32e40.png">


#### movies_with_ratings: 
The cleaned, merged DataFrame between “movies_df” and “ratings_counts” on “kaggle_id”.

<img width="671" alt="movies_with_ratings_df" src="https://user-images.githubusercontent.com/92558842/145770321-609fb0b7-a12b-4b1e-abd3-94f6560f5168.png">

#### SQL:
The following are screenshots of the SQL queries for the row counts for each table created. 

<img width="433" alt="movies_query" src="https://user-images.githubusercontent.com/92558842/145770433-b1e9e351-6e90-4a17-ba6a-a350e6475cad.png">
<img width="451" alt="ratings_query" src="https://user-images.githubusercontent.com/92558842/145770446-6a44c717-9f3e-4380-b885-7cac4d0a2ce5.png">

