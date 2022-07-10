# Training Models

## Linear Regression :- 

![image](https://user-images.githubusercontent.com/100412162/178146080-c8cbf5c8-2a7d-4fd0-a75d-fc8d9d7da961.png)


The above image demonstrates that Linear Regression is the model that tries to find a linear/ direct solution of how two parameters interact with each other and understand their relationship mathematically.
This allows us to predict the value of 'y' given any 'x'.

## The different ways of Linear Regression:-

1) Direct-closed form equation :- This equation of y=mx +c allows us to directly compute the linear relationship by minimizing the cost function over the training set.

    Note 📝:- Cost function is a funnction that tries to reduce the error

2) Gradient Descent (GD):- It is an iterative optimization approach that gradually tweaks the parameters to minimize the cost function over the training set.

    There are three main types of Gradient Descent:-

    a) Batch GD

    b) Mini-batch GD

    c) Stochastic GD
    
 ## 1) Direct-closed form equation :- 
 
![image](https://user-images.githubusercontent.com/100412162/178146126-a0ef1605-47e5-4259-8574-b70cf43405cc.png)
 
 The Beta(0) term is what is called as the bias term/intercept term. Beta(1) is the coefficient of 'x' which is the input variable to predict 'y' which is the output variable. It is always in the form of y=mx +c.
 
 In order to understand the performance measure of a regression model we use RMSE( Root Mean squared error).
 
 🎯 :- The main aim of the linear regression is to find a value of Beta(0) that minimizes the RMSE.
 
 ![image](https://user-images.githubusercontent.com/100412162/176452634-e15364a5-3c76-4e0b-8c0e-7e65c2fb602a.png)
 
 In order to find the closed form solution we use the normal equation, which we shall not cover as it is not widely used. An implementation of the same can be done by using the LinearRegression module from scikitlearn.linear_model
 
 Limitation:- The computational complexity of the scikitlearn's LinearRegression is O(n^2) which is generally not considered scalable code. Hence we look to other solutions such as the Stochaistic Gradient Descent.
 
 ## 2) Gradient Descent :- 
 
The idea of a gradient descent is to tweak paramters iteratively in order to minimize a cost function which is usually MSE/MAE for regression and Cross_entropy for classification problems.
 
Major steps involved:-

1) You can start filling the vector with random values (Random initialization). Then you improve it gradually until the algorithm converges at the minimum.

![image](https://user-images.githubusercontent.com/100412162/178146052-ed2d2ed9-da56-4bc5-9ff0-396a7aba1bd6.png)






