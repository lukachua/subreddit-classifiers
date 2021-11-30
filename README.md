

### Project 3: Subreddit Classifier - r/CryptoCurrency and r/Investing ###

## Problem Statement

As a new investment company which has 2 main trading desks - one for traditional securities and another for cryptocurrency, we find Reddit to be a potential source of information on trading news. The speculative discussions spanning a wide range of topics are something we would like to monitor on a daily basis. [*r/investing*](https://www.reddit.com/r/investing/) and [*r/CryptoCurrency*](https://www.reddit.com/r/cryptocurrency/), in particular, are especially of interest to our company. 

However, because we are a small company with limited manpower to spare, we are looking into help in the form of a classifier model to accurately sort the posts accurately so that our employees in the relevant department can quicky access the right information for their needs.

---

## Background

Reddit is a social news aggregation, web content rating, and discussion website that has been featured in a number of headlines recently due to the unexpected role it played in the prices of stocks. From the now-confirmed scam of Squid Game coin to the Gamestop saga on r/wallstreetbets, traders who tended to scrutinize traditional news for information have started turning to Reddit as well as a source of information ([*Source*](https://markets.businessinsider.com/news/stocks/reddit-stocks-10-most-discussed-tesla-gamestop-wallstreetbets-november-2-2021-11)). Due to the nature of Reddit as an online discussion platform, crytocurrency is also a popular topic there with r/cryptocurrency having a total of 3.8 million members in the lively community ([*Source*](https://www.reddit.com/r/cryptocurrency/)).

Using the ShiftPush API, our team collected about 2000 posts from the subreddits of cryptocurrency and investing, and will be building a suitable Natural Language Processing classifier model to cater to the needs of the company. We have also narrowed down the training model types to: Logisitic Regression and Naive Bayes. This report will walk the reader through the process of setting up the classifier model for the company.

---

|Feature|Type|Dataset|Description|
|---|---|---|---|
|title|*str*|crypto_df|The words found in the post title in r/CryptoCurrency|
|title|*str*|invest_df|The words found in the post title in r/investing|
|selftext|*str*|crypto_df|The words found in the post body in r/CryptoCurrency|
|selftext|*str*|invest_df|The words found in the post body in r/investing|
|all_text|*str*|combined_df|The words found both the title and post body in the combined r/CryptoCurrency and /investing dataframe|
|tok_lemma_all_text|*str*|clean_df| The tokenized and lemmatized words from combined_df|

---

## Summary of analysis

The naive Bayes models both performed better than the logistic Regression with TF-IVF Vectorizer in terms of the True Positive Rate, with the higher of the two models being the naive Bayes with Count Vectorizer. This model performed brilliantly with 97.3% True Positive Rate. Its test score is also adequate at 93.1%.

The TF-IDF Vectorizer has a more positive impact than the Count Vectorizer on the Logistic Regression model. The True Positive Rate and accuracy (test score) are higher at 95.6% and 94.3% respectively.

---

## Conclusion

We have chosen to go with the naive Bayes classifier model with Count Vectorizer for our company. True Positive Rate was prioritised beause of it is more crucial that our colleagues at both the traditional securities and crpytocurrency desks get a higher percentage of information relevant to their trading desks.