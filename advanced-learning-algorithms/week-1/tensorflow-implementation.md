# Tensorflow Implementation

The following module will primarly focus converting neural networks into tensorflow code

## Inference in Code

The following secion will go into details how we can convert neural network architecture into a tensorflow code for 2 examples what are the Coffee Roasting, and Digit Classification

### Coffee Roasting Example

Will showcase an example of how machine learning model can be used to optimize the quality of roasted beans 

**2 Parameters which can be controlled:**
- Temperature (Celsius): Heating up the coffee beans
- Duration (Minutes): How long the coffee beans can be roasted


$y=1$, Good Coffee
$y=0$, Bad Coffee


**Possible Scenarios:**
- Very low temperature $\rightarrow$ will be not unroasted  
- Too short duration of time $\rightarrow$ will be unroasted  
- Very High temperature $\rightarrow$ will be overcooked
- Too Long duration of time  $\rightarrow$ will be overcooked


The below image illustrates how coffee roasting 2 parameters may affect the coffee quality.
![image of coffee roasting problem](images/Coffee-Roasting-1.png)



### Build the Model using Tensorflow

The following section will implement the simple neural network/ logistic regression to the coffee roast problem.



```python
# create np 2D input vector of 2 features
# with shape (1,2) => 1 row, 2 columns => 1 example, 2 features
X = np.array([[200.0, 17.0]])

# unit is the number of neurons
# activation is activation function which is sigmoid like logistic regression
# Dense is another name for layers, and there are others
layer_1 = Dense(units=3, activation='sigmoid')

# layer_1 is a function
# passing the X input tensor to that function
# will be tensor of 3 number, because of the unit=3
# output= [0.2 0.7 0,3]
a1 = layer_1(X)


# will be the output layer
# single neuron in this layer with sigmoid activation
# output= [0.8]
layer_2 = Dense(unit=1, activation='sigmoid')


# threseholding/ converting output scalar to class
if a2 >=0.5:
    yhat = 1
else:
    yhat = 0

```


The following image shows how the model is converted into tensorflow code
![image of build the model using tensorflow](images/Build-Model-Using-TF.png)



### Model for Digit Classification

This section will discusses the previous digit classifcation problem 


```python
# input array of shape (64,)
# x is pixels intensity values
X = np.array([[0.0, ...,245, ..., 240, ...,0]])

### First Layer ###
# will have 25 units/neurons
# activation function = sigmoid
layer_1 = Dense(units=25, activation='sigmoid')

# carrying inference through layer 1
# output will be tensor/vector of 25 elements
a1 = layer_1(X)


### Second Layer ###
# will have 15 units/neurons
# activation function = sigmoid
layer_2 = Dense(units=15, activation='sigmoid')

# carrying inference through layer 1
# output will be tensor/vector of 25 elements
a2 = layer_2(a1)


### Third Layer / Output Layer ###
# will have 1 units/neurons
# activation function = sigmoid
layer_3 = Dense(units=1, activation='sigmoid')

# carrying inference through layer 1
# output will be tensor/vector of 25 elements
a3 = layer_2(a2)


# thresholding the values
# converting the probabilites into actual class
if a3 >= 0.5:
    yhat = 1
else:
    yhat = 0
```

The below image showcases how the digiti classification model in terms of code.
![image of Digit Classification Model](images/Digit-Classification-Model.png)



## Data in Tensorfllow


## Building a Neural Network

