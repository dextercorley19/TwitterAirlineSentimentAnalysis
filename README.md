# TwitterAirlineSentimentAnalysis
**Analysis of Twitter Sentiment data from [Kaggle dataset](https://www.kaggle.com/datasets/crowdflower/twitter-airline-sentiment)**

### [Final Presentation](/TwitterSentimentPPT.pptx) & [Alteryx Workflow](/TwitterSentimentFinalWKFLO.yxmd)


 
# Project Outline

## Analyze data set to produce insight report
 

Note: analysis plan and methods of enquiry are at the student’s discretion. This is designed to be a hands-on application of the analysis and data science tools you have learned during your program.

 

The output of this section of the homework will be; a) the contents of the Insight report (i.e. what you have learned from the data and analysis) and b) the action list of steps you took – including any code or models used.

 

## Create Insight report and key executive summary
 

Note: This is an executive summary presentation, up to 10 slides (not including appendix) that present the analysis and what is learnt from the data. Students are encouraged to use any form of visualization (including graphs and charts) that they feel aids the explanation and analysis of the data.

 

## Create action list of steps
 
 ## Data Overview & Thoughts
 | Quantitative | Description |  | Qualitative | Description |
| --- | --- | --- | --- | --- |
| tweet_id | Contains the tweet ID, each row contains a unique value. There is a fair bit of junk, need to just delete these rows with a conditional statement on length of the string. |  | airline_sentiment | Contains whether the sentiment towards the airline is negative, positive, or neutral. It contains some junk but should be easy to parse out through a filter. |
| airline_sentiment_confidence | Contains the confidence value from the sentiment analysis on a scale of 0-1, with 1 being extremely confident. No junk cells |  | negativereason | Contains the reason for why sentiment was negative. Null if not negative. Has some junk, most seems to be from a misread in and contains data from other colums |
| airline_sentiment_confidence | Contains the confidence level for the negative reason result. Has some Null and spillover from other columns |  | airline | Contains the airline corresponding to the tweet. Has some Null and spillover |
| retweet_count | Contains the number of retweets the tweet had. Most are 0 but could be interesting to get some insights from the ones that had more. Most retweets one had was 44 - possibly from others on the same flight?.. |  | airline_sentiment_gold | Contains positive, neutral, or negative results. I think gold being in the title represents important tweets. Less than 50 values for positive, negative and neutral, the rest is null or spillover. |
| tweet_coord | Contains the geotagged location of the tweet. About 1000 values - could be interesting to analyze what sentiments were coming from where. Maybe map it? |  | name | Contains the twitter handle for the users tweet. Something notable is that some users have multiple records, Jetbluenews being the most at 63. Bristishairnews also has 11. The others seem to be from personal accounts. Contains some null and spillover. |
| tweet_created | Contains the date of each tweet. |  | negativereason_gold | Contains important rows for the negativereason field. Other than that just null values |
|  |  |  | text | Contains the text from the tweet. 249 null, 60 not ok |
|  |  |  | tweet_location | Contains the location of the tweet. Different nomenclature for almost all of the data (ex. NYC, or NY, or New York). Lots of null, 171 not ok |
|  |  |  | user_timezone | Contains the timezone for the user. 5k ish nulls |

- Big data quality issue when it comes to some of the delta actually being jetblue

Hypothesis’ and Insight Pathways

- Get metrics for each airline (Sentiment towards them, gold?, regional tags, (possibly add in cost for those flights, API? $$$)
- Since each of the airlines have different amount of reviews, comparing them directly against each other leads to misinformation. Instead, comparing the percentages between, positive, negative, and neutral would work.

