# Project 3: Suicide Watch

#### Problem Statement

To predict the language used by individuals who are suicidal versus depressed by webscraping data from subreddits Suicide Watch and depression using Multinomial Naive Bayes and Logistic Regression. The subreddits allow for free expression of emotions, which helps us to study the difference between those who are depressed and suicidal in the most honest form. The information can help counsellors and psychologists in schools to classify children and adolescents into 'high-alert' cases if they are predicted to be suicidal so that more attention can be given to them.

Success will be evaluated by accuracy, precision, recall and f1-score. For this problem, recall is the most important metric because we want to identify as many possible cases of suicidal individuals as possible. The cost of not identifying them is a matter of life and death and it also does not hurt to be on high alert for those who were wrongly identified to be suicidal.

---

#### Executive Summary

The number of suicides in Singapore rose 10 per cent last year, with suicides among boys aged 10 to 19 at a record high, according to the Samaritans of Singapore (SOS). Against this backdrop, we investigate how we can better identify potential cases of suicide by looking at the words used by these individuals.

The subreddits Suicide Watch and depression will be used to help in the study of the language used. They offer firsthand accounts into the thought processes and emotional experiences of these individuals. The posts are cleaned by removing stopwords and pins by moderators and subsequently, the Multinomial Naive Bayes, Logistic Regression and K-nearest Neighbours models were run with Count and Tfidf Vectorizer. The better models - Multinomial Naive Bayes and Logistic Regression with Tfidf Vectorizer were then optimised before selecting the best model as the production model. 

The model that was found to be of the highest recall/ sensitivity (81%) was Tfidf Vectorizer with Multinomial Naive Bayes. This means that 81% of suicidal cases were identified correctly. It will be helpful for psychologists and counsellors in a school setting to be more sensitive to such cases and be on high alert to prevent loss of lives.

---

#### Datasets

Subreddits Suicide Watch and Depression were scraped from the following links:
* https://www.reddit.com/r/SuicideWatch/
* https://www.reddit.com/r/depression/


#### Data Cleaning

1. Imputed missing values in the posts with empty strings.
2. Combined title of posts with posts to capture all the information from users of the subreddits.
3. Removed pins from moderators.
4. Dropped duplicates, which are mainly empty posts, even after combining with titles.

---

#### Pre-processing

1. Concatenated dataframe from the two subreddits and created a binary column for the target variable - 1 for suicide, 0 for depression.
2. Tokenized, lowercased, and removed stopwords before lemmatizing and stemming.

---

#### Exploratory Visualisations

1. Barplots to show word counts in the subreddits. 
2. Venn Diagrams to show overlapping words, some of which include 'anymore', 'going', 'thing', 'help', 'time', 'know', 'feel', 'think','want','hear', 'friend'.
3. Wordclouds to visualise top 500 words in each subreddit.


#### Modelling

1. First Run:
* Lemmatized Tfidf Vectorizer with Multinomial Naive Bayes
* Lemmatized Tfidf Vectorizer with Scaled Logistic Regression
* Lemmatized Tfidf Vectorizer with Scaled K-nearest Neighbours
* Lemmatized Count Vectorizer with Multinomial Naive Bayes
* Lemmatized Count Vectorizer with Scaled Logistic Regression
* Lemmatized Count Vectorizer with Scaled K-nearest Neighbours
* Stemmed Tfidf Vectorizer with Multinomial Naive Bayes
* Stemmed Tfidf Vectorizer with Scaled Logistic Regression
* Stemmed Tfidf Vectorizer with Scaled K-nearest Neighbours
* Stemmed Count Vectorizer with Multinomial Naive Bayes
* Stemmed Count Vectorizer with Scaled Logistic Regression
* Stemmed Count Vectorizer with Scaled K-nearest Neighbours

2. Hyperparameter Search in the Second Run:
* Lemmatized Tfidf Vectorizer with Multinomial Naive Bayes
* Lemmatized Tfidf Vectorizer with Scaled Logistic Regression

3. Model Selection
* Lemmatized Tfidf Vectorizer with Multinomial Naive Bayes with the following parameters:
	* 'mnb__alpha': 1.4000000000000004,
	* 'tf__max_df': 0.45
	* 'tf__max_features': 3000
	* 'tf__min_df': 2
	* 'tf__stop_words': 'english'
	* 'tf__ngram_range': (1,1)

The models at each step were selected based on accuracy and recall. The accuracy of the models were compared against the baseline accuracy of 0.51. K-Nearest Neighbours models barely beat the baseline accuracy and as such, was eliminated after the first run. 
The final model picked was mainly based a higher recall of 0.81, compared to 0.79 in the first run of the same model. Recall is the main metric used because of its importance in the problem we are trying to solve. 

We want to maximise recall because the cost of predicting a false negative means the loss of a life. So we need it to be as high as possible, even if only marginally. 

---

#### Conclusions and Recommendations

**Production Model**

As mentioned above, the production model would be **Tfidf Vectorization with Multinomial Naive Bayes**, which gave a rather high recall rate of 81% - the fraction of the total amount of suicidal instances that were actually retrieved by the model. 

**Limitations**

It is important to recognise the limitations of using posts or written notes of any kind to raise red flags about potential suicide cases. The written notes cannot capture the tone in which it is written and cannot capture a person's behavioural changes which usually serves as a telltale sign. Thus, while it can be useful as a form of first screening, there is also a need to examine behavioural changes in relationships, eating and sleeping habits, etc.

**Further Expansion**

The two subreddits used are depression and suicide, which means that it could fail to classify those who are suicidal and at the same time, face depression correctly. The project could benefit from widening the scope of data collection to include people who may be suicidal due to other conditions like trauma and anxiety. 

Besides, higher data granularity, such as location, age, and gender would probably help in classifying because people from different regions, genders and age would express themselves differently. This will help identify the nuances and classify the categories better. The project can also be generalised to include more stakeholders such as parents, the community and teachers to help identify suicidal patients early on. It will be particularly helpful for those who do not have background in the field, i.e. those who are not trained psychologists and psychiatrists. 