## Data Modeling With Postgres

The goal of this project to convert data json files in the data/song_data and data/log_data directories into records using python pandas and then loaded into the **sparkify** database.

## Schema Design and ETL Pipeline

The star schema has 1 fact table songplay and 4 dimension tables (users,songs,artists,time), we create table by deciding the PRIMARY KEY, NOT NULL and Datatype.
Drop , Create, Insert and Select queries define in **sql_queries.py**.**create_tables.py** uses funtion create_database,drop_tables and create_tables.

**ETL**

The script connects to the Sparkify database, Extract, Transform, Load processes in **etl.py**  populate the **songs** and **artists** tables with data derived from the JSON song files, data/song_data. Processed data derived from the JSON log files, data/log_data, is used to populate **time** and **users** tables. A SELECT query collects song and artist id from the **songs** and **artists** tables and combines this with log file derived data to populate the **songplay** fact table.

The ETL processes from **etl.ipynb** were used as input to etl.py to process all the files in **data/song_data** and **data/log_data** and insert the records in the Sparkify database.         