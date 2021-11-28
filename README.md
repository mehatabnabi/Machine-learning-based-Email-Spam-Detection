## MACHINE LEARNING BASED SPAM EMAIL DETECTION

### Objective/Business Problem
Email has become one of the most important forms of communication. Below are some of the stats concerning emails:

* There are over 4 billion email users worldwide.
* There are over 7 billion email accounts.
* 95% of consumers check email every day.
* In 2020, over 306 billion emails were sent and received daily.
* Over 3 million emails are sent every second.
* Total email volume grew 7% in 2020.

In these collosal stats, Spam literally accounted for 47.3% of all email traffic in 2020. That means, about half of all the emails in the world are unsolicited messages. Data from 2020 points to the average percentage of 47.3%, meaning close to 150 billion spam emails are sent daily. Therefore, an effective spam filtering technology is a significant contribution to the sustainability of the cyberspace and to our society (Reference - https://99firms.com/blog/how-many-email-users-are-there/#gref)


The objective of this project is to build an efficient ML based email spam detector application. We are going to use 4 machine learning algorithms (Logistic regression, Support vector machine classifier (SVM), Random forest, Gradient boosting classifier) to classify the dateset containing spam and ham emails into their respective labels.


### Methodology
* We start with exploring the data and understanding the structure of the emails and their content.
* The data is then cleaned by removing any punctuation or special characters so these don't contribute to the noise in the model.
* We then define a few functions to convert all the email content to plain text and build a dataframe out of it.
* Then we proceed to build the machine learning models by vectorizing the text using the TFIDF vectorizer and feeding the data into them.
* Since the data classes are unbalanced we evaluate each model based on different performance metrics (majorly the F-1 score and the AUC ROC scores). After selecting the best model, it is finally evaluated on the test set.

Feature extraction: TF-IDF

Term frequency-Inverse document frequency uses all the tokens in the dataset as vocabulary.Frequency of occurrence of a token from vocabulary in each document consists of the term frequency and number of documents in which token occurs determines the Inverse document frequency.What this ensures is that,if a token occurs frequently in a document that token will have high TF but if that token occurs frequently in majority of documents then it reduces the IDF ,so stop words like an,the,i which occur frequently are penalized and important words which contain the essence of document get a boost.Both these TF and IDF matrices for a particular document are multiplied and normalized to form TF-IDF of a document.


### Conclusion
We observed that SVM-TFIDF vectorizer model perofomed the best with:
Precision:0.939,
Recall:0.991,
F1 score:0.964,
accuracy:0.989515,
AUC:0.990027.

The summary of the classification performance of all the ML models used is as follows:

| Model     | Precision | Recall  | F1 | Accuracy |AUC|
| ----------- | ----------- |--  |--|--|--|
| TFIDF vectorizer with LogisticRegression      | 1.000       |0.972   |0.986  |0.996068  |0.986111  |
| TFIDF vectorizer with SVM   | 0.939        |  0.991 |0.964  | 0.989515 |0.990027  |
| TFIDF Vectorizer with Random Forest Classifier            |  1.000           | 0.935   | 0.967 |0.99082  | 0.967593 |
| TFIDF Vectorizer with GradientBoosting Classifier            |   0.812          |   0.880 | 0.844 |0.954128  | 0.923021 |
