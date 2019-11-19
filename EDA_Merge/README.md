### EDA & Merge

---

Sources: http://www.trumptwitterarchive.com/archive & Bloomberg min-by-min data

After using the twitter scraper here - and signing up for a twitter developer account, the dataset was incomplete and the text was poorly formatted. The text data from Trump Twitter Archive was more complete and therefore gave full context for the Vader sentiment analysis.

Before merging, I removed any timestamps where the volume of trades in the S&P futures market were 0 (very few), as to remove any distorted values when looking at percentage increase. I also removed any tweets starting with 'https...' as this displayed a photo that Trump tweeted. Given the time constraints, I was unable to analyse the text in these photos, and if given more time, would love to explore.


### Binary Explanatory Variable: Market Moving Tweet

How did I define whether a tweet was market moving? This was tricky, and was heavily investigated after how poor my original recall score was. There were so many different themese in my original training set; the Crooked Hilary and New Hampshire rallies of 2016 in the same training data as China's trade tariff commentary and Jerome Powell
