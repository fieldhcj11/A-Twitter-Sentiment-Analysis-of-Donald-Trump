# A-Twitter-Sentiment-Analysis-of-Donald-Trump

### Use for Readme



1. Begin with an executive summary:


   - What is your goal?
   
   To solve the question 'To what extent do the president's tweets contribute to s&p500 futures imminent price volatility?' using a wealth of regression-based models to eventually refine into a predictive tool for future tweets.
   
   - What are your metrics?
   
   
   -> price volatility, measured by:
   
       -> the difference between the open and close s&p prices each minute after  Trump tweets, for 5 mins
       -> the difference between the open and high s&p prices for each minute after Trump tweets, for 5 mins
      
      
   -> Sustained volume volatility,measured by:
       
       -> whether the average volume 20 mins after the tweet is greater than the average volume of trades that hour (check)
       
      
   -> from 'price volatility', significant change, quantified by a 0.1% or greater change in either the minimum or maximum of both price volatility measures
   
   
 
   - What were your findings?
   
   
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
