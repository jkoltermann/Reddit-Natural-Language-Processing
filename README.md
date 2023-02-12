# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web APIs & NLP


### Contents:
- [Problem Statement](#Problem-Statement)
- [Executive Summary](#Executive-Summary)
- [Data Dictionary](#Data-Dictionary)
- [Conclusions and Recommendations](#Conclusions-and-Recommendations)

### Problem Statement 

As an outside consultant to reddit, I have been approached to create a solution to utilize machine learning to evaluate whether a post was unintensionally posted to an incorrect subreddit. To initially show a proof of concept, I have chosen the subreddit's r/science and r/space to evaluate a binary prediction of whether an inputted post best-applies to one, or the other subreddit to hopefully contribute to a broader classification in the future.

### Executive Summary
My process of building this model followed the structure of my 3 notebook design:
- 'Data Pulling' Pulling data from the public REST API to collect enough data to train my model from both r/science and r/space
- 'Data Cleaning and Processing', which includes text handling of special characters such as Emoji's, text numbers, etc.
- 'Model Building,' where I created 3 models to compare which were most effective in this use case.
Through creating these models, I was able to understand the variables the language that drives the two subreddits. 

### Conclusions and Recommendations
To create a classifier that would stand to test, I wanted to ensure that I picked two subreddits that were similar enough to make this a challenge. The r/science and r/space classification challenge ended up being difficult, but nonetheless I view the results as a success.

After picking the subreddits to be used in our project, I built a class to be able to dynamically pull down data from the public REST API from the two subreddits, and ended up with more than enough data to create my model. Next I conducted some exploratory analysis on my data. I learned through this process that the words and language used across the subreddits were very similar, as the two subreddits shared every top ten word after data cleaning.    

The next step of the process was data cleaning. Many reddit posts are removed or deleted after initiallly posted, which leads to a great quantity of posts being removed from the dataset. Additionally there were duplicate posts that needed to be removed. Beyond initial deletions, there were other changes to be made to the text prior to vectorization. First of all, I had to answer the question about numbers. Knowing that there would be many distinctive numbers mentioned across the posts of both subreddits, I realized that they would have to be bucketed all together, or else there would be no information gain. I consequently made the same decision with emojis.

Last, I built a 3 models to predict which of two subreddits a post belongs to. 
1- Logistic Regression: Surprisingly, the best model that I built ended up being the first model that I created, the Logistic regression model. Achieving an r2 of ~88%, it performed well considering the similarities across the subreddits

2- KNN: this model overfit very clearly, with a 99% train score and 55% test score

3- Random Forest: Performed well, but slightly short of logistic regression at 87% on test data

Ultimately this project lead me to the following conclusions and suggestions

CONCLUSION 1: *Cross-posting will create an issue for classification*
When somebody takes a post from one subreddit, and posts it on another subreddit, it becomes part of the next dataset. This is something to pay attention to as it will make classification more difficult

CONCLUSION 2: *r/space and r/science are very simiar locations for posts on Reddit* 
sharing very many most used word variables

Suggestions from my Research:
- Leverage counts of other languages, as the proportions of languages used on the site will create other differentiating predictive value

- Leverage many models, and explore boosting for the broader usage across reddit

SOURCES:
- Reddit


[data]: https://git.generalassemb.ly/dsir-1031/project_1/wiki/Data
[deliverables]: https://git.generalassemb.ly/dsir-1031/project_1/wiki/Deliverables
[rubric]: https://git.generalassemb.ly/dsir-1031/project_1/wiki/Rubric
[presentation]: https://git.generalassemb.ly/dsir-1031/project_1/wiki/Presentation
[ps]: https://git.generalassemb.ly/dsir-1031/project_1/wiki/Problem-Statement
[background]: https://git.generalassemb.ly/dsir-1031/project_1/wiki/SAT-ACT-background
