# Neural Network Training

## Tensorflow Implementation


### Train a Neural Network in Tensorflow

We will be using the same example from week-1

Given set of (X, y) examples
How to build and train this code.


```python
import tensorflow as tf
from tf.keras import Sequential
from tf.keras.layers import Dense

# 1 creating model
model = Sequential([
    Dense(units=25, activation='sigmoid'),
    Dense(units=15, activation='sigmoid'),
    Dense(units=1, activation='sigmoid'),
])


# 2 defining which loss function to use
from tf.keras.losses import BinaryCrossentropy

model.compile(loss= BinaryCrossentropy())


# 3 fit the model using the loss which was specified in 2
# epochs: number of steps in gradient descent or other loss function
model.fit(X, Y, epochs=100)



```



## Training Details


