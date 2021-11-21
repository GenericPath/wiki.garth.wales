# Word Respresentation

How to encode words (the simple way)

* Onehot
  * Doesn't encode any _similarity relationships_ between words\
    Want apple to be a bit like bananna
  * There are a lot of words! So each word has to be a vector the length of all possible words

But we want a denser method, that encodes similarities.

* Cluster words based on usage
* Meanings best represented in a continuous space (instead of traditional discrete meaning)

Use a _language corpus_ (a sample of how language is used) to determine 'meaning'

Therefore we can get some 'Co-occurrence' based representations.

* Define a context of a word as the _n_ words around it (left and right)
  * Store as a matrix
  * N words gives a N-dimensional 'usage' space
  * Use PCA or SVD to reduce dimension
  * Each word is now a point in a lower dimensional space

### Word2Vec

* Iterate through each word in a corpus, progressively learn a probability model to predict words around it
* Use a _maximum likelihood_ approach
* No weights, only the vectors themselves
* Dot product produces similarities between two vectors (but with a bias twowards large magnitudes)
  * if w_1 and w_2 have similar context words then maximising both their similarity and their context words maximises w_1 and w_2

This was very powerful because it clusters similar meanings together, and made semantic relationships\
v\__woman - v\__man  gives a semantic change from man to woman (so apply to king to get queen!)

GloVe then made this a key feature to achieve both better.

* Focused on probability ratios

Words close together can be antonyms as well as synonyms

Words with multiple meanings may be close to difference groups of words in different 'directions' in embedding space

Embeddings incorporate human biases, present in the training corpus

