<img src="http://imgur.com/1ZcRyrc.png" style="float: left; margin: 1px; height: 1px"> 

# Data Science Capstone Project - A Twitter Sentiment Analysis of Donald Trump

#### The following was completed during the last four weeks of my Data Science Immersive course at General Assembly.

### Aim:
   
I am trying to predict which of the president's tweets contribute to s&p500 futures imminent price volatility, using a number of classification-based machine learning techniques.

---

### My Data:

   11,661 tweets spanning from 01/01/2016 to 23/10/2019 from which I deemed 150 tweets 'significant' towards moving the market as explained below.
 
 ---
 
### My Metrics:
   
price volatility, measured by:
   
   -> Taking the first 10 minutes as 'imminenet' after using 5 different thresholds, if any tweet is followed by a 0.15% increase or decrease in any of the 10 S&P 500 intra-minute price values, that tweet is deemed to have moved the market 'significantly'.
       
   -> This was after analysing the training set of tweets for 5 different thresholds, and by using Latent Semantc Analysis to reduce the number of themes within the training set as much as I could to train a more accurate model.
   
---        
 
### My Fidings:
   
   -> My aim was trying to increase the number of Trump's impactful tweets my model correctly predicted (accuracy score) and         my original findings were just above baseline. I then went back over the dataset I was using and found a number of             issues:
         
   1) Inconsistencies with time stamps 
   
   2) Spacy's NER not picking up uncapitalised entities
   
   3) Some of the text data including links and symbols that were adding noise to the dataset
   
   4) A number of retweets, which I decided to omit as a source of 'impactful' tweets
   
   5) Using LSA, and simple EDA on my original training set, the amount of themes there were across almost four years                of tweets from the President, importantly including the run-up to the election, made my model incredibly                      difficult to train. If this had been a multi-classification clustering problem (which in the future may be of                  interest) then I would have tried to sperate 'impactful' tweets pre-election and post-election. I wanted to                    keep the model simple, so I removed any 'significant' market moving tweets prior to 2018.
   
### Navigate your way through the repository:

