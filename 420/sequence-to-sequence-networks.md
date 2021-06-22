# Sequence-to-sequence networks

A recurrent network is more accurate is D is large

Backpropagating through each layer is the repeated multiplication of hidden layer weights for hidden layer \(as they all share the same weight\). 

But if you multiple a matrix by itself multiple times the outcome depends on the eigenvalue:

eigenvalue &gt; 1, gradient will explode \(fix it by clipping weights\)  
eigenvalue = 1, gradient will propagate nicely  
eigenvalue &lt; 1, gradient will vanish

This was fixed with LSTM or GRU, and these networks were considered useful!

Also these recurrent networks are biased towards the end of the sentence.. \(can also do the otherway around and combine to be less biased\)

## Sequence-to-sequence

Input / output pairs

* Question / answer \(answering\)
* Long text / summary \(summarising\)
* English / french \(translation\)

Use a pair of networks - encoder and decoder

RNN learns a language model, give next word based on previous words  
Seq2Seq learns a conditional model, give net word based on previous words + a prompt

We want the best full sentence \(so use beamsearch to not do it greedily\)

## Attention

Seq2Seq gets all the information from encoder network _at one point in time_  


For an attention network, the decoder gets

* It's own previous internal state
* The last word it generated
* Weighted sum of internal states of the encoder network
  * So this gives us which words are likely to really matter for this words context

These also naturally produce good alignment charts to say what words are mapping onto the other words. Also here the network is shallower so less vanishing gradients problems!

## Transformer

Use attention to encode the input and decode the input!

* Attention network to map input sentence onto itself
* No RNN input - use word encodings
  * As such we also need to add positional embeddings
* Learning can be in parallel now for each word!
  * Basically an autoencoder without recurrent connections
* We want to learn rich representations
  * So use multiple self-attention layers in a feedforward manner
* We want to learn multiple _independent features_ of any given word
  * So use multiple-whole attention systems

Transformer is

* Multi-head attention
* Encoder attention links to decoder attention
  * Also they add skip connections to just about every layer
* Supports pre-training like convnets for vision!
  * Can be fine-tuned for specific task
  * Trained on much larger datasets and computers than most people have access to

**GPT-2** was trained on a massive corpus, with includes lots of prompts and their examples..

Dont specific input text and task, combine them!  
GPT-2 should therefore be able to perform many tasks without fine-tuning!

* Zero-shot learning
  * But it does these tasks _averagely_ unless fine-tuned like other networks..

**GPT-3** has a lot more parameters \(1.5 billion\) but basically the same as GPT-2

* few shot learning
  * Give it a number of examples and it will pick up what you want and then be able to answer more like it!











