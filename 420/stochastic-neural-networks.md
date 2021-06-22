# Stochastic Neural Networks

## Hopfield network

A markov chain of neurons, settles to some final state.

* Only two states \(1 or -1 / black or white\)
* Connections both way with the same weight
  * w\_ij = w\_ji
* No neurons connect to themselves
  * w\_ii = 0
* Asynchronous operation
* sign\(_v_\) is the activation function

Can converge very quickly on a custom circuit \(but slow on CPU\)

* Will fall into some stable state \(attractors\)

Associative memory

* So given a prompt of part of a dog it will fall back into a state of a reconstructed dog

### Learning

Hebbian rule

* w\__ij = w\_ij + u\_ni x_\_nj

Capacity

* 0.138 U patterns for U neurons... \(correct patterns\)
* Essentially because it there is too much similarity because so many patterns will start with 110 it is difficult to get the correct one

Will learn spurious states

* Combined states of learned states or kinda random states

Slow in training and slow in evaluation \(will also have to settle to the state

## Boltzmann machine

_A stochastic hidden Hopfield network with hidden units_

Activation function is a sidmoid \(between 0 and 1\)

* Probability of neuron being switched on / off
* T is temperature - how gradual the change between states is

Could have a neuron for input and a neuron for output as the visible units

Anneal the T value, if you in theory cool the system at infinitely slow rate you get the absolute minimia \(but you cant really do that\)

* Design a schedule for this \(high T is stochastic, low T is deterministic\)
* Very slow to settle

### Learning

* Positive phase
  * ...
* Negative phase
  * ...

Takes forever to settle \(with simulated annealing\)

### Restricted boltzmann machine

\(i.e. all the non-connections are forced to be 0, you loose a lot of dynamics\)

* No connections between visible units
* No connections between hidden units
* Feedforward

Dynamics

* Easier / faster to train
* Not as powerful
* Autoencoder
  * Lots -&gt; little -&gt; lots \(A compression exercise, learn the important ascepts\)

_Don't need to know the learning with contrastive divergence stuff_

\_\_

## Deep Belief Network

* Contrastive divergence
* Stacked auto-encoders
* Fine tuned backprop
* Explaining away labels

First do unsupervised learning, then use those features to derive labels

* Essentially an autoencoder learning step by step, where the 'input' layer moves through the network. 
  * A series of restricted boltzmann machines.
  * Requires sigmoids \(can't use ReLU\)
  * Showed deeper doesn't make it worse
* Then you add the output neurons, and then use backpropagation.
  * Essentially a way of fine-tuning. This was better than SVM.
* Can be used to run computation backwards, to generate possible 'inputs'

## Modern Hopfield Network

Can learn more patterns than there are neurons

Kinda like a ReLU unit with some power ^ k

* Ali covers these in better detail in Ali's notes

May be useful for reinforcement applications due to its high capacity!

