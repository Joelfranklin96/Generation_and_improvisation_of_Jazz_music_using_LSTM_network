# Generation and improvisation of Jazz music using LSTM network

1) The Jazz musical data were preprocessed into sequence of musical values (input X and output Y).
2) Input X was of shape (m,Tx,90) and output Y was of shape (Ty,m,90). The difference in the shapes of X and Y was because of the manner in which the 'Model' was structured for X to be fed and Y to be predicted. There were 90 unique values.
3) Utilized Keras with TensorFlow backend to develop and train an LSTM network, augmented with a fully connected dense layer on the sequence of musical values.
4) The output of a particular time step y<t> was assigned the value of x<t+1> and the LSTM network was trained with Adam optimization algorithm and cross entropy loss.
5) During the prediction, the y<t> was predicted. Since we applied softmax, y<t> is of shape (1,1,90) and it represents the probabilities of the 90 unique values. The index where the maximum value occurred was found and using this index, y<t> was converted into a one-hot vector.
6) The one hot y<t> vector was fed as input while predicting y<t+1> and the outputs were predicted in this manner.
7) These outputs were converted to produce novel Jazz music sequences.
