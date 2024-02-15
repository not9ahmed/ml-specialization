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


### Output Layer

Depending on the target/ ground truth for target $y$.

Choosing $g(z)$ for output layer

$$
a^{[3]} = f(\vec{X})
$$

$$
f(\vec{X}) = a^{[3]}_{1} = g(Z^{[3]}_{1})
$$

**Binary Classification Problem - sigmoid**  
- There are 2 possible answers in the target label
- y = 0/1

**Regression Problem - Linear Activation Function**   
- There are more than 2 possible answers in the target label (positve/negative values)
- y = +/-

**Regression - ReLU**  
- Takes only on non negative values
- y = 0 or +


All the output layer activation functions depend on the $y$ value which is predicting
![image of the activation layer to choose for output layer](images/Output-Layer.png)


### Hidden Layer

Choosing $g(z)$ for hidden layer

$$
a^{[1]}
$$

$$
a^{[2]}
$$


**ReLU**  
- Most common choice for for the hidden layers  
- $g(z) = max(0,z)$
- A bit faster as it's simple expression
- Goes flat in one part, and other part is not flat
- Gradient descent is faster, so faster learning


**Sigmoid**  
- It was used before, but now it's very rare
- $g(z) = {1 \over {1 + e^{-z}}}$
- Less efficient
- Flat on both sides
- Gradient descent will be slower, so slower learning


The image below showcases that the most common choice for activation function is ReLU as it's faster in gradient descent. Due to having one side of the value being not flat.
![image of activation functions in hidden layer](images/Hidden-Layer.png)


### Choosing Activation Summary

The below is the general guide to follow when choosing activation function in a layer.

**For Output Layer:**
1. Binary Classification, $y = 0/1 $
   - activation = 'sigmoid'
2. Regression, $y$ negative/positive
   - activation = 'linear'
3. Regession, $y \ge 0$
   - activation = 'relu'


**For Hidden Layer:**  
ReLU as the default activation function
   - activation = 'relu'

Sample Code
```python
from tf.keras.layer import Dense

model = Sequential([
    # layer 1
    Dense(units=25, activation='relu'),
    
    # layer 2
    Dense(units=15, activation='relu'),
    
    # layer 3/output layer
    # or linear/ or relu
    Dense(units=1, activation='sigmoid'),
])
```

**Other Activation Function:**  
- Tanh
- LeakyReLU
- Swish




The below image summarizes the activation choice to be used in each layer of the neural network.
![image of the choosing activation summmary](images/Choosing-Activation-Summary.png)



## Why Do We Need Activation Functions