---
description: 'Connectionist models are powerful, but how do they learn?'
---

# Learning

## Neuron

* _v_ = \(Sum of each input and weight\) + bias
  * or dot product of **x** and **w**
* Feed into activation function for the output
  * hardlim \(0, 1 output\)
  * sigmoid \(between 0 and 1 curve\)
  * tanh \(-1 and 1 curve\)
  * ReLu \(0 and inf\)
  * linear \(just output _v\)_
* Activation function is for the non-linear behaviour
  * Each neuron can only approximate the activation function it has
  * But combined they can approximate non-linear functions!
    * thus we need multi-layer networks

Perceptron is a single layer neural network

Multi-layer perceptron \(or fully connected\) can learn many non-linear functions!

## Learning

### Regression

e.g. fitting x,y values to some unknown curve based on some samples

* Evaluate with mean squared error

### Classification

e.g. map vectors / images to labels

#### Binary classification

This or that

* Sigmoid is good for emulating a probability between 0 and 1

#### Multi-class classification

* One hot encoding
* Output class 1 neuron, class 2 neuron.... feed into softmax to convert outputs into probability distribution

#### Evaluation

* Well either it is correct or incorrect
* Accuracy: Fraction of correct labels over N examples
* Errors: Fraction of incorrect labels over N examples
* Cross entropy: -\(Likelihood of model predicting the class labels well\)
  * Works well with sigmoid or softmax outputs

### Changing weights

* Derivatives can only be calculated on smooth functions
  * Accuracy and classification error aren't smooth! 
  * MSE and CE are
* Adjust weights by using their gradients with respect to the loss function to minimise loss
  * Should get closer to desired output

### Optimisation

Network is essentially a function of _inputs, weights_ and _biases_

Process of gradually changing the state in order to minimise the loss function. 

* Stochastic Gradient Descent \(sgd\)
* Optimisers: Adam, RMSProp

Gradient tells us which direction to go, but not how far.

* Some optimisers will try different approaches to reach the goal quickly

### Backpropagation

* Forward computation of output
* Backpropagation of gradient/derivative information through the network
  * Distribution of 'blame' for incorrect output



\_\_



### 

