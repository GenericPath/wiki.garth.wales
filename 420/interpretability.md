---
description: How do neural networks 'think'?
---

# Interpretability

Datasets have incorrect labels! How do you get 99% accuracy when 3% of test data is incorrect?  
[https://labelerrors.com/paper.pdf](https://labelerrors.com/paper.pdf)

Artificial intelligence

* Thinking like humans
* Acting like humans
* Thinking rationally
* Acting rationally

## Adversarial examples

* Small changes in pixels.. or noise.. or specific designed patters can be detected with a high accuracy of being something a human wouldn't think they were.



## How they 'think'

{% hint style="info" %}
**Sensitivity**  
Track input attributes that changed slightly have large effect on neuron's activity
{% endhint %}

{% hint style="info" %}
**Decomposition / attribution**  
Track input attributes that are the main contributor to neuron's activity
{% endhint %}

### Gradient based methods

* Gradient - true sensitivity
* Integrated gradient: interpolate over input \(e.g. from black image to fully exposed\)
  * Compute gradients of output with respect to weights for each image and sum it up

### Activation maximisation

* Adversarial image generation to train from noise to image that maximises neuron
* Use regularises to 'guide' the maximisation process
* Use priors \(images\) to change starting point of maximisation process

### DeConvNet

* Reverse mapping through 'deconvolution'
* Unpooling by tracking location of the winning unit in the pooling layer
* Rectifications - only track positive activity
* Deconvolve - get an inverse of convolution through a weight matrix transpose \(assume weight vectors on neurons are orthogonal\)

### Layerwise Relevance Propagation

* Reverse mapping through 'backpropagation'
* Track 'responsibility' or 'relavance' of each input for activation
* Relevance rules - e.g. only track positive activity
* Deep Taylor Decomposition \(DTD\) - generalisation of LRP revelance rule to Taylor expansion around 'root point' determines relavance rule

### PatternNet & PatternAttribution



### Other



### Generative adversarial network \(GAN\)





