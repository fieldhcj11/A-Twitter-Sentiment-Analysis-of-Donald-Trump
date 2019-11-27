# LSA for Dependant Variable Threshold

---

### Binary Explanatory Variable: Market Moving Tweet

How did I define whether a tweet was market moving? This was tricky, and was heavily investigated after how poor my original recall score was. There were so many different themese in my original training set; the Crooked Hilary and New Hampshire rallies of 2016 in the same training data as China's trade tariff commentary and complaints surrounding Jerome Powell's Fed decisions (or lack of).

At this point, I took some advice off the JP Morgan Trump 'Volfefe' study refernced [here](https://www.bloomberg.com/news/articles/2019-09-09/jpmorgan-creates-volfefe-index-to-track-trump-tweet-impact)

There were two reasons for this:
  1) Original results - see here(link to powerpoint) page 17 for original results
  2) The figures below and the amount of explained variance in the first 100 words that was concerning.

![Original](https://github.com/fieldhcj11/A-Twitter-Sentiment-Analysis-of-Donald-Trump/blob/master/lsa/Screenshot%202019-11-27%20at%2014.41.44.png)

![Updated](link-to-image)

Eventually, I set the threshold based on a training set of 120 tweets, where the first 100 words explained 80% of the significant market tweets, rather than X.


### LSA and Truncated SVD 

To provide some rationale behind reducing the number of observations in my training and test sets, I looked into using LSA and truncated svd to measure the explained variance of the most influential 100 words throughout my various different y-sets, based on different thresholds.

This was firstly using a TFIDF matrix of the corpus of 'significant tweets'. I used a tfidf matrix to value the rarity of words in all his tweets as well as the overall frequency with which they appear. After this, I used Truncated SVD for dimensionality reduction, resulting in the diminishing the original matrix by k-features to its most important parts (or words) to solve my prediction problem.

I chose the value of K based on sacrificing not sacrificing too much of the original data whilst leaving a good benchmark to compare.

