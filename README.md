# Sparkify Database ETL Process

## Purpose of the Database
The purpose of this database is to store the unstructured information, generated by the Sparkify software in a structured way.
The database will be used to provide the basis for analysis with the goal to extract business intelligence from the generated data.

## The Database Schema
The database follows the star schema with the following tables:
 1. Fact table 'songplays' - tracks the uuser interaction with the songs. 
         The fact table is connected with the dimension tables using foreign keys.
 2. Dimension table 'artists' - enlists all the artists with related data,
 3. Dimension table 'songs'- inlicsts all the songs with related data,
 4. Dimension table 'time'- enlists all the timestamps when the songs were played with related data,
 5. Dimension table 'users'- enlists all the users, who have ever played any songs with related data

## ETL Pipeline 
ETL pipeline has 3 main steps:
 1. Extracting the data from the song_file and log_file json files to Pandas DataFrames
 2. Selecting relevant columns from the DataFrame 
 3. Inserting the records to the relevant Postgres table 

Additional steps for certain fields were required:
 - Timestamp was converted from miliseconds to the uts format
 - song_id and artist_id fields were found by combining the data using additional SELECT query

## Instructions
The repository contains the following files:
 - create_tables.py contains the script to create and reset the relevant database
 - etl.py contains the script to extract the data from the json files and record them to the database
 - sql_queries.py contains the relevant SQL queries, which are used for the aforementioned scripts
 - etl.ipynb is needed for analysis of the etl process
 - test.ipynb is needed to test the results during creation of the etl process

In order to get the expected result please run the following scripts in the listed order:
 1. create_tables.py
 2. etl.py  
