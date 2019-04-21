# NLP-Summary-Evaluation
The task is to design classiﬁers to evaluate summary quality based on its non-redundancy and ﬂuency. 

Q4.1.1
------Packages and functions------
Import all the packages here and run all the defined functions.

data_preprocess: remove punctuation, multiple spaces and stopwords. Can also choose not to remove stopwords. The parameter is True by default.

	max_rep_uni: Get the maximun counts of unigrams.

	max_rep_bi: Get the maximun counts of bigrams.

	word2vec_embedding: Get the average vector of each sentence.

	max_sim: Get the maximum pairwise cosine similiarity of each summary.

------Data Preprocess and Feature Generation------

Put the Train_Data and Test_Data file under work directory. Read the files.

Unzip the word2vec under work directory. Load the file into python.

Process the training data and test data to get the features using the functions defined above.
		Get the cleaned new summary without punctuation and stopwords for bigram count and unigram count features. 
		Use the original summary for sentence tokenize to get the similarity.

------Modeling------

Train linear regression model to predict the non-redundency. 

Get the MSE and pearson correlation. 

------------------------------------------------

Q4.1.2

------Functions------
3 functions defined her to generate new features.

	count_stw: Count the number of stopwords in a list of unigrams.

	num_stw: Get the total number(count) of stopwords.

	num_uni: Get the count of distinct words.

------Generate features 1------
Generate new summary column without punctuation but with stopwords.

Generate the number of stopwrods for each row based on the summary with stopwords.  

------Modeling 1------

 Build linear regression model using the 3 features and the newly generated feature. Predict non-redundency score of test file and report MSE and pearson correlation.

 ------Generate features 2------
Generate the number of distinct words for each row based on the cleaned summary.  

------Modeling 2------

 Build linear regression model using the 3 features and the newly generated feature. Predict non-redundency score of test file and report MSE and pearson correlation.

------------------------------------------

Q4.2.1

------Functions------

5 functions here:

	count_rep_uni: count how many unigrams are the same as the previous unigrams in a list.

	rep_uni: count the repeat unigrams in each row.

	count_rep_bi：count how many bigrams are the same as the previous bigrams in a list.

	rep_bi: count the repeat bigrams in each row.

	read_score: return the minimum read_score of all the sentence in each summary.


------Generate features------

Generate features in training data and test data.

	Repeated unigrams count and repeated bigrams count are generated based on the summary with stopwords

	The read_score is generated on the original summary.

------Modeling------

Train linear regression model to predict the fluency. 

Get the MSE and pearson correlation. 

--------------------------------------------

Q4.2.2

------Functions------
3 functions defined her to generate new features.

	num_sen: Count the number of sentences in each summary.

	count_p: count preposition from a pos_tag list.

	num_prep: Get the count of preposition words in each summary.

------Generate features 1------

Generate the number of sentences for each row based on the original summary.  

------Modeling 1------

 Build linear regression model using the 3 features and the newly generated number of sentences feature. Predict fluency score of test file and report MSE and pearson correlation.

 ------Generate features 2------
Generate the number of preposition words for each row based on the cleaned summary.  

------Modeling 2------

 Build linear regression model using the 3 features and the newly generated number of preposition words feature. Predict fluency score of test file and report MSE and pearson correlation.
