# CopSense
A public dashboard backed with an elaborate sentiment analyzer parsing a Twitter stream to understand public temparaments about the Police in the United States. <br/>
Our #purpose is to help the public understand and constructively gain from and contribute to the public conversation about the Police Force in the United States. <br/>
## Summary
A significant portion of today's public conversation includes questions, opinions, and the implications of the police's role in society. CopSense aims to illustrate the big picture on the polarizing sentiments across the USA about the police force. We explored and utilized Natural Language Processing techniques like Sentiment Analysis, Opinion Mining, and novel ways to detect and capture the most relevant temparaments of the people on the subject of law enforcement. <br/>
A twitter Stream is periodically opened for each state and tweets are monitored for the presence of police related keywords. We then try to understand if the sentiments pertain to the Police force. We do this using Stanford CoreNLP's library to perform Parts of Speech(POS) and intersectionality analysis on the data. If we are satisfied that the tweet is an opinion on cops, we go ahead and perform sentiment analysis using Microsoft's Text-Analytics Cognitive Service. We then feed this to a MongoDB database which maintains a window of recent tweets, and latest example tweets for each category. <br/>
The dashboard is a minimalistic interface where you can view a choropleth map of the USA and sentiments for every state where a higher value corresponds to a more positive outlook. 
Our website seamlessly provides a one-stop solution to more insights on the broader geographical region of the USA. Sample tweets are displayed on the website for each category - positive, negative, neutral - sentiments pertaining to the subject of the police force. This way, people can easily find the trends <br/>
 Our application hopefully provides a #fast and #easy way to have a transparent, intelligent, and #straightforward dissemination of crucial information; to pop the bubble we may be surrounded by, and build a more informed and responsible community. 

## Challenges
This was the first time for all of us to be working with NLP. Understanding concepts of Linguistics was something new and eye-opening. <br/>
Microsoft's Azure Sentiment Analysis can give a sentiment score for any type of sentence. Many tweets about the police tend to be neutral but skewed to positive or negative from a plain language level.  We focused on trying our best to consider sentiments with the police as the subject. Our novelty includes Parts of Speech(POS) analysis and keyword dependency. We also tried Azure's Opinion Mining service to improve accuracy but experiments showed that most tweets are very short and unstructured to apply this technology. We referred the methods used in the study here https://www.ncjrs.gov/pdffiles1/nij/grants/205619.pdf to guide us in building a more intelligent solution. <br/>

Another Major challenge was getting location specific information on these sentiments. Most Tweets do not contain a geotag. For this we basically searched by each state with bounding boxes/circular search regions, to analyze location specific tweets. A following challenge was that we could not filter tweepy streams with more both location and keyword. For this sake, we implemented a loop we basically spends time analyzing tweets from each state, checks if its cop related, and analyzes that then. <br/>

We thought of trying to train a model to help classify better but we did not have enough data and the Twitter API rate limits were not big enough for the purpose. We also did not want to break Twitter's policy by attempting to using a Twitter scraping library. 

## What's next
Improving on the NLP architecture, studying more about ongoing research in the same sector and try to implement additional techniques. 
