# Activation Functions



## Alternatives to the Sigmoid Functions


### Demand Prediction Example

Modeling awareness as no negative number

$$
Z = \vec{W^{[1]}_{2}} \cdot \vec{W} + b^{[1]}_{2}
$$

$$
a^{[1]}_{2} = g(z)
$$

$$
a^{[1]}_{2} = g(\vec{W^{[1]}_{2}} \cdot \vec{W} + b^{[1]}_{2})
$$


**Sigmoid Function:**
$$
g(z) = {1 \over {1 + e^{-z}}}
$$

$$
0 < g(z) < 1
$$


To allow value to be greater than 1, ReLU function can be used

**ReLU (Rectified Linear Unit):**
$$
g(z) = max(0,z)
$$

if $z < 0 \longrightarrow g(z)$ is 0  
if $z \ge 0 \longrightarrow g(z)$ is $z$


The below image showcases the example of demand prediction, which instead of using the sigmoid activation, we can use ReLU in order to consider values greater than 1.
![image of demand prediction example](images/Demand-Prediction-Example.png)


### Examples of Activation Functions


#### 1- Linear Activation Function

"No Activation Function"
Without using any activation, as if there is no $g(z)$

$$
g(z) = z
$$

$$
a = g(z) = z = \vec{W} \cdot \vec{X} + b
$$


#### 2- Sigmoid

$$
a^{[1]}_{2} = g(\vec{W^{[1]}_{2}} \cdot \vec{W} + b^{[1]}_{2})
$$

$$
0 < g(z) <1
$$


#### 3- ReLU (Recified Linear Unit)

$$
g(z) = max(0, z)
$$

if $z < 0 \longrightarrow g(z)$ is 0  
if $z \ge 0 \longrightarrow g(z)$ is $z$


The below image summarized the most common activation functions for neural networks.
![image of activation function examples](images/Activation-Functions-Examples.png)



## Choosing Activation Functions






## Why Do We Need Activation Functions