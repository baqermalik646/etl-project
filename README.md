# etl-project

Kendall Gillies. (2017). Video Game Sales and Ratings. https://www.kaggle.com/datasets/kendallgillies/video-game-sales-and-ratings
Deep Contractor. (2021-2022). Top Video Games 1995-2021 Metacritic. https://www.kaggle.com/datasets/deepcontractor/top-video-games-19952021-metacritic

1. Extract
-We are analysts at a video game company looking to use previous data of video game sales and user ratings to see if there is a correlation between the two.
-We extracted the two video games datasets, in CSV format, from Kaggle. One dataset provided us with the name of the video game, platform, date of release, and user ratings. The second dataset provided us with the name of the video games as well as the global sales of each video game.

2. Transform
-We brought in our two CSV files into a Jupyter notebook to transform the data.
-First, we imported our dependencies and read in the first dataset to a dataframe which provided us with the ratings data.
-We then cleaned up this dataframe to remove unnecessary columns. Once we had only the necessary columns, we worked on transforming the name of each video games to replace the spaces with underscores, remove unnecessary characters in the names, and made all of them lowercase. This was done to make it easier for us to merge the two datasets later on the names of the video games.
-Next, we read in the second dataset to a dataframe which provided us with the global sales information. We cleaned this dataframe to only include the necessary columns of the video game name and the global sales. We transformed the names of the video games to replace spaces with underscores, remove unnecessary characters in the names, and made all of them lowercase. Once this was done, we changed the column titles to match with the previous dataframe which was lowercase letters.
-Once both dataframes were cleaned, we were able to merge the two together on the "name" column to make one dataframe with only the name, platform, release date, user review, and global sales columns. Once the merged dataframe was created, we dropped any duplicate values based on the "name" column.
-While reviewing the final datatypes in the merged dataframe, we could see one column, user review, was showing as an object instead of a float based on the numerical values. Once we figured this was incorrect, we converted the values in this column from an object to a float.

3. Load
We decided to load the cleaned data in a relational database. Once the merged dataframe was transformed, we created a database called etl_project2 and a table called "video_games" in pgAdmin with columns that matched with the dataframe. The columns created were name, platform, release date, user review, and global sales. Once the database and table were created, we started the connection between Python and SQL within our Jupyter notebook and using this connection, we loaded our dataframe into the database into the respective columns within the table. We wanted to confirm that the data was loaded correctly so we created a query in our notebook to see a few lines of data from the table.
