
# Project Title: Using Retrieval Augmented Generation to Create a Movie Recommendation System
## Group 2
(Edilberto Vinas, Abdullah Ibrahim, Isaac Gunacar, Nick Santos)

Presentation: https://www.canva.com/design/DAGDFgxYHxA/QQoTWpmUaC_lhItfts0-aQ/edit

Group 2 notebook: https://github.com/ishakgunacar/Group-2-Project3/blob/main/Movies.ipynb

## Works Cited
1. Rotten Tomatoes - EDA (Expoloratory Data Analysis) - https://www.kaggle.com/code/stefanoleone992/rotten-tomatoes-eda/input

## Sections Included
Section 1: Overview<br>
Section 2: Scope<br>
Section 3: Data Collection<br>
Section 4: Data Cleaning<br>
Section 5: Approach and Methodology<br>
Section 6: Conclusion<br>
Section 7: Future Considerations<br>

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
Early on in the process the group decided to create two competing models for the recommendation system, a BERT based model and a RAG (Retrieval Augmented Generation) model. The reason for this was to create a BERT model, being the more traditional neural network model for movie recommendation, to fall back on in case the RAG model didn't work. As a group, we were excited to create a RAG model so that could utilize the power of OpenAI and enrich the sentiment analysis portion. Ironically it was the BERT model that ended up not working for us in the end.

When embarking on the vectorization process we quickly realized that the data set was too large to vectorize and embed. The reason was because we wanted to use the column, "review_content" which contained an entire published review of the film for sentiment analysis. Given that some of these reviews were up to a 1,000 words, the field was just too large and would have taken too long for us to use a BERT toeknizer and vectorize it for that model.

Turning our attention instead to completing the RAG model there were still many hurdles to cross. First, the entire group was inexperienced with creating a RAG model as it was a topic we broached in the "Emerging Topics" week of our course. So we didn't have as much hands-on exerience with the code as we didn't even have a full class on the subject. Second, the vectorization for the model was still a problem even when we decided to drop the "review_content" field. The data had to be vectorized into the proper format and there was a time restraint (due to the limit of API requests per day) when upserting them into Pinecone. There were also some technical limitations with our local machines.

Upon creting our model and wrapping it with Gradio we still couldn't get our sentiment analysis to work. In the final model we ended up scrapping the sentiment analysis, even though it was a large part of our ideation phase when coming up with this project. In the end we had to choose between a working model and a non-working proof of concept.

# Section 6: Conclusion
Upon completing this project we realized that although ambitious, our initial idea to create a sentiment-based film recommender would likely take much longer than the alloted time we had for this project. However, the group feels confident that given enough time, trouble shooting and experience it would be possible to create a sentiment-based movie recommender.

# Section 7: Future Considerations
There are several ideas we would like to push as a group should we continue working on this project. One, we must find a sentiment analysis model that works for us, seeing as how this was the feature that excited us most about creating a movie recommendation system. Two, we would have liked to update the data set to include up-to-date films then train the model on all the data.