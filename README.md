# Sparkify DataBase

This program is used to create a Postgres database to optimise queries on songplay analysis for Sparkify.
First a database schema is created, followed by an ETL pipeline.

## Repository Files

There are 4 files in the package:
create_tables.py
sql_queries.py
etl.ipynb
etl.py

## Data

There are 2 data sources used to populate the database: log_data and song_data.

log_data -  JSON user activity logs on the Sparkify app based on user configurations
song_data -  JSON metadata on the songs as well as artist information

## Usage

### create_tables.py:

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
#This file contains SQL queries that defines and creates the database schema and tables, inserts records and finds songs

### etl.ipynb
#This notebook develops the ETL process for each of the tables: songplay, users, songs, artists, time

### etl.py

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


Project Description
In this project, you'll apply what you've learned on data modeling with Postgres and build an ETL pipeline using Python. To complete the project, you will need to define fact and dimension tables for a star schema for a particular analytic focus, and write an ETL pipeline that transfers data from files in two local directories into these tables in Postgres using Python and SQL.

