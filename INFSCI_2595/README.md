
# An Introduction to Neural Networks
2251 INFSCI 2595 SEC1050: Machine Learning

## Homework Objectives
In this homework, you will learn how to implement and train an entire MLP from scratch, on your
own. You will learn
– to write code for all the components that comprise a simple MLP;
– to chain these components up to actually compose a complete MLP of any depth;
– to implement losses to train the network parameters;
– how to backpropagate the derivatives of those losses through the network, to compute loss deriva-
tives with respect to all network parameters;
– how to incorporate those derivatives into stochastic gradient descent (SGD) to update network
parameters;
– how to implement at least one common regularization method, namely batch normalization, to
improve training.
This homework comes with an optional, separately posted bonus part, in which you will also learn to
implement other optimizers including ADAM, and another key regularization technique, dropout.