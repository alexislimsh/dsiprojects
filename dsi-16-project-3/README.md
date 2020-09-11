# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: NLP and API with Reddit

### By Alexis Lim, DSI-16

## Executive Summary

The [LifeProTips subreddit](https://www.reddit.com/r/LifeProTips/) is one of the most popular subreddits in Reddit with over 18.4M members, offering advice, hacks and tips on different aspects of life (family, work, hobbies etc.). It also has multiple offshoots including [UnethicalLifeProTips](https://www.reddit.com/r/UnethicalLifeProTips/), [IllegalLifeProTips](https://www.reddit.com/r/IllegalLifeProTips/) and a satire subreddit [ShittyLifeProTips](https://www.reddit.com/r/ShittyLifeProTips/).

In this project, we want to investigate the differences between LifeProTips and UnethicalLifeProTips. In their own words, the respective definitions are:
- LPT: Tip that improves your life in one way or another.
- ULPT: Tip that improves your life in a meaningful way, perhaps at the expense of others and/or with questionable legality.


_Problem Statement_

How can we qualify what exactly makes a pro tip unethical? By building a classification model for the two subreddits, we want to see if we can accurately predict posts for the two subreddits as well as investigate the following:
- We can understand what 'unethical' is defined as by society (using the Reddit community as a proxy).
- We can identify if the tips submitted to each subreddit are significantly different in any way, even though both purport to 'improve lives'.
- As the definition provided by the ULPT subreddit describes anti-social behaviour, we can also seek to understand what constitutes anti-social behaviour.


## Table of Contents

- Data Retrieval
- Exploratory Data Analysis
- Data Processing
- Model Fit and Testing
- Refining the Model
- Model Interpretation
- Conclusion & Recommendations


## Data Dictionary [Processed]
|Feature|Data Type|Description|
|-------|---------|-----------|
|subreddit|str|Name of subreddit|
|selftext|str|Post body|
|score|int|Total post score|
|title|str|Post title|
|upvote_ratio|float|Ratio of upvote of all upvotes and downvotes|
|created_utc|timestamp|Timestamp UTC|
|id|str|Unique id of post|
|fullname|str|Unique id of post|
|num_comments|int|number of comments|
|url|str|URL to post|
|total_awards_received|int|Total number of awards|
|author|str|Tuthor name|
|subreddit_cat|int|Mapped category for subreddits (1: ULPT, 0: LPT)|
|all_text|str|Combined title and post body text|
|timestamp|datetime-object|Timestamp for US EST|
|day_posted|datetime-object|Date posted|
|time_posted|datetime-object|Time of the day posted|
|month_posted|int|Month posted|
|weekday_posted|int|Day of the week mosted (starts at 0 for Monday)|
|hour_posted|int|Hour posted|
|all_text_cleaned|str|Processed text for model|
|polarity|float|Polarity score of all_text using TextBlob|
|subjectivity|float|Subjectivity score of all_text using TextBlob|
|num_words_all|int|Number of words in all text|


## Conclusion & Recommendations

Based on our investigations and model, while we managed to create a model that successfully predicts around 80% of all posts. Some things we can conclude are:

- **Unethical == materialism?:** There seems to be a greater focus on purchases and 'gaming' the system, in our ULPT posts, suggesting that people see this behaviour as unethical (but still beneficial to yourself.) Aside from this theme, we can't see any strong indications for the term.

- **Defining unethical:** While there are some themes that stand out for both subreddits, we can't explicitly conclude what 'unethical' or anti-social behaviour is. However, this may come down to the fact that since these posts are written from a 1st person POV and focused on actions, we may not see language that defines negative behaviour. We may be better off examining a different subreddit e.g. AmITheAsshole.

- **What are 'tips'?** We can definitely conclude that the tips submitted to both are quite similar and overlap in language and themes. Many of the tips submitted have to do with wanting to know things, purchases, work, and time.

*Limitations*
As with every dataset and project, there are some limitations we need to consider:

- **Population Bias**: Reddit tends to be more U.S. centric, so these themes and language may only be applicable to the U.S.. Additionally, we'll need to remember that U.S. Reddit users are a subset of the U.S. that is also not representative of the country's preferences and demographic.

- **Risk of Unreliable Data**: Our LPT posts are not explicitly 'not unethical', so we may have unethical posts in the LPT class anyway, or alternatively relatively ethical mods in the ULPT class. While the LPT subreddit is moderated to remove illegal and unethical tips, since the data is user-generated and defined, there is always a risk.

- **Time Limitations:** With more time, we could continue to keep testing with hyperparameter tuning and adding new stopwords to improve our classification as it could likely be improved with further testing. However, this may not give us more concrete conclusions as well.

- **Model Assumptions:** Our final model selected was a Naive Bayes model where the assumption is that our features are independent of one another, which cannot technically be true for our text features.

### Recommendations

Some other ways that we could approach this dataset and extend our investigation are:

- **Refine NLP:** We can try to build a custom set of stopwords based on the corpus and look into nouns, adjectives and verb analysis to see if that could improve our model.

- **Expand our datasets:** To look at other post variables via flairs, controversial posts, sample posts from across multiple years. We could also consider including the text of the comments within our dataset.

- **Investigate other trends:** For example, seeing if we can predict if a post is controversial or is likely to be popular, or likely to be awarded.
