# Predicting Heart Disease 

<p align="center">
  <img width="460" height="300" src="https://user-images.githubusercontent.com/100412162/200221104-4522f711-dc4e-4eb9-9996-f94742addb38.png">
</p>

## Aim:

The AIM is to predict if a person would suffer from a heart disease given the person's biological measurements such as Blood Pressure, cholestrol etc.

`Task` : Classification

`No of variables` : 14 

`No of rows`: 1050

`Independent Variable`: **Target** 
- [ ] 0 for No Disease

- [ ] 1 for Disease

### [Python notebook link](https://github.com/pxp210115/Machine_Learning-with-Scikit-Learn/blob/main/1.%20Predict%20Heart%20Disease_Classification/1.Heart_disease_Classification.ipynb)

## Data:

![image](https://user-images.githubusercontent.com/100412162/200219502-a3b23a1f-203e-4b9f-a06a-5edbc7f14738.png)

Independent Variable distribution:

![image](https://user-images.githubusercontent.com/100412162/200219596-d6c057b7-fbb8-497a-887c-126a0f1c65a3.png)

## Baseline Model:

Support Vector Machine for Classification ( LinearSVC) after StandardScaling using Pipeline

![image](https://user-images.githubusercontent.com/100412162/200219708-2edff3e6-6d9f-4ed3-85d4-06f8f1f97e37.png)

### Baseline Score:

![image](https://user-images.githubusercontent.com/100412162/200219749-7c5537cb-02f1-4a95-be5d-67442273c4bf.png)

### Choosing a more complex model: RandomForestClassifier

`hyperparameter`: n_estimators =2

![image](https://user-images.githubusercontent.com/100412162/200219831-bfef460f-621b-4749-8831-d6e1201cbf1e.png)

## Evaluation

Classification Report:

![image](https://user-images.githubusercontent.com/100412162/200219998-4c485b89-88e6-4b60-9a2c-20581e49d4e8.png)

## Hyper-parameter Tuning:

![image](https://user-images.githubusercontent.com/100412162/200220179-800786c2-fb3f-4e58-81f1-4735a5d84753.png)


## BEST MODEL AND ACCURACY:

RandomForest Classifier with n_estimators of n=4 produces an accuracy metric of 99.75%



