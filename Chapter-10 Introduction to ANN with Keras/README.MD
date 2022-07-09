## Chapter-10 Introduction to ANN with Keras

Perceptron- It is one of the simplest ANN architectures. It is simply composed of a single layer of TLU's, with each TLU connected to all the inputs

A TLU (Threshold logic unit) computes a weighted sum of all the inputs and then adds a step function as per the threshold required to determine a class to be positive.

Implementation of the Perceptron

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

## Building an Image Classifier using the Sequential API:-

