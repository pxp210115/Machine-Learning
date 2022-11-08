# California Housing Regression

We observe the shape of the data to be:

![image](https://user-images.githubusercontent.com/100412162/200453090-f1fd2aaa-73ae-4c43-8287-0078403d9a85.png)

AIM:

To predict the price of house based on 8 different variables such as no of bedrooms, no of rooms, long., lat.

Visualizing the training data:

The pixels as 0,1 indicate an overall picture to depict the number 5.

![image](https://user-images.githubusercontent.com/100412162/200453213-a527021b-9aea-4973-afac-73e7120c8703.png)

Baseline Model ( SGDClassifier):

![image](https://user-images.githubusercontent.com/100412162/200453296-a93107ef-73d8-4bb2-85b7-334685452d0c.png)

Evaluation Metric:

cross_val_score:

![image](https://user-images.githubusercontent.com/100412162/200453349-b03aa27c-27f6-459b-80d2-120f0df93761.png)

confusion_matrix:

![image](https://user-images.githubusercontent.com/100412162/200453383-72928866-09c8-4bd3-9a2e-af7cefa099c2.png)

ROC_curve for SGDClassifier:

![image](https://user-images.githubusercontent.com/100412162/200453442-13ab5e7b-d69f-48e1-93c8-132d0ccc92c1.png)

Comparing ROC_curve for SGDClassifier vs a more complex model such as Random Forests

![image](https://user-images.githubusercontent.com/100412162/200453550-106306f8-449d-4b2e-8c15-1852f680e7e2.png)

`Best Model:Random Forests`

`R² value: 80.39%`


