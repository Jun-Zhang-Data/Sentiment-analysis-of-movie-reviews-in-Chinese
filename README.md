# Sentiment-analysis-of-movie-reviews-in-Chinese
##### Installation
Code can be run with Google Colab. Upload this repository to a folder named 'ML_Colab' in your Google drive. In the 'Data' folder, upload the data from the following [link](https://drive.google.com/file/d/102O0uHfhwE3wH2FRbFl60RAOl-OxiHRk/view?usp=sharing).

##### The Prepared Datasets
<p align="justify">
The data is collected from Douban Movie Short Comments Dataset V2 on Kaggle (Utmhikari, 2018). The data now has comments as the input and ratings from 1 to 5 are the labels. White space, punctuations, numbers, English alphabets, and stopwords are also removed from the text. Text is tokenized. Most of the comments are paired with ratings from 3 to 5, with ratings of 4 has the highest number, followed by ratings of 5 and ratings of 3. On the other hand, the ratings of 1 and 2 are much smaller in number, with less than 400,000 in total. The number of ratings of 3 is around 480,000. Ratings of 4 and 5 have around 1.2 million in total.
</p>

##### Implementation
<p align="justify">
Two strategies are taken for the sentiment analysis. The first way of using the data for sentiment analysis is to predict the ratings on a scale from 1 to 5 based on the comments left by the users. This is 5-class classification where the labels are ratings from 1 to 5. The second way of doing sentiment analysis of the data is to do a 3-class classification based on the comments. Instead of predicting the rating from 1 to 5, the ratings of 1, 2 are treated as negative labels, 3 as neutral labels, and 4 and 5 as positive labels. Data will be split into three parts with 70% of it being the training set and 30% of it being the test set. Out of the training set, 20% of it will be the validation set.
</p>

##### Vectorization Methods
* TF-IDF
* Skip-Gram
* FastText

##### Feature Selection Methods
* Chi Square
* Mutual Information

##### Classifiers
* Logistic Regression
* Multinomial Naive Bayes
* Linear SVC
* SGD Classifier
* LSTM
* BILSTM

##### Results
<p align="justify">
LSTM with fastText as the embedding method is the best-performing classifier for 5-class classification. For 3-class classification, fastText is the better embedding method compared to Skip-Gram for both LSTM and BILSTM. LSTM and BILSTM perform equally well when fastText is the embedding method. <br/>
When TF-IDF is applied as the vectorization method, Logistic Regression seems to be the best-performing traditional machine learning classifier both when feature selection methods are applied and not. <br/>
For 5-class classification, class 2 is the most difficult class to be predicted, with the possible reason that class 2 has the smallest data. On the other hand, class 1 and class 5 are the easiest classes to be predicted, possibly because the comments belonging to class 1 carry the most negative emotion, while the comments belonging to class 5 carry the most positive emotion. For the task of 3-class classification, the pattern of misclassification is that class 1 is most difficult class to be predicted, with the possible reason that the comments belonging to class 1 have mixed emotion, which might cause the classifiers to predict them as either negative or positive. On the other hand, class 2 is the easiest class to be predicted, with the possible reason that class 2 has the largest data. In addition, some comments can be misclassified for the task of 5-class classification but correctly classified for the task of 3-class classification, and vice versa.
</p>

##### References
Utmhikari (2018). Douban Movie Short Comments Dataset. (Version 7) [Data set]. url: https://www.kaggle.com/utmhikari/doubanmovieshortcomments/version/7.
