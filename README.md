# Binary-classification-using-skip-connection

The IRIS dataset consists of 3 classes of flowers with 4 features each. With this model, I only look at two of the classes in order to do binary classificaiton using a multilayer perceptron (MLP).


The neural netwok is composed of 3 fully-connected layers; the neural network has 4 input-nodes (because of the 4 features used to describe each label) and has 2 output-nodes corresponding to the 2 classes that are being used. 


Skip connections are added in the model. The skip connections are of the form F(fc2(x1))+x1. F(fc2(x1)) is the output of the second layer after being passed through the activation function and x1 corresponds to the output of the first layer. So, the skips connections add the output of the first layer to the output of the second layer. 

Skip connections allow for a smoother loss landscape (as shown in this paper: https://arxiv.org/abs/1712.09913) which makes the optimizer converge faster. 
With this model, I managed to get 0% of training loss on the training set and 100% accuracy on both the training set and the test set after 9 epochs only. 
