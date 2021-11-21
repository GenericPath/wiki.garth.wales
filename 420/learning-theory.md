---
description: How do we know we have found the correct patterns?
---

# Learning theory

## Learners performance

{% hint style="info" %}
**Supervised learning**\
The task in supervised learning is to find _f(x,w)_ such that it models the relationship between a given input _x_ and output _y._
{% endhint %}

Loss function _L(f(x,w), y) _gives learner a score for a set of values _w_

* Classification&#x20;
  * L =
    * 0 if _f(x,w) = y_
    * 1 if _f(x,w) != y_
* Regression (MSE)
  * L=(_f(x,w)-y_)_^2_
  * Regression punishes if wrong
* Cross-entropy (CE)
  * L = -y ln _f(x,w)_ - (1-_y_) ln (1-_f(x,w)_)
  * Encourages if correct



Training we modify _w_ so as to minimise L

### Risk

{% hint style="warning" %}
**True risk**\
****True risk is the expectation of the loss (performance of the hypothesis on all possible data)

_**Not computable!**_
{% endhint %}

{% hint style="success" %}
**Empirical risk**\
****Empirical risk is the average of the loss computed from available data (performance of the hypothesis on the data we have)

_Can be computed!_
{% endhint %}

### Generalisation

{% hint style="info" %}
**Consistency**\
****A hypothesis with a small empirical risk is _**consistent**_
{% endhint %}

{% hint style="info" %}
**Generalisation**\
****A hypothesis where empirical risk approximates true risk is said to _**generalise well**_
{% endhint %}

But we can't compute true risk so we can't guarantee generalisation

{% hint style="info" %}
**Hoeffding's inequality**\
****This inequality gives an upper bound in probability of an average of _m_ samples being different from the expectation of the corresponding random variable by more than _e_

𝑃(𝐴\_𝑚 ≤𝐸\[𝐴\_𝑚] −𝜖) ≤𝑒_^(_−2𝑚𝜖^2)\

{% endhint %}

We can then substitute empirical risk for A\_m

* Giving us the probability of empirical risk being more than 𝜖 outside of true risk

The expression of ln| _H _| is a rough measure of complexity of _H._\
A more accurate measure of complexity of a hypothesis space is VC-dimension, denotes as _d_. With VC-dimension complexity mesure we have:

* True risk <= empirical risk + O(_some equation to be filled in_)
  * with probability 1-q

{% hint style="info" %}
**Generalisation principle**\
Choosing a hypothesis space with a smallest VC-dimension guarantees (in probability) better generalisation. In other words, the simpler the model, the better chance of generalisation.
{% endhint %}

### VC-dimension

VC-dimension is the maximum number of points that a hypothesis can _shatter_. It measures the complexity of a hypothesis space in terms of it's representational power.

* e.g. a line can shatter three points but not four

#### Neural networks and VC-dimension

* _Neural networks: d_ <= O(number of parameters squared)
* _ReLU NN: d _<= (parameters)(layers)(log(parameters))
* Deep vs shallow
  * A single hidden layer neural network is a universal function approximator
  * Single both shalow and deep can do anything, why deep?
  * For some problems, the deeper network has a lower VC-dimension so generalises better
    * But deep networks can also fit random patterns easily

Reducing complexity of neural networks

* Regularisation
  * Penality for complexity of neural network factored into optimised cost/loss function
    * Weight decay
* Constraints imposed on the model limit its representational power
  * Dropout (chance for a neuron/unit to do nothing for an iteration of learning)
  * Batch normalisation (standardises the inputs, makes it easier to learn)

****



