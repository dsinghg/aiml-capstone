# aiml-capstone
Create a model to determine the sentiment/tone (positive, negative, neutral) by performing a sentiment analysis on given data, using Natural Language Processing (NLP) techniques. Social media currently plays a big roles in our lives, more so in younger generations. Social media has been blamed for spreading lies, hatred and other negative content, causing many people to go into depression and committing suicides. By determining the sentiment of the messages, the social media companies may be able to stop people from highjacking the platform for spreading hate and violence.

Objective: Predict the sentiment/tone (positive, negative) of the given data from X (formerly Twitter) feed.

The Data
The witter Sentiment Analysis Datasets are from Kaggle: train.csv - the training set test.csv - the test set
Data fields: ItemID - numeric id of twit Sentiment - sentiment (0 - negative, 1 - positive) SentimentText - text of the twit
Citation: Azhar Yebekenova. (2017). Twitter sentiment analysis. Kaggle. https://kaggle.com/competitions/twitter-sentiment-analysis2

Text preprocessing:
As a pre-processing step, performed stemming (also tried lemmatizing but didn't help) to normalize your text before classifying. Used both the CountVectorizer and TfidifVectorizer and options for stop words and max features to prepare the text data for the estimators.

Classification: After preparing the text data with stemming and lemmatizing techniques, used LogisticRegression, DecisionTreeClassifier, and MultinomialNB as classification algorithms for the data. Compared their performance in terms of accuracy and speed.

Finally, used the spaCy library to configure, traiain and evaluate the model. The table below shows the results of different types of clasisfication:


Logistic-CV:	  Fit-Time=769 sec; Score=0.7646; max_features: 100,000, stop_words: None	
Logistic-TFID:	Fit-Time=651 sec; Score=0.7697; max_features: 100,000, stop_words: None	
Decision Tree:	Fit-Time=773 sec; Score=0.6979; max_features: 100,000, stop_words: None	
Bayes:	        Fit-Time=272 sec; Score=0.7581; max_features: 100,000, stop_words: None	
spaCy:	        Fit-Time=142 sec; Score=0.7633; N/A	


Overall, none of the models received the score (Accuracy, F1) higher than 77%. The primary reason for this is that the tweets are usally classified in three categorioes (positive, negative, neutral). However, the given data only had nbinary values. The the "neutral" text is naturarualy be very subjective to human readers, so the model could not match it perfpectly.

