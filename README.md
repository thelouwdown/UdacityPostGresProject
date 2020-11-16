# Sparkify DataBase

This program is used to create a Postgres database to optimise queries on songplay analysis for Sparkify.
To do this, first a database schema is created, followed by an ETL pipeline.

## Repository Files

There are 4 files in the package:
- create_tables.py
- sql_queries.py
- etl.ipynb
- etl.py
- test.py

## Data

There are 2 data sources used to populate the database: log_data and song_data.

- log_data -  JSON user activity logs on the Sparkify app based on user configurations
- song_data -  JSON metadata on the songs as well as artist information

## Database tables
There are 5 tables that are created to optimise the queries for our analysis:
- A songplay table
- A user table
- A song table
- An artist table 
- A time table

## Usage

### create_tables.py:
This file is used to drop and creates your tables. You run this file to reset your tables before each time you run your ETL scripts.

create_database()
"""
- Creates and connects to the sparkifydb
- Returns the connection and cursor to sparkifydb
"""
drop_tables(cur, conn)
"""
- Drops each table using the queries in `drop_table_queries` list.
"""
create_tables(cur, conn)
"""
- Creates each table using the queries in `create_table_queries` list. 
"""
main()
"""
- Drops (if exists) and Creates the sparkify database. 
- Establishes connection with the sparkify database and gets
    cursor to it.  
- Drops all the tables.  
- Creates all tables needed. 
- Finally, closes the connection. 
"""

### sql_queries.py
This file contains SQL queries that defines and creates the database schema and tables, inserts records and finds songs

### etl.ipynb
This notebook develops the ETL process for each of the tables: songplay, users, songs, artists, time. It reads and processes a single file from song_data and log_data and loads the data into your tables. This notebook contains detailed instructions on the ETL process for each of the tables.

### etl.py
This file reads and processes files from song_data and log_data and loads them into your tables.

process_song_file(cur, filepath)
"""
- creates the songs and artists dimension tables
"""
process_log_file(cur, filepath)
"""
- Creates the time and users dimensional tables, as well as the songplays fact table
"""
process_data(cur, conn, filepath, func)
- get all files matching extension from directory

### test.py
This file displays the first few rows of each table to let you check your database.
