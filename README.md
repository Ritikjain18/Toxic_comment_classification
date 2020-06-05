# Toxic_comment_classification

## Toxic LSTM
The approach we are talking is to feed the comments into the LSTM as part of the neural network but we can't just feed the words as it is.
1)Tokenization-Need to break down the sentence into unique words.
["I","love","cats"]

2)Indexing-We put the words in a dictionary like structure and give them an index.
["I":1,"love":2,"cats":3]

3)Index Representation-We could represent the sequence of words in the comments in the form of index,and feed this chain of index into ourr LSTM.

But we have to feed a stream of data that has consistent length(fixed no. of features).
Like some comments are very long and some are very short. And this is why we use "padding". We could make the shorter sentences as long as the other by filling the shortfall by zeros.
But also on the other hand, we also have to trim the longer ones to the same length(maxlen) as the short ones.

In this case we have set the max length->200

We plot the histogram where it is seen that most of the sentences have length between 30 to 50.

## Model

The input into our networks are oour list of encoded sentences. We begin by defining an i/p layer that accepts sentences of maxlen=200

Empty space is telling keras to insert this no. automatically.

We pass it into our embedding layer. Words wmbedding are basically representation of text data in vectorized format.


First we have make use of tokenization to help us convert all the words to tokens/indexes. Then we feed it into Embedding Layer.

Embedding layer will internally maintain a lookup table, and the lookup table will map the index/token to a  vector,a nd that vector is what represent the word in the higher dimensional space.

Next we feed this into the LSTM layer. We set the LSTM to produce an output that has a dimension of 50. As we already know that LSTM,RNN works by recursively feeding the output of a previous network into the i/p of current network.

Before we could pass output to normal layer we need to reshape 3D tensor->2D tensor.

We use globalMaxPooling layer -We took the maximum value of each patch in the data.

We pass it to the Dropout layer which randomly "disable" same nodes. It could result in better generalizatio

