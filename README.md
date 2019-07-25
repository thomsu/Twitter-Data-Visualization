# Twitter Data Visualization

## Synopsis

This project focuses primarily on getting data using an API and exploring the data with some graphic visualization. Tweepy is a third party Twitter API tool that is simple to use and has many of the Twitter Restful API features. It is used here to pull information on tweets by the top 5 Democratic presidential candidates, Bernie Sanders, Elizabeth Warren, Joe Biden, Kamala Harris and Pete Buttigieg. An attempt is made using Plotly to map out the US state where Twitter users who retweet those tweets are from. There are also two histograms about favorite and retweet counts from the data collected.

## Technologies

The codes are written in a Jupyter notebook using the following libraries:

* Tweepy version: 3.8.0
* Pandas version: 0.23.4
* Plotly version: 3.1.0
* Matplotlib version: 3.0.3

## File Description

The files found in this repository are:

* CandidatePlotly.xlsx -- This file contains a pandas dataframe that is passed as a variable to the plotly_plot function to get a map plot of Twitter users who retweeted.

* candidate.xlsx -- This file holds all Democratic presidential candidates' tweets data.

## Data Collection

The tweepy_call function was used to establish a connection. It requires several API keys for user authentication which can be obtain through Twitter online. The build_df_from_api function streamlines the rest of the process. By just providing the Twitter handle of a Twitter user and the number of most recent tweets, the function fetches the metadata of those tweets and transfer the information into a pandas dataframe. Twenty of the most recent tweets were collected for each of the presidential candidate.

## Data Cleaning

There are 2 columns that holds lists of ids and locations and a single column that contains a dictionary of metadata information. While some of the information from the lists are useful for visualizing the data, the dictionary provides little value. The column of list with the user locations is reconfigured to show a tally of the states where the retweets originated. There are here many with no values, some are from outside of the country and some where the exact location cannot be determined. These entries were dropped.

## Data Visualization

THe Plotly map shows the states where the retweets came from. Run the map plot function for each of the candidates to get the representative map. The two histograms reveals the favorite and retweet counts of all 20 tweets by each candidate and the breakdown of states where the retweets came from for the most retweeted message.
