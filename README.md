# Data Science Capstone Project - A Twitter Sentiment Analysis of Donald Trump

The following was completed during the last four weeks of my Data Science Immersive course at General Assembly.

Aim:
   
   I am trying to predict which of the president's tweets contribute to s&p500 futures imminent price volatility, using a number of classification-based machine learning techniques.
 
My Data:
   11,661 tweets spanning from 01/01/2016 to 23/10/2019 from which I deemed 150 tweets 'significant' towards moving the market as explained below.
 
My Metrics:
   
   -> price volatility, measured by:
   
       -> Taking the first 10 minutes as 'imminenet' after using 5 different thresholds, if any tweet is followed by a 0.15% increase or decrease in any of the 10 S&P 500 intra-minute price values, that tweet is deemed to have moved the market 'significantly'.
       
       -> This was after analysing the training set of tweets for 5 different thresholds, and by using Latent Semantc Analysis to reduce the number of themes within the training set as much as I could to train a more accurate model.
        
 
   - My Fidings:
   
         -> My aim was trying to increase the number of Trump's impactful tweets my model correctly predicted (accuracy score) and my original findings were just above baseline. I then went back over the dataset I was using and found a number of issues:
         
            -> Inconsistencies with time stamps 
            -> Spacy's NER not picking up uncapitalised entities
            -> Some of the text data including links and symbols that were adding noise to the dataset
            -> A number of retweets, which I decided to omit as a source of 'impactful' tweets
            -> Using LSA, and simple EDA on my original training set, the amount of themes there were across almost four years                of tweets from the President, importantly including the run-up to the election, made my model incredibly                      difficult to train. If this had been a multi-classification clustering problem (which in the future may be of                  interest) then I would have tried to sperate 'impactful' tweets pre-election and post-election. I wanted to                    keep the model simple, so I removed any 'significant' market moving tweets prior to 2018.
          -> 
   
   -> TBC
   
   
   
   - What risks/limitations/assumptions affect these findings?
   
   -> Generalisation
   
       -> Given the data was gathered from 2016, many of the tweets driving 'significant' volatility in price were politically specific to the 2016 election race. This included candidates such as Ted Cruz and Jeb Bush becoming key men in the race against Trump becoming President. To potentially avoid this, I attempted Latent Semantic Analysis to reduce the number of features in the count vectorized matrix, by grouping words into components. By doing so, I could theoretically categorize words into specific themes associated with cuasing volatile price movements; presidential race, federal reserve, economic (specifically monetary policy,  currencies (USD focus) and trade. I could steer away from specific names, and try to spot the presence of other terms that would still be there if there were other people up against Trump in the 2020 preisdential race, or another country Trump picked to have a trade war. I could also perform this task using NER through spacy, where I would look for certain entities in a sentence; a person, geographical place, economic term etc. and by generalising, prevent any overfitting from my model. 
       
       
    -> Reverse Causality
    
        -> Does the market move Trump? He has been subject to a lot of accusations on currency manipulation, as well as being prompted to tweet more contentiously as the markets have become more volatile. This issue of reverse causality, could be a problem, with the Presidential election coming up next year, and the trade ralationship with China hitting an all-time low, it is difficult to tell whether he has ridden the wave of volatility, or has directly contributed to it, particulraly in the recent months
        
        
     -> Sentiment Analysis for Trump
     
        -> For Donald Trump, his inconsistencies in level of sarcasm, as well as inconsistent use of language in a variety of different contexts, make it very difficult to find the best sentiment library to truly reflect the level of negativity or positivity in his tweets. Moreover, his use of certain words like 'growth' in an economic context, and therefore a context of this hypothesis, is misinterpreted by many sentiment libraries, with vader sentment giving it an extremely mild score. Maybe in years to come, financial/economically important terms will be given a greater weight whether in existing sentiment libraries or new ones. I did experiemnt with one financial sentiment library, however, it was missing a fair few words.
   

    -> Inability to capture reaction
    
        -> Given the very short timeframe used to measure the significance of the impact, we are unable to tell the compounded impact of many of the tweets with regards to reactions from other very influential twitter accounts. Running a sentiment analysis on giant news outlets and other important twitter figures' reactions may have provided us with a more accurate insight, as the language used would be generally less sarcastic more consistent.
        


2. Walk through your model step by step, starting with EDA



   - What are your variables of interest?
   
   
   -> y = significant price change
   
   -> x = vader compound score, dummy variables for hour, dummy variables for key words for tweets from 2016 -> Aug 2018
   
   - What outliers did you remove?
   
   
   -> I trialled removing half of my dependant variable data and only collecting tweets from 2018. This was because of the variety of the topics Trump tweets about, and because my hypothesis of trade and monetary policy being the overriding themes causing a significant price change.
   
   - What types of data imputation did you perform?
   
   -> n/a

3. Summarize your statistical analysis, including:


   - model selection
   
    -- KNNeighbours
    
    
    -- Multinomial Naïve Bayes
    
    
    -- Random Forest Classifier


    -- Logistic Regression with L1 and L2 penalty


    -- SVM & Linear SVM Models


        -> All of which have a selction of different parameters that have been tuned individually, through a gridsearch function. Prior to that, I tried LSA (Latent Semantic Analysis) to perform dimensionality redction on my tfidf to categorise trump’s tweets to either subset on relevant tweets or introduce dummy variables. Unfortunately, the number of tweets and inconsistency of tweeting patterns meant LSA struggled to capture any themes other than those tweets that had no significant impact on the S&P500

   
   - implementation
   
   -> See the function highlighted in 'Sentiment Analysis' under the 'implementation' section
   
   - evaluation (finish tomorrow)


   -> My original scores needed some severe improvement - I hadn't


   - inference (finish tomorrow)


   ->  


4. Clearly document and label each section
   - Logically organize your information in a persuasive, informative manner
   - Include notebook headers and subheaders, as well as clearly formatted markdown for all written components
   - Include graphs/plots/visualizations with clear labels
   - Comment and explain the purpose of each major section/subsection of your code
