# YouTube Channel Data README

This code is a Streamlit application that interacts with the YouTube Data API, MongoDB, and MySQL to retrieve, store, and visualize data for YouTube channels and their videos.

## Dependencies

The code requires the following dependencies:

- `streamlit`: A web application framework for building interactive web apps.
- `googleapiclient`: A library to interact with Google APIs, specifically the YouTube Data API.
- `pymongo`: A Python driver for MongoDB, used to connect and interact with the MongoDB database.
- `mysql-connector-python`: A Python driver for MySQL, used to connect and interact with the MySQL database.
- `pymysql`: A Python library that provides an interface for connecting to a MySQL database and executing SQL statements.
- `matplotlib`: A plotting library used for visualizing data.
- `pandas`: A data manipulation library used for working with structured data.
- `sqlalchemy`: A SQL toolkit and Object-Relational Mapping (ORM) library for Python, used for connecting to the SQL data warehouse.

## Connecting to Databases

The code connects to two databases:

### MongoDB

The code connects to a MongoDB database using the `pymongo` library. The connection is established with the following details:

```
mongo_client = MongoClient("mongodb+srv://xyz:xyz*@cluster0.pue5wip.mongodb.net/")
mongo_db = mongo_client["my_mongodb_database_youtube"]
mongo_collection = mongo_db["my_mongodb_collection_youtubers"]

```


### MySQL

The code connects to a MySQL database using the `mysql-connector-python` library. The connection is established with the following details:

```
mysql_conn = pymysql.connect(
    host="localhost",
    user="root",
    #password="root",
    database="test",
    charset="utf8mb4",
    cursorclass=pymysql.cursors.DictCursor
)
mysql_cursor = mysql_conn.cursor()
```

## Retrieving Channel Data

The code retrieves channel data from the YouTube Data API by calling the `get_channel_data` function. It takes a YouTube channel ID as input and retrieves information such as the channel name, subscriber count, total videos, playlist ID, and video data. The channel data is then stored in MongoDB using the `insert_one` method.

## Migrating Data to MySQL

The `migrate_data_to_mysql` function migrates the channel and video data from MongoDB to MySQL. It retrieves the data from MongoDB, creates a corresponding table in MySQL for each channel, and inserts the video data into the respective tables. The data migration is performed using SQL queries executed through the `mysql_cursor` object.

## Querying Data

The `query_data` function allows querying the MySQL database to retrieve specific data. It uses SQLAlchemy to create a session and execute a SQL JOIN query between the Channel and Video tables. The results are fetched and processed to display the channel and video information.

## Visualizing Data

The `visualize_data` function retrieves data from the MySQL database for a specific channel and visualizes it using matplotlib and Streamlit's charting capabilities. It creates three types of visualizations:

1. Bar Chart: Displays the likes, dislikes, and comments for each video in a bar chart.
2. Line Chart: Shows the likes and dislikes over time in a line chart.
3. Area Chart: Displays the comments over time in an area chart.

## Executing Custom Queries

The `execute_query` function allows executing custom SQL queries on the MySQL database. The query is passed as an input, and the function executes it using the `mysql_cursor` object. The results, if any, are displayed.

## Running the Application

To run the application, execute the `main` function. The Streamlit web app will be launched, and you can interact with it through the provided UI. You can enter YouTube channel IDs to retrieve data, migrate data to MySQL, query data, and visualize the retrieved data.
