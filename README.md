Author : pmehta16@uncc.edu

# Topic-Modeling using LDA Model
Topic Modelling to segregate news story data to different topics using Gensim, NLTK, Spacy.


Topic modelling as the name suggests, it is a process to automatically identify topics present in a text object and to derive hidden patterns exhibited by a text corpus. Thus, assisting better decision making. Topic Modelling is different from rule-based text mining approaches that use regular expressions or dictionary-based keyword searching techniques. It is an unsupervised approach used for finding and observing the bunch of words (called “topics”) in large clusters of texts. Topics can be defined as “a repeating pattern of co-occurring terms in a corpus”. 
Dataset under consideration for this project consists of News Stories and our task is to assign topics to those stories. For this project I will be using an LDA model to perform the topic modeling. 


Task consist of :
1. <b>Loading the dataset</b>
Link to dataset : Dataset: https://www.kaggle.com/datasets/akash14/news-category-dataset?select=Data_Train.csv

About Dataset: Size of training set: 7,628 records Size of test set: 2,748 records. 
FEATURES: STORY: A part of the main content of the article to be published as a piece of news. 
SECTION: The genre/category the STORY falls in. There are four distinct sections where each story may fall in to. 
The Sections are labelled as follows : Politics: 0 Technology: 1 Entertainment: 2 Business: 3

2. <b>Data Preprocessing</b> <br>
* Tokenization: Split the text into sentences and the sentences into words. Lowercase the words and remove punctuation.
* Words that have fewer than 3 characters are removed.
* All stopwords are removed.
* Words are lemmatized - words in third person are changed to first person and verbs in past and future tenses are changed into present.
* Words are stemmed - words are reduced to their root form.

3. <b>Bag of Words on the dataset</b><br>
Created a dictionary from the processed data, containing the number of times a word appears in the training set. I have used 
genism.coropa.Dictionary() for this. Followed by some more filtering out of data.
Steps Involved: 

* Create dictionary from words present in the entire training data.
* Remove very rare and very common words from the dictionary under consideration.
* Convert document (a list of words) into the bag-of-words format = list of (token_id, token_count) 2-tuples. Each word is assumed to be a tokenized and normalized string.

4. <b>Topic Modelling using Gensim's LDA</b><br>
LDA generalizes the way the documents are generated and this modelling assumption leads to better topics. We will be using num_topics = 4 for or usecase since we have four major categories of data in our dataset. 