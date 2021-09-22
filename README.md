# Binary-classification-using-skip-connection

The IRIS dataset consists of 3 classes of flowers with 4 features each. With this model, I only look at two of the classes in order to do binary classificaiton using a multilayer perceptron (MLP).


The neural netwok is composed of 3 fully-connected layers; the neural network has 4 input-nodes (because of the 4 features used to describe each label) and has 2 output-nodes corresponding to the 2 classes that are being used. 

Descirption of the forward pass and the skip connections: 

Let's define "A" as a parameter, "X" as a feature and "B" a bias. The goal is to find the right values for A and B to be able to classify the data properly. 
When the data are being processed through the first layer and the first activation function, we get an output value X1 = F1(A1*X+B1) where F1 corresponds to the RELU activation function. 

Skip connections are added for the second layer. When the data are passed through the second layer before the activation function, we have something of the form A2*X1+B2. That value is passed through the TANH activation function F2, so we get something of the form F2(A2*X1+B2); but the output obtained at the first layer is added to that value so we get X2 = F2(A2*X1+B2) + X1. That operation corresponds to adding skip connections to the model. 

For the last layer, the output is simply X3 = (A3*X2+B3)^2.



Skip connections allow for a smoother loss landscape (as shown in this paper: https://arxiv.org/abs/1712.09913) which makes the optimizer converge faster. 
With this model, I managed to get 0% of training loss on the training set and 100% accuracy on both the training set and the test set after 9 epochs only. 
