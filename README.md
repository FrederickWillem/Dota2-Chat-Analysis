# Dota2-Chat-Analysis

## Accuracies:

### SVM: 0.67
### Logistic Regression: 0.65

## AUC:

### XGBoost: 0.704

1. We transformed a dataset on Dota 2 matches into a series of chat messages per team per game and which team won.
2. We transformed the messages sent by players, by turning emoticons and common abbreviations into direct English
3. We split the data 90%/10% train/test and then trained a word2vec model on the training set. This generated some promising results regarding the semantics of words.
4. For every message, we took the average of all the word vectors in it. For every set of messages sent by a team, we took the average of each message vector and for every match, we took the average of the message set vectors of team 1 and team 2.
5. We input this into 3 different models: SVM, Logistic Regression and XGBoost with 100 iterations. From these, we concluded that XGBoost performs best with an AUC-value of 0.704 and Logistic Regression performs worst with an accuracy of 0.65. Both the training and test data were approximately evenly split over team 1 winning and losing.
6. From the values we found, we can conclude that chat does indeed show to be a good estimate of whether a match was won or not. Most likely noise in the data (even after cleaning) and a lot of Russian is keeping down its performance.
