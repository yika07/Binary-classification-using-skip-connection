# Binary-classification-using-skip-connection

The IRIS dataset consists of 3 classes of flowers with 4 features each. With this model, I only look at two of the classes in order to do binary classificaiton. 
The neural netwok is composed of 1 input layers with 4 nodes, 1 hidden layer with 4 nodes and 1 output layer with 2 nodes. 
Skip connections are added from the input layer to the hidden layer so the value given to the nodes inside the hidden layer is of the form F(x1) + x1 where F() is the activation function used for the hidden layer and x1 the output of the first layer. 


Skip connections allow for a smoother loss landscape (as shown in this paper: https://arxiv.org/abs/1712.09913) which makes the optimizer converge faster. 
With this model, I managed to get 0% of training loss on the training set and 100% accuracy on both the training set and the test set after 9 epochs only. 
