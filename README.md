# Capstone Project Proposal

### What are you trying to do?

I'd like to do sentiment analysis on the political subreddits like /r/politics within Reddit. Ideally, the analysis will be done with BERT or another SOTA language model.

Sentiment analysis allows insight into the views of users in aggregate, in general or on some specific topic. I would like to calculate sentiment on a post-by-post basis by running a sentiment regressor, perhaps measuring from 0.0-1.0, on all comments for a given post. My hypothesis is that political discourse has become more polarized within reddit. I would love to test this hypothesis, which I'll explain in more detail below.

I would also like to see how political subreddits' opinion change over time on specific subjects. For example, it would be interesting to filter on posts containing "Bernie" to see how reddit's feelings towards Bernie Sanders have changed from the 2016 democratic nomination to today. 

### How has this been solved before?

It's well documented within the social sciences that the US has become increasingly politically divided over the last few decades ([see here](https://www.people-press.org/2014/06/12/political-polarization-in-the-american-public/)). 

Within the world of Data Science, sentiment analysis is well-studied on social media data. However, I haven't found anything looking at political subreddits in particular. The closest I could find is someone predicting comment score from text.
* [Related 0](https://www.kaggle.com/ehallmar/reddit-comment-score-prediction#__sid=js0)
* [Related 1](https://towardsdatascience.com/determining-presidential-approval-rating-using-reddit-sentiment-analysis-7912fdb5fcc7)

### What is new about your approach, why do you think it will be successful?

I would like to measure not just overall sentiment for a subreddit, but how extreme the views are. Average sentiment wouldn't capture this, so I propose using the variance of sentiment to measure this. And although I'm sure others have used BERT/GPT2/XLNet for sentiment analysis on reddit, I haven't seen anything close to the project I'm working on.

### Who cares? If you're successful, what will the impact be?

1. It could be valuable evidence on the political polarity hypothesis.
2. It may turn up interesting results on how opinions of the masses fluctuate over time. This phenomenon is well known yet perhaps not well understood.

### How will you present your work?

Given unlimited resources, I'd like to make a web app for the project so that users can play around (see: experiment) with the data and different subreddits. But given the scope of the project, I believe the analysis should be stored in a static format, via presentation and github.

### What are your data sources? What is the size of your dataset, and what is your storage format?

All reddit comments to date, located [here](https://files.pushshift.io/reddit/comments/). Back-of-the-envelope calculation puts this at ~400 GB. Perhaps 1/100th of this data would fall under political subreddits, which is not too large. I will begin downloading from newest to oldest and work my way back, with the understanding that processing the entire dataset may not be feasible. This data is stored monthly as json files.

Sample json data [here](https://files.pushshift.io/reddit/comments/sample_data.json).

### What are potential problems with your capstone?

1. Too much data to process. Solution: Just work with part of the dataset.
2. Difficult/expensive to use BERT or other state of the art tool. Solution: use simple pretrained model like [nltk's vader module](https://www.nltk.org/api/nltk.sentiment.html).
3. Too much analysis to do. Solution: Just focus on one of the two goals outlined above.

### What is the next thing you need to work on?

I need to identify which SOTA language model that optimizes for ease of use and hardware requirements. Then train on IMDB dataset to be a sentiment analysis regressor.
