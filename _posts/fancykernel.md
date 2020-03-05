---
layout: post
title: Fancy kernels
---


Your fancy neural network is just another kernel on steroid, mapping from pixels or words space into a linearly separable Euclidean space, train jointly with linear decision function.


Just before the final activation, everything is suppose to be linear.


One nice trick to examine the last layer is to chop off the activation, run the samples throught the network and obtain the feature space. Then fit good od Skelearn linear regression on that. You got yourself the same result.


Then you can calculate the distance of each sample to the decision boundary and see where things gone wrong.

Rambling a bit, most of the advancements on NeuralNets boil down to: Automatic and fast gradient computation, dynamically constructable graph ( Convolution operation, gated units...) and faster GPUs.
That's super watering down, I know. But F** me, right, what do I know.