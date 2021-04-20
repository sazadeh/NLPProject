# NLPProject

<b>Title: </b>
 Evaluating Doc2Vec Model based on Sentiment Analysis on IMDB DataSet (Using Doc2Vec Model/ Gensim)
 
 <b>Background Information</b>
 Many ML algorithms require the input to be presented as a fixed-length feature vector. (bag-of-words one of the most common fixed-length feature)
Bag-of-words has two major weakness: 
 loose ordering of words, ignore semantics of words
Paragraph Vector is an unsupervised algorithm that learns fixed-length feature representations from variable-length pieces of text
 In this algorithm each document represent by a dense vector which is trained by predict words in the document. 
This method overcome the bag-of-words weaknesses


We try to use these two papers:
Paper 1: https://arxiv.org/abs/1405.4053       Paper 2: https://arxiv.org/abs/1507.07998


![Screen Shot 2021-04-20 at 3 58 45 PM](https://user-images.githubusercontent.com/81987771/115456630-634b4680-a1f1-11eb-9b13-938f09bd2b81.png)
<img width="249" alt="Screen Shot 2021-04-06 at 9 28 50 PM" src="https://user-images.githubusercontent.com/81987771/115456641-67776400-a1f1-11eb-9be6-e72cf620809e.png">




<b> Dataset:</b>
We used the imdb Dataset from here: ( It will be downloaded as a one of the steps in Jupyter notebook file)
<http://ai.stanford.edu/~amaas/data/sentiment/>`_ ( the size was more than 25Mb we could not upload here)

These reviews will be the documents that we will work with in this tutorial. There are 100 thousand reviews in total.

25k reviews for training (12.5k positive, 12.5k negative)

25k reviews for testing (12.5k positive, 12.5k negative)

50k unlabeled reviews

First Experiment:
We made these models:
Doc2Vec(dbow,d100,n5,mc2,t4) vocabulary scanned & state initialized
Doc2Vec(dm/m,d100,n5,w10,mc2,t4) vocabulary scanned & state initialized
Doc2Vec(dm/c,d100,n5,w5,mc2,t4) vocabulary scanned & state initialized
Doc2Vec(dm/m,d100,n5,w5,mc2,t4) vocabulary scanned & state initialized
Doc2Vec(dm/m,d100,n5,w5,mc2,t4) vocabulary scanned & state initialized

Our Error rates for the buitin models are sorted and the result is :
Error Rate and Model Name:

0.1074 	 Doc2Vec(dbow,d100,n5,mc2,t4)+Doc2Vec(dm/m,d100,n5,w10,mc2,t4)
0.1094 	 Doc2Vec(dbow,d100,n5,mc2,t4)+Doc2Vec(dm/c,d100,n5,w5,mc2,t4)
0.10948 	 Doc2Vec(dbow,d100,n5,mc2,t4)
0.1096 	 Doc2Vec(dbow,d100,n5,mc2,t4)+Doc2Vec(dm/m,d100,n5,w5,mc2,t4)
0.18848 	 Doc2Vec(dm/m,d100,n5,w10,mc2,t4)
0.21308 	 Doc2Vec(dm/m,d100,n5,w5,mc2,t4)
0.35204 	 Doc2Vec(dm/c,d100,n5,w5,mc2,t4)

Random Forest Clasifier Results:

0.227960 Doc2Vec(dbow,d100,n5,mc2,t4)
0.255800 Doc2Vec(dm/m,d100,n5,w10,mc2,t4)

<b> References: </b> 
Gensim – Deep learning with paragraph2vec (https://radimrehurek.com/gensim/models/doc2vec.html)

https://radimrehurek.com/gensim/auto_examples/howtos/run_doc2vec_imdb.html#sphx-glr-download-auto-examples-howtos-run-doc2vec-imdb-py





