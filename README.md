# product calssification challenge
This problemis simple but yet complex. Lack of labelled data add to complexity. So, I rely on pretrained models. The approach here
is ensemble method. Predict on the basis of 1) product description and 2) use image to classify. Then take the average.

* Run Jupyter Notebook product_classification.ipynb

* Output file after classification is classified_product_data.json

### Why are you designing the solution in this way?
More of NLP algorithms are moving towards deep learning. For this problem, however, I unable to leverage deep learning. Deep learning needs more data for training. Also, I did not find any pretrained models for eCommerce ( fashion or beauty ). There is no public data set available. So, I have choosen text classification word embeddings approach. Good pretrained word embedings are available in open source community. 

### What are the aspects that you considered when designing?
I considered not to spent much time, finish within 3 hours. I attempted to label data but did not pursue as this will take time. Basically, tried to solve the problem with many constraints like no labelled data, data set is very small etc. I leveraged word embedings and cosine similarity to find the highest match for product to a cetegory. Data clean-up ( preprocessing ) is important for vector space model to have better score. So, I considered data preprocess is importatnt. Liguistics or grammar is very important here as well. 
I changed "Intimate" category to "Intimate Collection" as is used in retail. This is required only when we match, not required when we output i.e in while display. We can still display "Intimate" to uses. Few categories, I manually changed to its singular form ( e.g. "Dresses" to "Dress) to get better accuracy and not clubbed into "Others" category. 

In part-2, I have designed code to use deep learning to classify images, but this requires to label the data. I did few but itakes lot of manual effort and time, so I abandoned but code is still there in Jupyter Notebook. Using a pre-trained model removes the need for you to spend time obtaining, cleaning, and processing (intensively) such large datasets. This requires few thousand of laballed data to train for this specific project using transfer learning.

Second problem I found is images has multiple objects in it. So, simple image classification may not work. In this cases, object detection will give better result. Object detection in OpneCV also requires few labelled images, which is not given in this home-work.

### What are the cases your solution covers, how are they covered and why are they important?
It covers all the cases, I believe, my only concern is accuracy. It can be improved, by training a word2vec model with eCommerce training data. Better alogrithm to find a good threshhold value which determines "Others" category.

### What are the cases your solution does not cover and what are the ways you can extend your current solution for them?

The disadvantage of pre-trained word embeddings is that the words contained within may not capture the peculiarities of language in your specific application domain. For example, Wikipedia may not have great word exposure to particular aspects of legal doctrine or religious text, so if your application is specific to a domain like this, your results may not be optimal due to the generality of the downloaded model’s word embeddings.

Initially, I was thinking to use a hybrid model one from text i.e. product description and two from images. Given little bit more time, I would have tried "attention" and transformers.
