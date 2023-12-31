# reddit-advice

## Intro
This is a machine learning project that aims to try to better understand the nature of online career advice-giving communities like those on Reddit. We wanted to learn more about the popular topics being discussed in these communities and what factors drove engagement. This is important because career advice often involves high-stakes decision-making and learning about what drives these communities can help guide both employers and employees actions in the future. I worked on this project with Walker Azam and Wen Yi Aw as a part of my graduate studies.

## Methodology
This project required us to gather our data from [PRAW](https://praw.readthedocs.io/en/stable/), the Python Reddit API wrapper. We collected over 16,000 comments across 4,000 posts from a curated list of popular career advice-giving communities. From there, we identified some of the distinct categories of posts using LDA. We then created Naive Bayes and Logistic Regression models to try to predict if a comment would be considered "good" advice by the community, with the "upvote" score being the response variable. Some of the variables we explored as features were comment charactertistics (body length and stopword ratio), sentiment scores (TextBlob and VADER), and readability scores (SMOG and Gunning-Fog).

## Findings
Using trial-and-error, we found that the most distinct groupings appeared for LDA when we chose 10 as our number of topics. Standard workplace topics like skill building, legal and HR questions, and managing workload were found in the LDA groupings. However, there were also other distinct topics that involved questions about things like background checks and maternity leave, which highlights how some marginalized people might lean on these resources to find people in similar situations for help, which they might not have access to otherwise. Neither our Naive Bayes and Logistic Regression predictive models were successful at accurately predicting comments that the community would characterize as "good" advice.

## Future Work
Our work was limited by the fact that we only collected English posts and posts from Reddit. Other online career advice-giving communities might operate in different ways and posts written in English might also have distinct characteristics that don't hold true across other languages and cultures. We were also limited by the way that we decided to categorize "good" advice. Without the time and resources to manually code our comment data as "good" and "bad" advice, we were only able to use the community upvote score as a response variable for our predictive models. This could introduce problems, as "good" advice is not necessarily upvoted by the community, and things that aren't "good" advice might be upvoted by the community.

Our future work would start by addressing some of these limitations. We could hire or manually encode "good" advice comments in our dataset. We would also diversify our dataset by finding representative posts from forums other than Reddit and in languages other than English. Our future work would also look into actionable recommendations for employees and employers. Our research here found that marginalized people often turn to these communities seeking advice that they might not have access to locally, but this project didn't investigate ways to actually use this information to further help these people. Future work would address this.

## Files
* post_collection.ipynb: This notebook outlines the steps we took to collect the posts from Reddit that we used in our dataset
* comment_collection.ipynb: This notebook outlines the steps we took to extract the comments from the posts that we collected for our dataset
* comment_cleaning_EDA.ipynb: This notebook contains the cleaning steps that we applied to our data. It also contains the exploratory data analysis we conducted on our data
* LDA_topic_modeling.ipynb: This notebook contains the steps we took for our LDA topic modeling
* advice_models.ipynb: This notebook contains the steps we took to create our predictive Naive Bayes and Logistic Regression models to predict "good" advice
