# Neural Networks Model

The Funedamental building block of modern Neural Network is layer of neurons, and putting them togther to form large neural network.

## Neural Network Layer

The following section will cover how a network layer works in details, with the hidden layers, logistic regression, and activation function.


**The layer number goes a follows:**  

- Layer 0: Input Layer and it's where the $\vec{X}$ reside
- Layer 1: Hidden Layer
- Layer 2: Output Layer


**To distunguish the layer the following notation for layer numbering:**  
Use superscript [layer number]
- such as $sample^{[1]}$ to denote the output of layer 1/ hidden layer.
- $sample^{[2]}$ to denote the output of layer 2/ output layer.




### Example:

The input layer will consist of $\vec{X}$, and contains 4 feature which are $x_{1}, x_{2}, x_{3}, x_{4}$.

$\vec{X} = [197, 184, 136, 214]$

Each neuron in the hidden layer implements logistic regression.

First neuron in the hidden layer has 2 parameters $\vec{W}_{1}, b_{1}$.

***Logitsic regression will be used across all the neurons!***
$$g(Z) = {1 \over {1 + e^{-Z}}}$$

**For first neuron $a_{1}$ in the layer 1/hidden layer:**

$neuron^{1}=> \vec{W}_{1}^{[1]} , \vec{b}_{1}^{[1]}$  
$$
a_{1}^{[1]} = g(\vec{W}_{1}^{[1]} \cdot \vec{X}_{1}^{[1]} + b_{1}^{[1]})
$$

$$
z_{1}^{[1]} = \vec{W}_{1}^{[1]} \cdot \vec{X}_{1}^{[1]} + b_{1}^{[1]}
$$

$$
a_{1}^{[1]} = 0.3
$$

**For second neuron $a_{2}$ in the layer 1/hidden layer:**

$neuron^{2}=> \vec{W}_{2}^{[1]} , \vec{b}_{1}^{[2]}$

$$
a_{2}^{[1]} = g(\vec{W}_{2}^{[1]} \cdot \vec{X}_{2}^{[1]} + b_{2}^{[1]})
$$

$$
z_{2}^{[1]} = \vec{W}_{2}^{[1]} \cdot \vec{X}_{2}^{[1]} + b_{2}^{[1]}
$$

$$
a_{2}^{[1]} = 0.7
$$

**For third neuron $a_{2}$ in the layer 1/hidden layer:**

$neuron^{2}=> \vec{W}_{3}^{[1]} , \vec{b}_{1}^{[1]}$

$$
a_{3}^{[1]}  = g(\vec{W}_{3}^{[1]} \cdot \vec{X}_{3}^{[1]} + b_{3}^{[1]})
$$

$$
z_{3}^{[1]} = \vec{W}_{3}^{[1]} \cdot \vec{X}_{3}^{[1]} + b_{3}^{[1]}
$$

$$
a_{3}^{[1]} = 0.2
$$


**These 3 value combine to create vector of activation values $\vec{a}$:**

Vector of activation values from layer 1
$
\vec{a}^{[1]} = [0.3, 0.7, 0.2]
$

Then the output of layer 1 or hidden layer $\vec{a}^{[1]}$ will be the input to layer 2!


The following image showcases the steps which were done in order to compute the activation of the each neurons in layer 1/ hidden layer, and the output will be a vector $\vec{a}^[1]$
![image of neural network layer1](images/NN-Layer-1.png)


**For the only neuron $a_{1}$ in the layer 2/output layer:**

The input to layer 2 is the output of layer 1!

$\vec{a}^{[1]} = [0.3, 0.7, 0.2]$

$neuron^{1}=> \vec{W}_{1}^{[2]} , \vec{b}_{1}^{[2]}$

$$
a_{1}^{[2]}  = g(\vec{W}_{1}^{[2]} \cdot \vec{a}_{1}^{[2]} + b_{1}^{[2]})
$$

$$
z_{1}^{[2]} = \vec{W}_{3}^{[2]} \cdot \vec{a}_{3}^{[2]} + b_{3}^{[2]}
$$

The value is scalar value, and this will be final output of the neural network
$$
a^{[2]} = 0.84
$$



The following image showcases the steps which were done in order to compute the activation of single neuron in layer 2/ output layer, and the output will be a vector $\vec{a}^[1]$
![image of neural network layer 2](images/NN-Layer-2.png)




## More Complex Neural Networks

## Inference: Making Prediction (Forward Propagation)

## Neurons and Layers