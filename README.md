# Project 3: Web APIs & Classification - Reddit

## Directory Structure

├── project_3
    ├── dataset2
        ├── cooking1.csv
        ├── cooking2.csv
        ├── cooking3.csv
        ├── cooking4.csv
        ├── cooking5.csv
        ├── parenting1.csv
        ├── parenting2.csv
        ├── parenting3.csv
        ├── parenting4.csv
        ├── parenting5.csv
    ├── Cooking.ipynb
    ├── README.md
    └── Project 3.pdf

## Executive Summary

Reddit is the social network made up of forums. It is the space in which users define relevant content.

The purpose of the platform is exactly that you can speak your mind without fear of being judged.

In addition, the platform encourages participations and discussions on issues among users within the forums of each theme.

But not everyone will see this, only those who have an interest in the topic spoken, or those who participate in the forum will have direct access to the discussion. The network is literally created and stimulated by the users.

But the truth is that despite the “vintage” design Reddit is quite simple indeed. The network is very dynamic and affordable.

This is because Reddit will only present to the user content that is of interest to him, ie content that is within the forum in which he participates or follows.

The goal of our project is to create a model that will classify users reddit post by the owrds used in both title and post, and with that, increase accuracy in a campaign to reach high intent users resulting in efficient conversions and marketing efficiency.

## Description of Data

### Size
The Reddit post data consist of 2,445 rows (53% posts for Parenting, 47% posts for Cooking). Please refer to the Data Dictionary section to see which columns were selected for the model.

### Source
The data was scraped for this project by using a Reddit api:

The file provides a wide range of metadata scraped from the Reddit r/parenting and r/cooking subreddits, which is organized by post by row. Multiple CSV's were created during the data collection process.

### Data Dictionary

|Feature|Type|Description| 
|---|---|---|
|title|object|title of the post| 
|posts|object|text of the post| 
|subreddit|object|name of subreddit of our project|

## Model Creation and Score

### Model Steps

Below is a summary of steps to create a model that categorizes posts to a subreddit:

Gather posts from target subreddits and combine into one dataset Clean the data and do preliminary EDA Utilize stemming, lemmatization, regex, and/or stop words to create clean tokens Choose transformers and models to use in a pipeline Gridsearch for optimal parameters to fit the pipeline

### Check the scores of the models

#### TfidfVectorizer and Multinomial Naive Bayes
lowercase=True, stop_words="english" max_df=.95 min_df=10 max_features=1000 vocabulary=None binary=False ngram_range=(1, 2))

#### TfidfVectorizer and Random Forest
lowercase=True, stop_words="english" max_df=.95 min_df=10 max_features=1000 vocabulary=None binary=False ngram_range=(1, 2)) "min_samples_split"=25 "min_samples_leaf"=1 "max_depth":10

#### TFIDFVectorizer and Adaboost - Gradient Boosting
lowercase=True, stop_words="english" max_df=.95 min_df=10 max_features=1000 vocabulary=None binary=False ngram_range=(1, 2)) 'max_depth'=11 'n_estimators'=5 'learning_rate'=0.06

### Model Scores
TFIDFVectorizer and Multinomial Naive Bayes - 98.32% train and 98.12% test TfidfVectorizer and Random Forest - 97.66% train and 93.94% test TFIDFVectorizer and Adaboost - Gradient Boosting - 96.14% train and 93.52% test

The pipeline with the highest test accuracy scores is TFIDFVectorizer and Multinomial Naive Bayes model, with an accuracy score of 98.12% on the test data. However, all 3 models were very high in accuracy scores.

## Data Visualization
Conclusion
With this model marketing teams will be able to mamximize the return of investors in MFCG industry, on both subreddits.

## Next Steps
Utilize regex to clean the tokens more thoroughly Perform the same analysis on the comments section of the subreddit Explore the 4 posts that caused type I errors

## Outside References:

https://www.reddit.com/ 
https://en.wikipedia.org/wiki/Reddit
