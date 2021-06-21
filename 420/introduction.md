# Introduction

## Symbolic vs. connectionist models

Computation could be thought of as either

* Continuous sequence of operations \(Turing machine! or modern CPU\)
  * Computer
    * Memory - static, addressable places
    * Processing - CPU with certain instructions to manipulate following a sequence of rules
    * Learning - Adding to / changing stored memory
  * Fast at doing exactly what you tell it, but needs explicit instructions!
* Connected graph of events that all feed into feature events \(Neural network!\)
  * Brain
    * Memory - patterns of activations over multiple neurons
    * Processing - associating patterns, settling to stable states, no 'rules'
    * Learning - modification of weights and biases
  * Map anything to anything

## Neural network

### Advantages

* Neural plausibility
* Parallel tasks inherent \(brain is slow, but does much more complex things in parallel compared to CPU\)
* Learn by example! Not a hardcoded sequence
* Content addressable memory \(Memory distributed accross neurons\)
  * A symbolic system has to learn certain steps
* Automatic generalisation \(learning more general patterns\)
* Robust \('better' than human in many different ways, but worse in others\)
  * But can sometimes learn the wrong things... i.e. every picture of a car is on a road so it learns the road is a car..

### Architecture

* Layers, number of units, starting weights
* Not learnable \(unless you use a neural net / genetic algorithm to develop neural nets\)

### Representation

* Many layers, many connections per layer
  * What does one neuron do?
  * How do they

### Processing

* Each layer is a weight matrix, each layer has bias vector too
* Can process multiple matricies at once \(batching\)

### Learning

* Backpropagation
  * Given an input, outputs something.
  * If the output is wrong, go backwards through the network in order to reduce the error of the output
  * Each neuron should take it's share of the blame
  * **Doesn't seem biologically plausible**

### Disadvantages

* Distributed representation \(Good for GPU training..\)
* Uniqueness \(Training from different initial weights will be slightly different..\)
* Modification \(How to adjust it to do something new?
* Interpretation and explanation \(Very hard to tell what it does!\)

## History

_a brief recap_

* 1969: Minsky & Papert, 'Perceptron'
* 1974: Werbos, backpropagation of error
* 1979: Miyake & Ito, neocognitron \(precursor to CNN\)
* 1986: Rumelhart, Hinton & Williams, backpropogation popularised
* 1990: Elman, simple recurrent neural network
* 1995: Cortes & Vapnik: Support Vector Machines
* 1997: Hochreiter & Schmidhuber, Long Short-Term Memory \(LSTM\) networks
* 1998: LeCun, convolutional neural network
* 2012: Krizhevsky, AlexNet
* 2014: Goodfellow.etal, Generative Adversarial Nets \(GAN\)
* 2015: Google Deep Mind’s AlphaGo
* 2017: Google researchers create Transformer Networks
* 2018: Generative Pre-trained Transformer \(GPT\) 2

and more...











