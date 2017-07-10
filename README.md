Sentiment Analysis - Amazon Beauty Reviews <br> Aubrey Browne <br> DSCI6004 <br> December 2016
----

**Goal/Problem:**  
The goal of this project was to use the descriptive vocabulary in Amazon beauty reviews to train several machine learning models to predict the overall sentiment (positive or negative) about a product. This is an interesting problem because it could help determine product success or be used identify issues. The information could then be used to improve advertising, marketing, or even the product itself. Therefore, this could lead to a large impact on the future success of a beauty product.

**Procedure:**  
The data that was used for my project was roughly 200,000 Amazon beauty reviews for about 12,000 unique products. The data had approximately 78% positive reviews(rated with 4 or 5 stars) and 22% negative reviews (rated with 1-3 stars).

Preprocessing natural language processing (NLP) data can be time consuming and certain decisions need to be made such as: Should I remove stop words?  Do you remove capitalization? How to handle contractions? I ultimately decided to remove stop words, capitalization, and punctuation since it made the data easier to work with. This made my data a bag of words which means that the order of the words no longer were preserved.

The models that I decided to run were Naive Bayes, logistic regression, and support vector machines since they are all binary classification models. I ran all with count vectorization and term frequency inverse document frequency (tf-idf).

Naive Bayes with count vectorization outperformed all the other models with an AUC of 0.905. The next best model was Naive Bayes with tf-idf which performed with an AUC of 0.8883. The next overall model was support vector machines (SVM) with AUC of 0.8700 and logistic regression had an AUC with 0.86 for both count vectorization and tf-idf.

I was happy with the results of all of the models but one thing I would like to note is that SVM took about 5 hours to run on my local. While both Naive Bayes and logistic regression ran within a few minutes. This could be overcome with a GPU (graphics processing unit) on a virtual machine.

The next part of my project was to look at sentiment analysis through TextBlob which is a library in Python used for processing textual data. It is a simple API used for many NLP tasks including sentiment analysis.

For this part of the project, I grouped all reviews by product (~12,000) and looked at the vocabulary from all of the reviews for each product. Then through the use of TextBlob, I assigned a polarity score to each item with negative polarity correlating to negative reviews/vocabulary and a positive polarity corresponding to positive reviews/vocabulary.

I separated the positive and negative reviews into two groups and plotted the distributions of each group's’ product polarity scores. These two distributions followed a normal curve and found that the two distributions were statistically different after running a t test. Concluding that both groups were more positive than negative since the mean polarity score for both was approximately 0.19. This could be explained by the fact that Amazon remove products that are low performing, in order to keep up their reputation.
