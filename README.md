# NLPProject

**Title:**<br />
 *Evaluating Doc2Vec Model based on Sentiment Analysis on IMDB DataSet (Using Gensim)*
 
 **Background Information** <br />
 Many ML algorithms require the input to be presented as a fixed-length feature vector. (For example Bag-Of-Words is one of the most common fixed-length feature.)
Bag-Of-Words has two major weaknesses: 
1)Loses the  ordering of words 2)Ignores semantics of words

Doc2Vec (Paragraph Vector) is an unsupervised algorithm that learns fixed-length feature representations from variable-length pieces of text.
 In this algorithm each document is represented by a dense vector which is trained by predicting words in the document. 
This method overcomes the Bag-Of-Words weaknesses.


**Word2Vec Vs. Doc2Vec** <br />
In Word2Vec, you train to find word vectors and then you use these word vectors in NLP tasks.
Doc2Vec generates vectors representing documents (sentences, paragraphs) 
While Word2Vec computes a feature vector for every word in the corpus, Doc2Vec computes a feature vector for every document in the corpus. 

**How Does it Work?** <br />
Both Word2Vec and Doc2Vec train models to predict one or more words. The weight matrices that are created during this training are the word and document vectors.
Gensim allows you to train Doc2Vec with or without word vectors

**Paragraph Vector : A distributed memory model (PV-DM)** (Right Image)<br />
The basic idea behind PV-DM is inspired from Word2Vec . Every paragraph is mapped to a unique vector represented by a column in matrix D  and every word is mapped to a unique vector represented by a column in matrix W. Paragraph vector or word vectors are averaged or concatenated to predict the next word in context.
After being trained , the paragraph vector can be used as a feature for the paragraph. 

**Paragraph Vector without ordering :Distributed bag of words (PV-DBOW)** (Left Image) <br />
In this method we ignore the context words in input but force the model to predict words randomly sampled from the paragraph.In this version, the paragraph vector is trained to predict the words in a small windows. In our experiment, each paragraph vector is combination of PV-DM and PV-DBOW. 


<img src="https://user-images.githubusercontent.com/81987771/115461302-43b71c80-a1f7-11eb-8ec8-17ebb5422f6f.png" width="500"/> <img src="https://user-images.githubusercontent.com/81987771/115461659-adcfc180-a1f7-11eb-8326-f24928e7c1f2.png" width="500"/> 


**Dataset:**<br />
We used the imdb Dataset from below link here: ( It will be downloaded as a one of the steps in Jupyter notebook file)
<http://ai.stanford.edu/~amaas/data/sentiment/>`_ 

These reviews will be the documents that we will work with. There are 100 thousand reviews in total.
25k reviews for training (12.5k positive, 12.5k negative)
25k reviews for testing (12.5k positive, 12.5k negative)
50k unlabeled reviews


**Methodologies:**<br />
Our starting point was to replicate part of the papers listed below which includes the original papers on Doc2Vec concept.
We chose to test the application of Doc2Vec on sentiment analysis.
The Auhtors did not publish their codes .However there were several implementations of their papers. We chose one of those implementation as a baseline.
That implemenation trained the models based on Gensim(Doc2Vec) and then assess the sentiments uning the Logistic Regression. We expanded that assess the sentiment using RandomForest Classifier and GaussianNB.<br />
*Other papers mentioned the difficulty in replicating the original papers both for accuracy and in terms of the best models and hyperparameters.We performed several experiments to determin the best Doc2Vec model in predicting sentiment.*

**Results:**<br />
We got the based results based on the Logestic Regression and the one of the concatenated model of DBOW and DM has the best result after that we have DBOW plain model which gets the better result which is different from what they menntioned in paper

**References:**<br /> 
We try to replicate the concepts of these two papers:<br />
* Paper 1:* https://arxiv.org/abs/1405.4053       * Paper 2:* https://arxiv.org/abs/1507.07998

Gensim – Deep learning with paragraph2vec (https://radimrehurek.com/gensim/models/doc2vec.html)

https://radimrehurek.com/gensim/auto_examples/howtos/run_doc2vec_imdb.html#sphx-glr-download-auto-examples-howtos-run-doc2vec-imdb-py





