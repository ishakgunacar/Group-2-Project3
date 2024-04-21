
# Project Title: Using Retrieval Augmented Generation to Create a Movie Recommendation System
## Group 2
(Edilberto Vinas, Abdullah Ibrahim, Isaac Gunacar, Nick Santos)

Presentation: 

Group 2 notebook: 

## Works Cited
1. Rotten Tomatoes - EDA (Expoloratory Data Analysis) - https://www.kaggle.com/code/stefanoleone992/rotten-tomatoes-eda/input

## Sections Included
Section 1: Overview<br>
Section 2: Scope<br>
Section 3: Data Collection<br>
Section 4: Data Cleaning<br>
Section 5: Approach and Methodology<br>
Section 6: Data Optimization<br>
Section 7: Conclusion<br>
Section 8: Future Considerations<br>

# Section 1: Overview
The objective of our project was to create a sentiment-based Movie Recommendation app that utilized the power of OpenAI to suggest films and tv shows based on an arbitrary statement. For example, if a user were to input the statement, "I feel like watching a crime drama with a police officer as the main character," the app would ideally be able to process that sentiment and recommend a list of films and/or shows baesd on it.

The problem we were trying to alleviate was one where the user, although probably already utilizing different "watch lists" on several different streaming services, would be searching for something new that they had never heard of based on a notion (as opposed to searching by genre). Ideally our app would open them up to lesser-known prodcutions or even international productions of a similar ilk. Basically it would be a free-association approach to searching for something to watch.

Another consideration we had was for the user that didn't know what they wanted to watch and didn't want to waste time looking through their various "watch lists". This was a logistical concern for the user that may only have thrity minutes to an hour to relax at night before going to bed.

# Section 2: Scope
The intention of our project was to create an app that the user could utilize to get a movie recommendaiton by inputting a general sentiment. Ideally this would have been the base for software that would be made available to the general public on an online browser and as a cellular OS app. 

Although the group fell short of making a working model, we are still confident that we have created a solid proof of concept for how the model would work.

Once we trained the model on the current data set (which only included films up to 2013) we could add up-to-date data with current films, as well as data for films from foreign markets.

# Section 3: Data Collection
The data set for our project was large enough to feed our model but was a bit outdated (ending with films from 2013). We gathered the data from a Kaggle project [1] that was sourced from the website Rotten Tomatoes. The data included 2 .csv files with over a million rows of entries.

One .csv file included 21 columns including technical details like, 'movie title,' 'content rating,' 'directors,' 'actors,' 'production company,' and 'review content' amongst others. The second .csv file included arbitrary informaiton about the films including columns such as, 'genre', 'tagline', and 'keywords.' Many of these categories were considered for the sentiment analysis training.

# Section 4: Data Cleaning
Luckily, because both data sets were collected from Rotten Tomatoes they included a column named, 'Rotten Tomatoes link,' which acted as an identifier in their database for that film. This made it easy to merge the two sets using, 'Rotten Tomatoes Link' as the index. After merging the data we dropped 13 columns that the group deemed unnecessary for our purposes. Most of these columns related to information about the reviews including 'authors' and 'critic names' and since we were only going to utilize the reviews for sentiment analysis, it made sense to lose that info.

# Section 5: Approach and Methodology
Early on in the process the group decided to create two competing models for the recommendation system, a BERT based model and a RAG (Retrieval Augmented Generation) model. The reason for this was to create a BERT model, being the more traditional neural network model for movie recommendation, to fall back on in case the RAG model didn't work. As a group, we were excited to create a RAG model so that we could utilize the power of OpenAI and enrich the sentiment analysis portion of our model. 



# Section 6: Data Optimization

# Section 7: Conclusion

# Section 8: Future Considerations