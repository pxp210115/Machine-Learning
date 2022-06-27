## Chapter-10 Introduction to ANN with Keras

Perceptron- It is one of the simplest ANN architectures. It is simply composed of a single layer of TLU's, with each TLU connected to all the inputs

A TLU (Threshold logic unit) computes a weighted sum of all the inputs and then adds a step function as per the threshold required to determine a class to be positive.

Implementation of the Perceptron

<img width="690" alt="image" src="https://user-images.githubusercontent.com/100412162/175992288-3207a07c-c805-4a9c-ab0a-1283dd097de4.png">

Note:- The difference between a logistic regression and a perceptron is that regression gives us the prediction probabilities whereas the perceptron provides us with a prediction on the basis of a hard threshold as shown above.

Perceptron has its limitations and cannot perfrom trivial tasks such as XOR gates. Hence, we use the MLP ( Multi layer Perceptron).

MLP:-

![image](https://user-images.githubusercontent.com/100412162/175993205-f6f78985-58c3-4fcd-b081-b14e0634f55f.png)

Each MLP layer has a bias neuron except for the last layer. The above is an example of a feed forward neural network (FNN).
