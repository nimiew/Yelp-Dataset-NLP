# Requirements and Download links:
Anaconda Python 3.7 Version (https://www.anaconda.com/distribution/) - Anaconda comes pre-packaged with many data science libraries we used.
Additionally, install the following libraries within conda environment:
	conda install -c conda-forge spacy
	conda install tensorflow
	conda install tensorflow-gpu
	python -m spacy download en_core_web_sm # Note this one requires running the command prompt as administrator
Download glove.twitter.27B.zip (http://nlp.stanford.edu/data/glove.twitter.27B.zip) - We used GloVe word embeddings to transform the reviews into a format for classification. We used 200d vector representation for training the neural network.
	
# How to replicate experiments:
Note: We didn't set the random seed for the data analysis portion of the project, so re-running may give different results. 
1.	Open jupyter notebook at directory (Ensure conda environment is activated)
2.	Place the json data files in the same directory
3.	You can just open each notebook and run the cells sequentially

# Notebooks and their output
Dataset Analysis.ipynb
	The files produced are:
	
	text_20.txt - 5 random samples for comparing with Straits Times Article
	sample_straits_times.txt - Scraped Straits Times Article
	
	reviews.csv - Converted reviewSelected100.json to csv format for faster loading
	star level 1 num reviews against num sentences.png
	star level 2 num reviews against num sentences.png
	star level 3 num reviews against num sentences.png
	star level 4 num reviews against num sentences.png
	star level 5 num reviews against num sentences.png
	Number_of_reviews_given_stars.png - distribution of reviews based on stars
	5_reviews_and_their_segmentation.txt
	
	num reviews against num tokens (Tokenization).png
	num reviews against num tokens (Stemming).png
	
	stop_words.txt
	top_20_tokens.txt
	top_20_tokens (stemmed).txt - not required but useful for comparison with top 20 stems
	top_20_stems.txt
	
	POS_tagging_result.txt - POS Tagging results for 5 random sentences
	
	most_frequent_adjectives.txt - most frequent adjectives per star rating
	most_indicative_adjectives.txt - most indicative adjectives per star rating
	good_in_1.0.txt - reviews with star rating 1 but with the word 'good'
	
Development of a Noun-Adjective Pair Summarizer.ipynb
	noun_adj.txt - most frequent Noun-Adjective Pairs for 5 different reviews
	
Data Preparation for Application.ipynb
	X.npy - GloVe vector representations for each review
	X_tfid.npy - TF-IDF representations for each review
	Y.npy - Star ratings for each review
	
Application - Predicting Star Rating (SVM, KNN, Random Forest, Logistic Regression).ipynb
	Uses scikit-learn for building various models to predict star rating
	
Application - Predicting Star Rating (Feed Forward Neural Network).ipynb
	Uses tensorflow to for building FFN to predict star rating