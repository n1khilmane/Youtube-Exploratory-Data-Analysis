# Youtube-Exploratory-Data-Analysis
Perform Exploratory Data Analysis on Youtube data for countries like India, United States of America, etc. on Pyspark and produce visualizations on Kibana dashboard. We analyze the data to obtain insights on country level, few of which are:

1) Channel with most views, likes, dislikes, comments
2) Distribution of videos across categories
3) Top channels and its statistics (mean/max/sum) for views, likes, dislikes, comments, etc.
4) Most watched/uploaded categories of videos

## Data Acquisition
The data used for this project is collected from the available Youtube data API. This API provides access to data like the view count, likes, dislikes, category of videos, title and description of videos etc. We cleaned this data of redundant and null values for analysis.

## Data Preparation

We need to explore data before analyzing it. First, we performed data cleaning. Youtube provides their data in a rather clean format, so our data cleaning involves only removing unnecessary symbols, and columns, retrieving corresponding categories from ID, grouping data, and handling data types.

1) Preprocessing of data: Unnecessary columns like Description, comments disabled etc, are not really useful for us. So we get rid of them. 

2) Retrieving the category name from ID: The data has a category ID field which is an integer. There is a json file available to read the corresponding category name. We need to replace the category ID with its corresponding name by reading the json file.

3) Datatype of columns: The data provided by the stack overflow data archive had columns like ‘ViewCount’ as strings. Such columns were converted to Integer datatypes to make further computations possible. Converted published date/time to the right format which can be pushed to ES.

4) Grouping of data: We group the videos based on their categories and country for both India and USA to get insights on the viewing behavior in the 2 countries.

## High level design overview

![diagram](https://github.com/n1khilmane/Clubroom/blob/main/images/arch.png)




