# Multiclass Classification

Classification problems where there is more than 2 possible classes.

## Multiclass


**Multiclass Classification Problem:**  
target $y$ can take on more than ***two*** possible values.


### Minist Example

**Examples:**
- Classifying number (0,1,2,3,4,5,6,7,8,9)
- Diagnosing problem (Many diseases)
- Visual Defect Inspection of Manufactury parts, discoloration, chipped

![image of multiclass problems](images/Mnist.png)


### Multiclass Classification Problem

Previously we had a dataset with 2 possible classes:
- $P(y = 1 | \vec{X})$
- not 1


Now with Multiclass:
- Class= 1, $P(y = 1 | \vec{X})$
- Class= 2, $P(y = 2 | \vec{X})$
- Class= 3, $P(y = 3 | \vec{X})$
- Class= 4, $P(y = 4 | \vec{X})$


The below image illustruates how the multiclass classification will work. It will have many decision boundaries to seperate each class of the dataset instead of one single line like before with logistic regression.
![image of multiclass classification example](images/Multiclass-Classification-Example.png)



## Softmax

Generalization of logistic regression (binary classification) to the multiclass context

### Logistic Regresion (2 Possible output values):

$$
z = \vec{W} \cdot \vec{X} + b
$$ 

**Probability of y=1:**
$$
a_{1} = g(z) = {1 \over {1 + e^{-z}}} = P(y=1 |\vec{X})
$$

**Probability of y=0:**
$$
a_{2} = 1 - a_{2} = P(y=0 |\vec{X})
$$

Logistic estimate of the probability that $y = 1$ given those input features $\vec{X}$

- $P(y=1 |\vec{X}) = 0.71$  
- $P(y=0 |\vec{X}) = 0.29$

The have to add up to 1!


### Softmax Regression (4 possible outputs)

$y=1,2,3,4$


**Class 1:**  
$$
z_{1} = \vec{W}_{1} \cdot \vec{X} + b_{1}
$$


$$
a_{1} = {
    {e^{z_{1}}}
    \over
    {e^{z_{1}} + e^{z_{2}} + e^{z_{3}} + e^{z_{4}}}
}
$$

$$
= P(y=1 | \vec{X}) = 0.30
$$


**Class 2:**  
$$
z_{1} = \vec{W}_{1} \cdot \vec{X} + b_{2}
$$


$$
a_{2} = {
    {e^{z_{2}}}
    \over
    {e^{z_{1}} + e^{z_{2}} + e^{z_{3}} + e^{z_{4}}}
}
$$

$$
= P(y=3 | \vec{X}) = 0.20
$$



**Class 3:**  
$$
z_{3} = \vec{W}_{3} \cdot \vec{X} + b_{3}
$$

$$
a_{3} = {
    {e^{z_{3}}}
    \over
    {e^{z_{1}} + e^{z_{2}} + e^{z_{3}} + e^{z_{4}}}
}
$$

$$
= P(y=3 | \vec{X}) = 0.15
$$


**Class 4:**  
$$
z_{4} = \vec{W}_{4} \cdot \vec{X} + b_{4}
$$

$$
a_{4} = {
    {e^{z_{4}}}
    \over
    {e^{z_{1}} + e^{z_{2}} + e^{z_{3}} + e^{z_{4}}}
}
$$

$$
= P(y=4 | \vec{X}) = 1 - (a_{1}+ a_{2} + a_{3})
$$

$$
= 1 -(0.30+0.20+0.15) = 1 - 0.65 =  0.35
$$


### Softmax Regression (No Possible Outputs)

$(y =1,2,3,4,N)$


**Where $j = 1,2,3,4..,N:**
$$
Z_{j} = \vec{W}_{j} \cdot \vec{X} + b_{j}
$$

Parameters:
- $w_{1}, w_{2},\dotso, w_{N}$
- $b_{1}, b_{2},\dotso, b_{N}$


$$
a_{j} = {
    {e^{Z_{j}}}
    \over
    {\sum_{k=1}^{N} {e^{Z_{k}}}}
}
= P(y=j | \vec{X})
$$


- $k$ to index to summation
- $a_{j}$ is the model estimate that y =j given the input feature $\vec{X}$


**Note:**  
$a_{1} + a_{2} + a_{3} + \dotso + a_{N} = 1$


The above formula can also work with 2 classes!  
it ends up being like logistic regression

![image of softmax formula](images/Softmax-Formula.png)


### Cost

#### Logistic Regression

$$
z = \vec{W} \cdot \vec{X} + b
$$

$$
a_{1} = g(z) = {1 over {1 + e^{-z}}} = P(y=1 | \vec{X})
$$

$$
a_{2} = 1 - a_{1} = P(y=1 | \vec{X})
$$


$$
loss = -y log(a_{1}) - (1 - y) log(1 - a_{1})
$$

By substituting $a_{2}$
$$
loss = -y log(a_{1}) - (1 - y) log(a_{2})
$$

if $y=1$ then:
- $-y log(a_{1})$

if $y=0$ then:
- $- (1 - y) log(a_{2})$


$J(\vec{W}, b)$ = average loss of the entire training set




#### Softmax Regression


$$
a_{1} = {
    {e^{z_{1}}}
    \over
    {e^{z_{1}} + e^{z_{2}} + e^{z_{3}} + e^{z_{4}}}
}
= P(y=1 | \vec{X})
$$
$$\dotso$$

$$
a_{N} = {
    {e^{z_{N}}}
    \over
    {e^{z_{1}} + e^{z_{2}} + e^{z_{3}} + e^{z_{N}}}
}
= P(y=N | \vec{X})
$$


The loss is taking the -log of the probability it thought y was N:
$$
loss (a_{1}, \dotso, a_{N}) = 
    \begin{cases}
    - \log\left(a_{1} \right) & \text{if $y=1$}\\
    - \log\left(a_{2} \right) & \text{if $y=2$}\\
    \dotso \\
    - \log\left(a_{N} \right) & \text{if $y=N$}\\
  \end{cases}
$$


**if $y =j$:**
- $loss = -log(a_{j})$


**If $a_{j}$ is low, then Loss is high!!**

**For computing the loss, we are computing for single $y$ prediction and not all!**


Teh following image summarizes the differences between Logistic Rgression Cost, and Sofmax Regression Cost.
![image of cost function for softmax regression](images/Cost.png)





## Neural Network with Softmax Output



## Improved Implementation of Softmax


## Classification with Multiple Outputs



## Topics to study
- 

