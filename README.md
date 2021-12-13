# An ETL Pipeline for Movies Data

## Overview
With the goal of cleaning and transforming raw data about movies, an ETL pipeline was created from multiple sources to a PostgreSQL database.

### Resources
Data sources: Wikipedia, Kaggle and MovieLens rating
Jupiter Notebook
Python(dependencies: pandas, dumpy, re, sqlalchemy)
PostgreSQL, pgAdmin

## Results

To extract the data, a function named extract_transform_load() was defined in jupyter notebook to read the three files: Wikipedia data, Kaggle metadata, and the MovieLens rating data.

Figure 1
Defining Function to Extract Data Files


To transform the data, some steps were performed. First, a function named clean_movie(movie) was defined to remove duplicate title information.

Figure 2
Defining Function to Clean Data


Second, regular expressions were used to clean a few columns in the wiki_movies_df data frame, such as ‘Box office’ and ‘Budget’. Columns from the kaggle_metadata and ratings data frames were also cleaned.

Figure 3
Cleaning ‘Budget’ Column


Third, the cleaned data frames were merged and further cleaning was performed.

Figure 4
Merging Cleaned Dataframes


Finally, the merged data frames were loaded by adding the data to a PostgreSQL database.

Figure 5
Connecting to the PostgreSQL database


## Summary
In sum, an ETL pipeline was created to extract movies data from multiple file formats. This pipeline generated two SQL tables, movies and ratings, that have no missing information and are ready for data analysis.