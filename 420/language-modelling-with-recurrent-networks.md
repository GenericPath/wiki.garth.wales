# Language modelling with recurrent networks

Before neural networks there were _n-grams_

* Modelled frequency of word sequences from a corpus
  * Struggled with low likelihood words \(sparsity problem\)
    * Fixed slightly by smoothing and using backoff
      * e.g. add a small value to every count to avoid numerator of zero
      * e.g. 4-gram move to 5-gram
* These used one-hot representations so no symantic relationships or word embeddings

## Recurrent network

current -&gt; hidden -&gt; predicted word  
                   ^ + previous step

Recurrent network learnt word embeddings in its hidden layer \(similar words / contexts predict similar next words!\)

 But an Elman network only looks back one time step

### Unfolding \(Backpropagation through time\)

* Choose a depth _D_
* Break corpus into sub-sequences of _D+1_
* Same weights for all of the hidden layer and other bits

But as you train, the gradients get smaller as we propagate to earlier words making it hard to capture _long distance dependencies_ in text.

## Evaluate a language model

{% hint style="info" %}
**Perplexity**  
Allows you to evalute a model.. maths goes here..
{% endhint %}

