# Project Title

YouTube Data Harvesting and Warehousing using SQL, MongoDB, and Streamlit

## Skills Takeaway from This Project

- Python scripting
- Data collection
- MongoDB
- Streamlit
- API integration
- Data management using MongoDB (Atlas) and SQL

## Domain

Social Media

## Problem Statement

The problem statement is to create a Streamlit application that allows users to access and analyze data from multiple YouTube channels. The application should have the following features:

1. Ability to input a YouTube channel ID and retrieve all the relevant data (channel name, subscribers, total video count, playlist ID, video ID, likes, dislikes, comments of each video) using the Google API.
2. Option to store the data in a MongoDB database as a data lake.
3. Ability to collect data for up to 10 different YouTube channels and store them in the data lake by clicking a button.
4. Option to select a channel name and migrate its data from the data lake to a SQL database as tables.
5. Ability to search and retrieve data from the SQL database using different search options, including joining tables to get channel details.

## Approach

The approach for this project involves the following steps:

1. Set up a Streamlit app: Use Streamlit to create a user interface where users can input a YouTube channel ID, view channel details, and select channels to migrate to the data warehouse.

2. Connect to the YouTube API: Use the Google API client library for Python to make requests to the YouTube API and retrieve channel and video data.

3. Store data in a MongoDB data lake: After retrieving data from the YouTube API, store it in a MongoDB database. MongoDB is suitable for a data lake as it can handle unstructured and semi-structured data effectively.

4. Migrate data to a SQL data warehouse: Once data is collected for multiple channels, migrate it to a SQL database for efficient storage and querying. MySQL or PostgreSQL can be used as the SQL database.

5. Query the SQL data warehouse: Use SQL queries, possibly with the help of a Python SQL library like SQLAlchemy, to join tables in the SQL data warehouse and retrieve data based on user input.

6. Display data in the Streamlit app: Visualize and display the retrieved data in the Streamlit app. Utilize Streamlit's data visualization features to create charts and graphs for data analysis.

## Example Data Extraction from YouTube to MongoDB

Here's an example of the data structure extracted from YouTube and stored in MongoDB:

```json
{
    "Channel_Name": {
        "Channel_Name": "Example Channel",
        "Channel_Id": "UC1234567890",
        "Subscription_Count": 10000,
        "Channel_Views": 1000000,
        "Channel_Description": "This is an example channel.",
        "Playlist_Id": "PL1234567890"
    },
    "Video_Id_1": {
        "Video_Id": "V1234567890",
        "Video_Name": "Example Video 1",
        "Video_Description": "This is an example video.",
        "Tags": ["example", "video"],
        "PublishedAt": "2022-01-01T00:00:00Z",
        "View_Count": 1000,
        "Like_Count": 100,
        "Dislike_Count": 10,
        "Favorite_Count": 5,
        "Comment_Count": 20,
        "Duration": "00:05:00",
        "Thumbnail": "https://example.com/thumbnail.jpg",
        "Caption_Status": "Available",
        "Comments": {
            "Comment_Id_1": {
                "Comment_Id": "C1234567890",
                "Comment_Text": "This is a comment.",
                "Comment_Author": "Example User",
                "Comment_PublishedAt": "2022-01-01T00:01:00Z"
            },
            "Comment_Id_2": {
                "Comment_Id": "C2345678901",
                "Comment_Text": "This is another comment.",
                "Comment_Author": "Another User",
                "Comment_PublishedAt": "2022-01-01T00:02:00Z"
            }
        }
    },
    "Video_Id_2": {
        "Video_Id": "V2345678901",
        "Video_Name": "Example Video 2",
        "Video_Description": "This is another example video.",
        "Tags": ["example", "video"],
        "PublishedAt": "2022-01-02T00:00:00Z",
        "View_Count": 2000,
        "Like_Count": 200,
        "Dislike_Count": 20,
        "Favorite_Count": 10,
        "Comment_Count": 30,
        "Duration": "00:10:00",
        "Thumbnail": "https://example.com/thumbnail.jpg",
        "Caption_Status": "Not Available",
        "Comments": {}
    }
}
```

## Example SQL Tables

Here are some example SQL tables that can be created in the SQL data warehouse:

| Table: Channel            |
|---------------------------|
| Channel_Id (Primary Key)  |
| Channel_Name              |
| Subscription_Count        |
| Channel_Views             |
| Channel_Description       |
| Playlist_Id               |

| Table: Video                  |
|------------------------------|
| Video_Id (Primary Key)        |
| Video_Name                    |
| Video_Description             |
| Tags                          |
| PublishedAt                   |
| View_Count                    |
| Like_Count                    |
| Dislike_Count                 |
| Favorite_Count                |
| Comment_Count                 |
| Duration                      |
| Thumbnail                     |
| Caption_Status                |
| Channel_Id (Foreign Key)      |

| Table: Comment             |
|----------------------------|
| Comment_Id (Primary Key)   |
| Comment_Text               |
| Comment_Author             |
| Comment_PublishedAt        |
| Video_Id (Foreign Key)     |

## Project Evaluation Metrics

The following metrics will be considered for evaluating the project:

- Modular code structure: Write modular code in functional blocks to improve maintainability and readability.
- Maintainability: Ensure that the code can be easily maintained as the codebase grows.
- Portability: Make the code work consistently in different environments (operating systems).
- GitHub repository: Maintain the project code on GitHub and keep the repository public for others to review.
- Readme file: Include a detailed readme file in the GitHub repository, explaining the project workflow and execution.
- Coding standards: Follow the coding standards defined in PEP 8 (https://www.python.org/dev/peps/pep-0008/) for clean and consistent code.
- Demo video: Create a demo video of the working model and post it on LinkedIn to showcase the project.

## References

- Streamlit: https://docs.streamlit.io/library/api-reference
- MongoDB: Topic: MongoDB - Skill Enhancement Session
- YouTube API: https://developers.google.com/youtube/v3/getting-started
- API Data Collection Reference Colab

**Orientation Links**:
- English Recording Link
- Tamil Recording Link
