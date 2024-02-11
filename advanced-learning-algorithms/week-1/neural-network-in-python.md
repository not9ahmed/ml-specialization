# Neural Network Implementation in Python

Getting into further details of the neural networks algorithms without the complete use of Tensorflow.


## Forward Prop in Single Layer


### Forward Prop (Coffe Roasting Model)


![](images)

The following expression $w_{1}^{[2]}$ will be represented as w2_1. So the first number is superscrit, and _1 is the subscript.


```python
# 1D np Vector and not [[]] like in tensorflow which is a matrix
x = np.array([200, 17])


```


For the first neuron in the layer the following formula will be used:
$$
a^{[1]}_{1} = g(\vec{W}_{1} \cdot \vec{X} + b^{[1]}_{1})
$$



 
Notes for code variable w1_1,... a1_1:
- First number indicates superscript => Layer
- Second number indicates subscript => neuron

To compute $a^{[1]}_{1}$ we have the following parameters: 
```python
# the 2 parameters for the first neuron
w1_1 = np.array([1, 2])
b1_1 = np.array([-1])

# x is the one example which is from the previous code block
z1_1 = np.dot(w1_1, x) + b1_1


# applying the sigmoid to the z1_1 value
a1_1 = sigmoid(z1_1)
```










## General Implementation of Forward Propagation

