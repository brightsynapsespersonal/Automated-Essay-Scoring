﻿
# Automated Student Assessment and Essay Generator

### Background

The Hewlett Foundation has provided a set of high school student essays along with scores generated by human expert graders. The initial data was released in 2012<sup>1</sup> as part of a Kaggle competition to produce an automated student assessment algorithm to closely match the human scores. Scores are evaluated with the quadratic weighted kappa error metric, which measures the agreement between two raters.

Since then, a few teams have published their attempts to match or improve on the original challenge. Initial success was somewhat disappointing<sup>2</sup> as the Kappa scores were around 0.5, but improved significantly by incorporating modern NLP with neural networks<sup>3</sup>.

Sadly, it is no longer possible to submit kernels and the human graded scores for the validation and test sets have not be made public. Therefore it is perhaps unreasonable to compare kappa scores from the training data set with Kaggle leaderboard where models were trained on the full training data set, validated on the validation set and evaluated on the test data set.

Further confounding the issue, some published kappa scores are based on a subset of essay topics<sup>4</sup>, or evaluated by combining all scores together instead of individually by topic.

### Approach

My goal is to see if current NLP algorithms can improve upon the 2012 attempts. Additionally, can the essay and score combinations be used to automatically generate essays? 

Assessment can be performed in a variety of ways. For example, in an unsupervised approach, topic modeling can be performed to assign scores based on derived word probabilities.

A supervised approach is possible using machine learning on extracted features, such as named entities, syntax or labelled dependencies.

Neural networks have the advantage of working very well with word embeddings and their typically large number of features (dimensions).

Essay generation can be performed with recurrent neural network algorithms.

The data is provided as separate training, test and validation sets. The training data contains about 1700 essays for each of 7 topics and about 500 essay for an eighth topic. Essays are either source dependent responses or persuasive/narrative/expository on a given topic. The code is executed across four notebooks:

[1 EDA and Topic Modeling with LDA](0_EDA_and_Topic_Modeling_with_LDA.ipynb)

[2 Automatic Scoring with Machine Learning](1_Automatic_Scoring_with_Machine_Learning.ipynb)

[3 Automatic Scoring with Neural Networks](2_Automatic_Scoring_with_Neural_Networks.ipynb)

[4 Automatic Student Essay Generation](3_ASAP_Essay_Generator.ipynb)

### Outlook
This problem set has commercial impact far beyond student assessment and many applications can be tackled with nearly the same approach. For example:

* Given a set of financial documents, which one should a manager read first? 

* Which products can be effectively marketed to users based on their social media postings? 

* Detection of fake news vs real news.

* Sentiment analysis on a graded scale, e.g. very upset - upset - satisfied - happy - very happy.


## References

The original Kaggle competition can be found here:

https://www.kaggle.com/c/asap-aes/data

A selection of published work on the Kaggle ASAP data is given below:

<sup>1</sup> https://www.kaggle.com/c/asap-aes

<sup>2</sup> https://nlp.stanford.edu/courses/cs224n/2013/reports/song.pdf

<sup>3</sup>http://aclweb.org/anthology/D/D16/D16-1193.pdf 

<sup>4</sup> https://github.com/vasu5235/Kaggle-Automated-Essay-Checking-System/blob/master/Capstone%20report/capstone_report.pdf

<sup>5</sup> https://github.com/m-chanakya/AutoEssayGrading/blob/master/papers/paper1.pdf

<sup>6</sup> http://dspace.bracu.ac.bd/xmlui/bitstream/handle/10361/5399/12101114.pdf?sequence=1&isAllowed=y