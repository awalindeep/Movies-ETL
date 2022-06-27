# Movies ETL - Extract, Transform and Load

_An ETL Movies Analysis using Python, RegEx and SQL Databases_

## Project Overview

### Background

Raw data exists in multiple places and forms. In order to perform any kind of data analysis, this data needs to be cleaned and structured. Data pipeline process  **ETL – Extract, Transform, and Load**  is a core concept in data engineering, ensuring that data is consistent, maintains its integrity, and nonetheless strives for automatization of data wrangling. Without a consistent and robust data structure, it’s nearly impossible to perform any meaningful analysis.

![ETL](https://github.com/awalindeep/Movies-ETL/blob/AwalinGHMAIN/Resources/ETL.png)


### Purpose

The Amazing Prime, a video streaming company, decided to sponsor a  _hackathon_, where participants trying to predict which low budget movies being released will become popular. Participants of a hackathon need a clean data in order to perform analyses for their algorithms. In order to provide organized and clean dataset, this project focuses on  _ETL_* or  **Extract, Transform and Load**  process and includes the following:

-   **Extracting**  data from two different sources.
    -   web scrape of Wikipedia website for all movies released since 1990
    -   data from Kaggle website for rating data.
-   **Transforming**  data using Jupyter Notebook, Python, Pandas and Python RegEx module.
-   **Loading**  data using PostgreSQL and pgAdmin to host final cleaned data set.

## Overview of the code

The goal of this analysis is to create automated pipeline that extracts, transform and loads data. This analysis consists of four parts, where each step is building up from beginning of extracting data and function testing, through transformation and cleaning process to its final step connect and load to the database. The entire process of ETL can be executed with a single call of the function  _**extract_transform_load**_  in the final step  [ETL_create_database.ipynb](https://github.com/awalindeep/Movies-ETL/blob/AwalinGHMAIN/ETL_create_database.ipynb) The ETL process is broken down into four jupyter notebook files:

1.  [ETL_function_test.ipynb](https://github.com/awalindeep/Movies-ETL/blob/AwalinGHMAIN/ETL_function_test.ipynb)
    
    -   Data is extracted from the website in JSON and CSV formats.
    -   Data is transformed into Pandas data frames.
    -   JSON file requires extra step – loading file first and then transforming into data frame.
2.  [ETL_clean_wiki_movies.ipynb](https://github.com/awalindeep/Movies-ETL/blob/AwalinGHMAIN/ETL_clean_wiki_movies.ipynb)
    
    -   Function  _clean_movie_  combines scattered data of alternative languages into one column  _alt_titles_.
        
    -   Its subfunction  _change_column_name_  organizes column names into consistent pattern.
        
    -   In the function  _extract_transform_load_  the transformation process of wiki movies data begins and includes:
        
        -   Python  **list comprehensions**.
        -   apply() and map() methods in combination with  **lambda functions**.
        -   regular expressions or  **RegEx**.
3.  [ETL_clean_kaggle_data.ipynb](https://github.com/awalindeep/Movies-ETL/blob/AwalinGHMAIN/ETL_clean_kaggle_data.ipynb)
    
    -   Function  _extract_transform_load_  gets new tasks for cleaning Kaggle data and includes:
        
        -   Changing datatypes, using methods pd.to_numeric, astype() and python comparison operators for Boolean types.
        -   Filling missing values and filtering unwanted columns.
        -   Merging data frames using  _pd_merge_  method.
4.  [ETL_create_database.ipynb](https://github.com/awalindeep/Movies-ETL/blob/AwalinGHMAIN/ETL_create_database.ipynb)
    
    -   Finally, the function in its final step connects to the database by  **sqlalchemy**  library and  **to_sql**  method.
    -   Complete ETL process can be executed with a single function  _extract_transform_load_  call.


**Practice File Results**
![ETL_practice](https://github.com/awalindeep/Movies-ETL/blob/AwalinGHMAIN/Resources/Movies-ETL_time.png)

**Deliverable 4 File Results**

![Rating-ETL](https://github.com/awalindeep/Movies-ETL/blob/AwalinGHMAIN/Resources/rating_time.png)


Ultimately, we were able to clean, merge the datasets and export the two new tables into PostgreSQL by using Python. The final results created a movies table with 6,052 rows. A 17% reduction from the original of 7,311 and a ratings table with 26,024,289 rows.

![Movies](https://github.com/awalindeep/Movies-ETL/blob/AwalinGHMAIN/Resources/movies_query.png)

![rating](https://github.com/awalindeep/Movies-ETL/blob/AwalinGHMAIN/Resources/ratings_query.png)

## Resources

Data Sources:

-   Wikipedia web scrape  [JSON file](https://github.com/awalindeep/Movies-ETL/blob/AwalinGHMAIN/Resources/wikipedia-movies.json)
-   Kaggle data from  [Kaggle.com](https://www.kaggle.com/rounakbanik/the-movies-dataset)  - two files: [movies_metadata.csv](https://github.com/awalindeep/Movies-ETL/blob/AwalinGHMAIN/Resources/movies_metadata.csv) and [ratings.csv](https://github.com/awalindeep/Movies-ETL/blob/AwalinGHMAIN/Resources/ratings.csv)

Enviroment:

-   Python 

Dependencies:

-   Please see Jupyter Notebook  [ETL_create_database.ipynb](https://github.com/awalindeep/Movies-ETL/blob/AwalinGHMAIN/ETL_create_database.ipynb) for complete list of dependencies

Software:

-   Jupyter Notebook
-   PostgreSQL and PgAdmin
