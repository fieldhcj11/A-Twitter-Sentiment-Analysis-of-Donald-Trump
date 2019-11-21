# Merge, EDA & NLP

---

Sources: http://www.trumptwitterarchive.com/archive & Bloomberg min-by-min data

After using the twitter scraper here - and signing up for a twitter developer account, the dataset was incomplete and the text was poorly formatted. The text data from Trump Twitter Archive was more complete and therefore gave full context for the Vader sentiment analysis.

Before merging, I removed any timestamps where the volume of trades in the S&P futures market were 0 (very few), as to remove any distorted values when looking at percentage increase. I also removed any tweets starting with 'https...' as this displayed a photo that Trump tweeted. Given the time constraints, I was unable to analyse the text in these photos, and if given more time, would love to explore.


### Further EDA

This included looking at volume, sustained volume, average volume in the hour of that tweet both throughout the dataset and that hour. None of these metrics were remotely correlated to the dependant variable. 

Furthermore, after looking at the distribution of 'significant' tweets by hour of the day, I decided to include hour of the day as a binary, explanatory variable and use further down the line potentially after checking for correlative power.

I then looked into keywords such as 'China' and 'Trade' to check if I had the correct timeframe (originally 5 minutes) to caputre the full effect of the price 'shock' after the President tweeted. It showed that much of the price movement happened between 5 and 10 minutes, hence factoring that into the threshold for 'significant' tweets.
