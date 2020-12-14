# ETL-Project1
Extract Transfer Load Project

# Summary

2020 appears to have far exceeded voting rates in recent US presidential elections.  According to estimates on Wikipedia, 2020 voting among eligible population was between 66.4% and 72.1%.  If correct, this would be the highest turnout % since the election of 1900 (re-election of William McKinley). At-least 22 million more votes were cast in 2020 vs. 2016 with an eligible population increase of only approximately 9 million. 

My project collects election related data from various sources to build a database that will allow analysis, by state of changes in voter Eligible age population and voter turnout %.

I further collected actual (2016) and current estimates (2020) of voting results by party for each state for further possible analysis

# Extract

After examining many possible sources of data, I decided to gather votor tunout data via http://www.electproject.org/

This appeared to have the most complete ,relevant and up to date data for this project on voter turnout by state. 
Voter turnout data tables for 2020 and 2016 general elections were obtained from the website through google docs links, then downloaded 
as CSV files.

Election results by state data was more difficult to obtain than expected.  Most datasets were in clickable map format for both elections, and very few sited had 2020 data as results are/ were not official at time of collection.

2016 results were finally obtained from the New York Times: https://www.nytimes.com/elections/2016/results/president via copying and pasting multiple tables to a CSV file.

2020 results were found at the cook political report: https://cookpolitical.com/2020-national-popular-vote-tracker with a downloadable CSV format

# Transform

All four datasets were then trasformed via Python/ Pandas to contain the desired data and correct formatting to create a database.

The 2020 and 2016 turnout data were transformed similarly:
    1) Dropped extra rows not containg data
    2) Dropped extraneous columns and renamed remaining data columns
    3) reformatted relevant columns to numeric format, including removing punctuation symbols

2016 Election Results:
    1)created a new column with state abbreviation codes for ability to index and join in database
    2) removed columns of data not needed and renamed remaining columns
    3) reformatted relevant data to numeric format
    4) sorted rows alphabetically

2020 Election Results
    1) Dropped columns of data not relevant
    2) reformatted numeric data, dropped extra punctation symbols

# Load

I created a new database using PostgreSQL to contain 4 tables, one for each cleaned DataFrames
I connected my Jupyter notebook directly to the database using SQLAlchemy and loaded the DataFrame data into each table

To ensure functionality, I created a join Query in SQL of the data tables.








