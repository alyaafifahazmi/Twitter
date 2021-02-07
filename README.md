# Tweets Analysis: Project Overview
Using Jupyter Notebook

1. Scraped tweets and its details from live streaming using chosen keyword or specific tweet handle.
2. Cleaned the tweets for anlyzing purpose. 
3. Get the most languages used for the tweets.
4. Top words used from tweets.
5. Top people mentioned from tweets.
6. Sentiment analysis of tweets. 
7. Wordcloud just for fun. 

## To get to access token, access token secret, consumer key and consumer secret

First, apply to be a developer to get API key and API token.
link: (https://developer.twitter.com/en)

1. Click on 'Apply' on top right.
2. Click on 'Apply for a developer account'.
3. Sign in with your twitter account.
4. Follow the steps shown.
5. In writing your 'How you plan to use Twitter data and/or APIs, please save what you have written in all the process as they will ask again in the coming steps. 
6. You can check out 'Use cases' to get some ideas. 
7. It will take multiple days to get approved and you may need to revised your description in step 5. 

## Extracting Streaming Tweets

Tweets extraction are done following [twitter_streaming_analysis.ipynb](https://github.com/alyaafifahazmi/twitter/blob/Introduction/mod_twitter_streaming)

Kindly edit they ***keyword*** of your selection and ***file name*** in the file. 

When in Jupyter Notebook, run the mod_twitter_streaming file by typing ->***%run mod_twitter_streaming***

This will run the file and streaming tweets will be shown while running until it has reached its limit. 

You can rerun it back again to get more tweets and the tweets will be added to the exciting file. 


## Twitter Scrapping
By scraping the details from twitter, you will get these info below: 
 *  created_at                 
 *  id                             
 *  id_str                               
 *  ***text***                          
 *  display_text_range         
 *  source                     
 *  truncated                 
 *  in_reply_to_status_id      
 *  in_reply_to_status_id_str  
 *  in_reply_to_user_id        
 *  in_reply_to_user_id_str    
 *  in_reply_to_screen_name          
 *  user                
 *  geo                   
 *  coordinates            
 *  place              
 *  contributors           
 *  is_quote_status           
 *  extended_tweet           
 *  quote_count               
 *  reply_count               
 *  retweet_count        
 *  favorite_count          
 *  entities                  
 *  favorited                
 *  retweeted              
 *  filter_level             
 *  ***lang***                 
 *  timestamp_ms               
 *  retweeted_status           
 *  quoted_status_id           
 *  quoted_status_id_str       
 *  quoted_status                         
 *  quoted_status_permalink                
 *  possibly_sensitive                   
 *  extended_entities
	
## Languages of Scrapped Tweets

I used ***groupby*** to group the tweets following languages used. 

![languages used](https://github.com/alyaafifahazmi/twitter/blob/Introduction/Languages.png)

From the graph, we can see that most used languages are english (en), indonesian (in) and japenese (ja).

*und is undefined

## Data Cleaning

After getting the data, I cleaned data using ***regular expression (re)*** to give more accurate sentiment analysis and lemmetize the words to get more accuarate used words. 

* Removed mentions/@
* Removed RT words
* Removed hyperlink
* Lowercase all the tweets
* Extra steps to make sure there are only alphanumeric and space only
* Combined each tweets into a list named 'all_sentences'
* Separated each words and put them in a list called 'lines'
* Removed all the space between the words in the 'list' and named the new list as 'lines2'
* Lemmetized all the words and put them in a list called 'stem'
* Removed english stopwords and pu them in a list called 'stem2'

Now each words are cleaned and lemmetized, and ready to show some pattern!

## Top Words Used

I got the counts of each words and sort them descendingly. 

Removed words that I find irrelevant such as 'de' and 'amp'. 

![Top words](https://github.com/alyaafifahazmi/twitter/blob/Introduction/top%20words.png)

## Top People Mentioned

Using ***spacy*** to categorize the words following its cluster as 'person'.

![Top people mentioned](https://github.com/alyaafifahazmi/twitter/blob/Introduction/Top%20people%20mentioned.png)

However, this analysis seems irrelevant due to many languages used other than english. 

This spacy's language I have used was for english language. 

Hence, this analysis is irrelevant/not needed or more languages should be added to my analysis. 


## Sentiment Analysis

I have added new columns at end of my dataframe: 
* Subjectivity: Strength of the polarity
* Polarity: Magnitude of the polarity (-1 to 1)
* Analysis: Categorized the polarity to Negative, Neutral and Positive

![Scattered plot](https://github.com/alyaafifahazmi/twitter/blob/Introduction/Sentiment%20Analysis%20scattered%20graph.png)

We can see from this scattered graph that most tweets is Neutral with 0 polarity. 

![Bar plot](https://github.com/alyaafifahazmi/twitter/blob/Introduction/Sentiment%20Analysis%20bar%20graph.png)

Proven with this bar plot graph that more than 400 tweets are tweeted with neutral polarity and less than 200 tweets have a negative polarity. 

## Word Clouds

This is just for fun, so that I can refer to it in the future. 

![Word cloud](https://github.com/alyaafifahazmi/twitter/blob/Introduction/Word%20Cloud.png)

The bigger words shows the frequency of the words have been used. 



