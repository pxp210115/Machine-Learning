## Chapter-10 Introduction to ANN with Keras

Perceptron- It is one of the simplest ANN architectures. It is simply composed of a single layer of TLU's, with each TLU connected to all the inputs

A TLU (Threshold logic unit) computes a weighted sum of all the inputs and then adds a step function as per the threshold required to determine a class to be positive.

## Implementation of the Perceptron

<img width="690" alt="image" src="https://user-images.githubusercontent.com/100412162/175992288-3207a07c-c805-4a9c-ab0a-1283dd097de4.png">

Note:- The difference between a logistic regression and a perceptron is that regression gives us the prediction probabilities whereas the perceptron provides us with a prediction on the basis of a hard threshold as shown above.

Perceptron has its limitations and cannot perfrom trivial tasks such as XOR gates. Hence, we use the MLP ( Multi layer Perceptron).

## MLP:-

![image](https://user-images.githubusercontent.com/100412162/175993205-f6f78985-58c3-4fcd-b081-b14e0634f55f.png)

Each MLP layer has a bias neuron except for the last layer. The above is an example of a feed forward neural network (FNN). A layer where all the neurons are connected to the neurons in the previous layer is called a Dense layer.

Another important feature is called as Backpropogation.

## Backpropogation:-

1) It handles one-mini batch at a time ( ex:- 32),  and it goes through the entire set multiple times. Each pass is called an epoch.

2) Each mini-batch is then passed to the input layer where thr algorithm computes the output of all the neurons and passes it on to the next layer. This si exactly like making predictions but all the intermediate results are neede as they are preserved for the **backward pass**.

3) The algorithm meaures the networks output error (i.e it uses a loss function that compares the actual output with the desired ouput of the network.

4) Then it computes how much each output connection contributed to the error. This is done using the chain rule. This chain rule is appplied till we reach the input layer. Which basically means that the reverse pass measures the gradient eroor acroaa all connection weights in the network.

5) The final step is perfroming a Gradient Descent step to tweak all the connection weights in the network.

Note 📝:- Gradient Descent cannot move on a flat surface, hence we tend to use activation functions such as Tanh and the use of Relu. Non-Linear activation functions are a must for non-linear complexities to understand the data and for the stacked neural network to make sense.

For specific outputs use the below mentioned activation functions:-

* For output between 0 and 1 use Logistic function

* FOr output between -1 and 1 use Tanh

* For output to be always postiive use the ReLu activation function.

Popular loss functions are MSE, MASE, but when we know that the data has too many outliers one should use the MAE ( Mean ABsolute Error).

## Classification MLP's:-

We dedicate one output neuron for each positive class. In the case of binary classification we use one output neuron to determine the class probabilities. When we use mutliple classification metrics ( i.e across multiple classes, we use the softmax function as the output probabilities are always between 0 and 1 and their sum adds up to 1.

## 1) Building an Image Classifier using the Sequential API:-

### Understanding the Data

We first fetch the data using the keras Data API and classify them into test, train and validation data set.

![image](https://user-images.githubusercontent.com/100412162/178121229-047bd2c9-56cf-4257-8353-986b7aa6b71c.png)

The above are the shapes of the data.

### Modelling

![image](https://user-images.githubusercontent.com/100412162/178121239-12e1274f-0230-4d75-a2d7-489bdcf7b0f5.png)

The Sequential API is the simplest kind of Keras model for Neural networks.

The Flatten layers helps in converting the initial 2-D array to a 1-D array. We however need to specify the input_shape which doesn't include the batch size and only the shape of the instances.

We have a bunch of Dense layers followed by the ouput layer which usually has the same shape as the number of classes. The softmax function ensures that the sum of all the probabilties is equal to 1.

The layers in Keras can act individually as a Dense layer of neurons. We can get each layer and the specfic weights and biases that the layer stores. These are updated at the end of each training and stored for interaction with the next set of the data.

![image](https://user-images.githubusercontent.com/100412162/178121466-0fb41dc3-fd50-4eb7-a76a-c35ebdef8531.png)

We have a bunch of Dense layers followed by the ouput layer which usually has the same shape as the number of classes. The softmax function ensures that the sum of all the probabilties is equal to 1.

### Compiling and Fitting the model

![image](https://user-images.githubusercontent.com/100412162/178121500-5abe9fc2-4d14-4e6d-b6f6-13de26d87a83.png)

In the above fit function we see that we get metrics such as loss and accuracy at the end of each epoch.

Note 📝:- If the training data is very skewed we can set the class_weight argument when calling the fit() method. This would allow for a larger weight to under represented classes to ensure equality of visibility.

![image](https://user-images.githubusercontent.com/100412162/178121513-98c47c53-87b1-4ed6-a7f9-5de9a6b34c80.png)

The fit method returns a history object containing the training parameters, the list of epcohs it went through and the training parameters such as loss and validation.

### Making Predicitions on the data

![image](https://user-images.githubusercontent.com/100412162/178121557-048aa103-51b2-499b-9327-da0528b6d408.png)

## 2) Building a Regression MLP using the Sequential API

### Data Understanding

We split the data into train, test and validation. Each training sample has 8 parameters each to predict a continuous solution.

![image](https://user-images.githubusercontent.com/100412162/178121605-64471e96-6012-4683-a154-b6574072c264.png)

### Scaling the Data

![image](https://user-images.githubusercontent.com/100412162/178121631-26808418-0ef3-4451-a769-a77349b2581a.png)

Note 📝:- We tend to never fit and transform the validation data/ test data as they need to be untouched by the model for real-time like predicitons.

### Fitting the model, Evaluation and Prediction

![image](https://user-images.githubusercontent.com/100412162/178121661-5f87295c-7a62-48fd-929c-7dc34449e205.png)

## 3) Implementing A Wide and Deep Neural Network

First we need to create an Input object. This is a specialization of the kind of input the model will get, including its shape and dtype.

We then pass the input layer as function to the hidden1 layer. This acts as a functional API as it only tells how to connect the multiple layers and there is no data flowing through the model yet.

### Creating the Model

![image](https://user-images.githubusercontent.com/100412162/178121936-28cd2e0d-5e9e-4387-8ac8-002fd8efc8f9.png)

### Compiling and Training the model

![image](https://user-images.githubusercontent.com/100412162/178121958-995553ef-5e4c-4d98-9b93-8f46529bc1ec.png)

### Saving the Model and Loading it

![image](https://user-images.githubusercontent.com/100412162/178121984-bdabbd8a-312f-4286-aea2-9265b61509e2.png)

## Using Callbacks during Training

![image](https://user-images.githubusercontent.com/100412162/178122011-15a30348-a196-4f67-8975-796a63c1d3e0.png)

The callback above helps us to not overfit the model/ train it extensively for no better use in the metric. We therefore use the ModelCheckpoint callback as it helps in putting a checkpoint after each epoch and then tells us when the model is no more improving on further iteration. The parameter used is the save_best_only to save the best weight for minimal loss which is our loss function for the model.





