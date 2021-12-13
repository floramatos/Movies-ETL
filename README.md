# An ETL Pipeline for Movies Data

## Overview
With the goal of cleaning and transforming raw data about movies, an ETL pipeline was created from multiple sources to a PostgreSQL database.

### Resources
- Data sources: Wikipedia, Kaggle and MovieLens rating
- Jupiter Notebook
- Python(dependencies: pandas, dumpy, re, sqlalchemy)
- PostgreSQL, pgAdmin

## Results

To extract the data, a function named extract_transform_load() was defined in jupyter notebook to read the three files: Wikipedia data, Kaggle metadata, and the MovieLens rating data.

Figure 1
Defining Function to Extract Data Files
![Screen Shot 2021-12-13 at 10 53 26 AM](https://user-images.githubusercontent.com/89421440/145876276-aaf4484a-b191-4c97-b283-9e8b1ba54916.png)


To transform the data, some steps were performed. First, a function named clean_movie(movie) was defined to remove duplicate title information.

Figure 2
Defining Function to Clean Data
![Screen Shot 2021-12-13 at 11 10 43 AM](https://user-images.githubusercontent.com/89421440/145876376-1ec30ad7-1758-428d-886e-9ba3245d9e67.png)


Second, regular expressions were used to clean a few columns in the wiki_movies_df data frame, such as ‘Box office’ and ‘Budget’. Columns from the kaggle_metadata and ratings data frames were also cleaned.

Figure 3
Cleaning ‘Budget’ Column
![Screen Shot 2021-12-13 at 11 14 28 AM](https://user-images.githubusercontent.com/89421440/145876427-db674bf4-250c-412f-a235-4355a56d3ae7.png)


Third, the cleaned data frames were merged and further cleaning was performed.

Figure 4
Merging Cleaned Dataframes
![Screen Shot 2021-12-13 at 11 21 42 AM](https://user-images.githubusercontent.com/89421440/145876448-a83fb374-2eda-4294-868b-2dd7f1568d41.png)


Finally, the merged data frames were loaded by adding the data to a PostgreSQL database.

Figure 5
Connecting to the PostgreSQL database
![Screen Shot 2021-12-13 at 11 22 10 AM](https://user-images.githubusercontent.com/89421440/145876473-d07e22ca-0349-49f7-91ea-0708497d1be7.png)


## Summary
In sum, an ETL pipeline was created to extract movies data from multiple file formats. This pipeline generated two SQL tables, movies and ratings, that have no missing information and are ready for data analysis.
