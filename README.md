# Toxic_comment_classification

##Toxic LSTM
The approach we are talking is to feed the comments into the LSTM as part of the neural network but we can't just feed the words as it is.
1)Tokenization-Need to break down the sentence into unique words.
["I","love","cats"]

2)Indexing-We put the words in a dictionary like structure and give them an index.
["I":1,"love":2,"cats":3]

Index Representation-We could represent the sequence of words in the comments in the form of index,and feed this chain of index into ourr LSTM.

But we have to feed a stream of data that has consistent length(fixed no. of features).
Like some comments are very long and some are very short.

