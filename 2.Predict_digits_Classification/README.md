# Predict MNIST hand-written digits

# Classification:-

Classification is a supervised Learning task that helps in predicitng classes/ labels that are not continuous in nature. If the data can be classified into two classes it is called as Binary Classification or else it is called Multiclass Classficiation(if there are multiple classes).

### About the Data:-

MNIST:- It is a set of 70,000 small images of digits handwritten by high school students and employees of the US Census Bureau

Data has the images coded into pixels for relative use as well as their respective labels to represent which digit it is. This tells us that it is a supervised problem as we already have the labels in place for the training data

### Shapes of the Data:-

We can see that we have X and y to represent pixels and it's respective labels.
The size of X tells us that there are 70,000 images of data and each image has been represented in 784 pixels which is 28*28 pixels by nature.
![image](https://user-images.githubusercontent.com/100412162/174502604-7b6e0a9e-560d-4365-a2e7-eac38624e4f5.png)


Randomly visualizing the data and it's respective label.This ensures that the labels are clearly representative of the data.

![image](https://user-images.githubusercontent.com/100412162/174502668-b636ffdb-9aa6-4a65-8558-8ea8c8c68bb9.png)

### Splitting the data into Training set and Testing set

Because we used the open_ml and fetched the MNIST data, the data has been already split for us into train,test. We do not need to use the train_test_split
![image](https://user-images.githubusercontent.com/100412162/174502712-44fc7dfb-ded1-4f72-8e26-05afff7ecc10.png)

### Which model to choose from?

Always follow the sklearn model selection image that is also present on [Sci-kit Learn's documentation](https://scikit-learn.org/stable/tutorial/machine_learning_map/)

Our problem consists of:-
1) Data points > 50
2) Is used to predict a category
3) Has labelled data
4) Has a decent number of training samples

So as per our problem and the map presented above we shall go ahead with the SGDClassifier as our first choice.
![image](https://user-images.githubusercontent.com/100412162/174502844-0e4e6d6f-b7fc-4327-924e-f812ceed228e.png)

We start by creating a "5 or not 5" classifer where

We do not change the values of the x labels as they dont need to be altered for training purposes.
y_train_5 = y_train == 5
y_test_5 = y_test == 5

### Creating a Binary CLassifier
![image](https://user-images.githubusercontent.com/100412162/174502761-e75cda4e-3485-4b74-962a-1182bacc2d65.png)

### Evaluating our Model

We always evaluate our model on what it has already trained ( X_train) and how it performs while predicting the labels (y_train_5.

**a) Cross- Validation:-** This method allows us to split the training data into k-folds and then making predicitons and evaluating on each fold using a trained model

The model in our case is the SGDClassifier 

![image](https://user-images.githubusercontent.com/100412162/174503024-f948095f-9dd1-4c7a-ba2c-9e9a894694c5.png)

We achieve an average accuracy of 95% which is great but it does not take into consideration that the training data has an unequal balance of training data with the label 5 vs the ones that arent. Even a very normal rule based model could achieve such high levels of accuracy because of the class imbalance.

📝 Note:- Accuracy is not a very good metric when it comes to skewed datasets

**b) Confusion Matrix:-** This helps us to count the number of times data from class A has been wrongly predicted as Class B or rightly predicted as Class A.

📝 Note:- To compute the confusion matrix we need to have the predicitons made by the model. This metric helps us to compare the actual labels( ground-truth labels) with the predictions made.

We shall compute the predictions made by using the cross_val_predict ( which is similar to cross_val_score but instead returns actual predicitons and not predcitions scores).

![image](https://user-images.githubusercontent.com/100412162/174503229-eab202fc-151b-4bc5-b7d0-64f79651746d.png)

Each row in a confusion matrix represnts an actual class, while each cilumn represents a predicted class. First row is the -ve class (non-5's predicted).

[ True Negatives   False Positives]
[ False Negatives  True Positives]

The diagonals represent the correct predicitions and the wrong predicitons.


**c) Precision:-** Tells us the accuracy of the positive predictions. Of the positive predictions how many were actually correct

= True Positives/( True Positives + False Positives)

**d) Recall:-** Tells us the ratio of positive instances that are correctly detected by the classifier. Of all the positive instances,how many were correctly detected

= True Positives/(False Negatives + True Positives)

![image](https://user-images.githubusercontent.com/100412162/174503664-39b47ab2-0f1a-4f02-a2f6-37f83b1698f3.png)

We achieve a score of 83% which suggests that we are able to predict 83% of the training data accurately with our model.

We also achieved a score of 65% which suggests that we are only able to predict 65% of the positive instances correctly which is bad.

📝 Note:- As we can see that there is a tradeoff when it comes to precision and recall. An increase in precision leads to decrease in recall, whereas an increase in recall leads to an decrease in precision.

e) ROC- Curve :- It is the area under the ROC curve that is formed by plotting the TPR ( True positive rate or Recall) against the FPR ( False Positive Rate).

TPR is the same as recall. 
FPR is the ratio of -ve instances that have been incorrectly classified as Positive.

![image](https://user-images.githubusercontent.com/100412162/174504398-8bf251eb-55de-4a45-9b04-3059ae28224e.png)

To compare multiple classifiers we use Area under the ROC curve.

We make predicitons using the RandomForestClassifier and the SGD and then compare them as below:-

![image](https://user-images.githubusercontent.com/100412162/176000491-f8959eb5-4537-4014-9a17-1e9ef8592f31.png)
