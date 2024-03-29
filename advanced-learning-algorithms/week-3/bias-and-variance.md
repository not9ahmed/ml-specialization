# Bias And Variance


## Diaganosing Bias and Variance


### Bias/Variance

Looking athe Bias and Variance of learning algorithms gives a good guidance on what to do next.

For simple feature it's easy to diagnoise to find the algorithm performance.

Systematic way to find the algorithm performance is by looking at the training set and cross validation set.


#### High Bias (Underfit)

$f_{\vec{W},b} = w_{1} x + b$  
$d=1$  
$J_{train}$ is high  
$J_{cv}$ is high

#### Just Right

$f_{\vec{W},b} = w_{1} x + w_{2} x^{2} + b$  
$d=2$  
$J_{train}$ is low  
$J_{cv}$ is low

#### High Variance (Overfit)

$f_{\vec{W},b} = w_{1} x + w_{2} x^{2} + w_{3} x^{3} + w_{4} x^{4} + b$  
$d=4$  
$J_{train}$ is low  
$J_{cv}$ is high


The below image showcases a different apporach to determine if the learning algorithm is overfitting or underfitting from the $J_{train}$ and $J_{cv}$
![image of bias/varinace](images/Bias-Variance.png)


### Understanding Bias and Variance

On the x-axis the left side means a low degree polynomial d=1, and right is d=4

As the degree of polynomial increases, the $J_{train}$ decreases drastically.

For $J_{cv}$ if the degree is very low or too high, the $J_{cv}$ increases drastically, but in the middle it is the lowest. Right side is underfit, and right side is overfit.

![image of degree of poly and jtrain and jcv](images/Understanding-Bias-and-Variance.png)


### Diagonsing Bias and Varinace Summary

How do you tell if your algorithm has a bias or variance problem.

**High Bias(Underfit)**  
$J_{train}$ is high  
($J_{train} \approx J_{cv}$)


**High Variance(Overfit)**  
$J_{train} >> J_{train}$ [much greater]  
($J_{train}$ may be low)


**High Bias and High Variance**  
$J_{train}$ will be high  
and $J_{cv} >> J_{train}$

Don't happen that much in linear model applied in d=1.  

Overfits (High Bias) part of the input, and underfit (High Variance) part of the input. So it does bad in both dataset.

The below image summarizes the diagnosing bias and variance section.
![image of bias and variance](images/Bias-Variance-Summary.png)


## Regularization and Bias/Variance


### Linear Regression with Regularization

**Model:**  
$$
f_{\vec{W},b} (\vec{X}) = w_{1} x + w_{2} x^{2} + w_{3} x^{3} + + w_{4} x^{4} + b
$$


$$
J(\vec{W},b) =
{1 \over 2m}
\sum_{i=1}^{m}
\left(
    f_{\vec{W},b} (\vec{X}^{(i)}) - y^{(i)}
\right)^{2}
+ {\lambda \over 2m}
\sum_{j=1}^{n} w_{j}^{2}
$$


**$\lambda$ (Regularization parameter):**  
How much you trade-off the parameters w small versus versus fitting the training data well.


**Large lambda**  
**High Bias (Underfit)**  

- $J_{train} (\vec{W},b)$ is large
- $\lambda= 10,000 \;\;\; w_{1}\approx 0, w_{2}\approx 0$  
- Large lambda, the algorithm is motivated to keep parameters $w$ very small.  
- $f_{\vec{W},b} (\vec{}X) \approx b$



**Small lambda**  
**High Varaince (Overfit)**  

- $J_{train} (\vec{W},b)$ is small
- $J_{cv} (\vec{W},b)$ is large
- $\lambda= 0 \;\;\; w_{1}\approx 0, w_{2}\approx 0$  


**Intermediate $\lambda$**  

- $J_{train} (\vec{W},b)$ is small
- $J_{cv} (\vec{W},b)$ is small



![image of linear regression with regularization](images/Linear-Regression-with-Regularization.png)



### Choosing the Regularization Parameter $\lambda$

**Model:**  
$$
f_{\vec{W},b} = w_{1} x + w_{2} x^{2} + w_{3} x^{3} + w_{4} x^{4} + b
$$

1. Try $\lambda = 0 \rightarrow min_{\vec{W},b} J(\vec{W},b) \rightarrow w^{<1>}, b^{<1>} \rightarrow J_{cv} (W^{<1>}, b^{<1>})$

2. Try $\lambda = 0.01 \rightarrow min_{\vec{W},b} J(\vec{W},b) \rightarrow w^{<2>}, b^{<2>} \rightarrow J_{cv} (W^{<2>}, b^{<2>})$

3. Try $\lambda = 0.02 \rightarrow min_{\vec{W},b} J(\vec{W},b) \rightarrow w^{<3>}, b^{<3>} \rightarrow J_{cv} (W^{<3>}, b^{<3>})$

4. Try $\lambda = 0.04 \rightarrow J_{cv} (W^{<4>}, b^{<4>})$

5. Try $\lambda = 0.08 \rightarrow J_{cv} (W^{<5>}, b^{<5>})$


Pick $W^{<5>}, b^{<5>}$

Report test error: $J_{test} (W^{<5>}, b^{<5>})$

The same procedure which was used with polynomial degrees can be applied with regularization term in order to pick the best value.
![image of choosing the regularization term](images/Choosing-Reg-Param.png)


### Bias and Variance as a Fucntion of Regularization Parameter $\lambda$

$$
J(\vec{W},b) =
{1 \over 2m}
\sum_{i=1}^{m}
\left(
    f_{\vec{W},b} (\vec{X}^{(i)}) - y^{(i)}
\right)^{2}
+ {\lambda \over 2m}
\sum_{j=1}^{n} w_{j}^{2}
$$


As the $\lambda$ increases the $J_{train} (\vec{W},b)$ will increases. Also, $J_{cv}$ will increases, so it will result underfitting the data (high bias)

Meanwhile, as $\lambda$ decreases, $J_{train}$ will decreases. Also, $J_{cv}$ will decreases. So it will result in overfitting the data (high variance)

The graph is like a mirror of the degree of polynomial graph.

Cross Validation evaluating different values can help to choose good value for $d$ or $\lambda$

![image of choosing regularization term](images/Choosing-Reg-Summary.png)


## Establishing a Baseline Level of Performance

Concenrete numbres on $J_{train}$ & $J_{cv}$ to see if learning algorithm has high bias or high variance


### Speech Recognition Example

**Human Performance:** 10.6%  
Measure how well fluent speakers can transcript audiocips.
Can be bad due to bad audio

**Training Error $J_{train}$:** 10.8%   
What is the percentage of audioclips in data that algorithm doesn't transcript correctly.

- It does slightly worse (0.2%) than human peformance, which is very good.

**Cross Validation Error $J_{cv}$:** 14.8%

- It does worse with cv, and it has high variance problem, as it has 4.0% more error than training error.

So we conclude that that the learning algorithm has a high variance problem, and not high bias problem. (Overfitting)

![image of speech recognition example](images/Speech-Recognition-Example.png)



### Establishing Baseline level of Performance

What is the level of error you can reasonably hope to get?

- Human Level Performance
  - Good level when using unstructured data like audio, images or text.
- Competing algorithms performance
- Guess based on experience


### Bias/Varianace Examples


**To determine Bias:**  
Gap between Baseline performance and Training error $J_{train}$

**To determine Variance:**  
Gap between training error $J_{train}$ and cross validation error $J_{cv}$

We can have a learning algorithm with both high bias and high variance but it's a rare occurence.


The below image showcases an examples bias and variance problem by comparign with baseline performance. It concludes that the gap between each measure will determine the bias and variance of the learning algorithm.

![image of bias and variance example](images/Bias-Variance-Examples.png)


## Learning Curves

Learning curves are a way to understand how well the algorithm is doing as a function of the amount of experience/training examples it has.

$$
f_{\vec{W},b} = w_{1} x + w_{2} x^{2} + b
$$

$J_{train}$ = Training error  
$J_{cv}$ = Cross validation error  


As the training set gets bigger, the training error $J_{train}$ increases.


In the image below, it can be observed that the quadratic learning algorithm will fit the training set easily, and the error will be low or even close to 0. However, when add more training examples the algorithm will struggle to fit all the data points.

- Training error will be increase as the train set size increases.
- Cross validation error will decrease as the training set increases. Which is opposite of the training error learning curve.
![image of quadratic learning curve](images/Quadratic-Learning-Curve-Example.png)


### High Bias

$$
f_{\vec{W},b} = w_{1} x + b
$$

**If a learning algorithm has high bias, then getting more training examples will not help much in achieving baseline performance.**

The below image showcases a linear model with high bias learning curve. It can be observed than at certain point the 2 curves $J_{train}$ and $J_{cv}$ will flatten out, because the simple model will be unable to fit more datapoints, so it will not adjust that much.

The 2 learning curves will be very far from the human level performance
![image of high bias learning curve](images/High-Bias-Learning-Curve.png)


### High Variance

$$
f_{\vec{W},b} = w_{1} x + w_{2} x^{2} + w_{3} x^{3} + w_{4} x^{4} + b
$$
With small ($\lambda$)

Fits the data very well but does not generalize.

When the $J_{train}$ is much higher than $J_{cv}$, then it's good indicator that it suffers from high variance problem.

**If a learning algorithm suffers from high variance, getting more training data will help.**

The 2 learning curves have big gap which incidates high variance, but adding more training example will help in closing that gap. As a result, high variance problem can be resolved.
![image of high variance learning curve](images/High-Variance-Learning-Curve.png)

Plotting the learning curve have a downside, which it;s computationally expensive for training differnt size subset of dataset.

But it's good nonetheless, it's a good way to visualize high bias or high variance.


## Deciding What to Try Next

By looking at the plot training error & cross validation, we can determine the bias and variance of learning algorithm.


### Debugging a Learning Algorithm


Regularized Linear Regression on Housing prices 

$$
J(\vec{W},b) =
{1 \over 2m}
\sum_{i=1}^{m} (f_{\vec{W},b} (\vec{X}) - y^{(i)})^{2}
+ {\lambda \over 2m} \sum_{j=1}^{n} w_{j}^{2}
$$

But it makes large errors in predictions. What to try nex?

- Get more training examples
  - Fixes high variance/ ovetfitting

- Try smaller number of features ($x_{1}, x_{2}$)
  - Fixes high variance/ ovetfitting

- Try getting additional number of features
  - Fixes high bias/ underfitting, to improve performance on training examples

- Try adding polynomial features ($x_{1}^{2}, x_{2}^{2}, x_{1} x_{2}, etc$)
  - Fixes high bias/ underfitting, to improve performance on training examples

- Try decreasing $\lambda$
  - Fixes high bias/ underfitting, to improve performance on training examples

- Try increasing $\lambda$
  - Fixes high variance/ overfitting, to fit smoother less wiggly function


**These steps either fix high bias or high variance problem.**

![image of learning algorithms fixes](images/Debugging-Learning-Algorithm-Fixes.png)


## Bias/Variance and Neural Networks


### The Bias Variance Tradeoff


**Simple Model**  
High Bias  
$
f_{\vec{W},b} = w_{1} x + b
$

**Simple Model**  
High Bias  
$
f_{\vec{W},b} = w_{1} x + w_{2} x^{2} + b
$

**Complex Model**  
High Variance  
$
f_{\vec{W},b} = w_{1} x w_{2} + x^{2} + w_{3} x^{3} + w_{4} x^{4} + b
$


![image of bias variance tradeoff](images/Bias-Variance-Tradeoff.png)



### Neural Networks and Bias Variance

Large neural networks are low bias machines.

Meaning, it can always fit the training set, as long it's not enormous.


The following procedure can be followed in neural networks can be used in order to overcome the high bias and high variance problem:

1. Does NN do well on training set $J_{train} (\vec{W},b)$?

    - Yes: Got to Step 2
    - No: Make the network bigger by adding more hidden layer, or more units in the layers. It requires more computing resources.

2. Does it do well on the cross validation set $J_{cv} (\vec{W},b)$
    
    - Yes: Done!
    - No: Get more data, or have a bigger network and go again to Step 1.

![image of neural networks and bias variance](images/NN-and-Bias-Variance.png)


### Neural Networks and Regularization


A large neural network will usually do as well or better than smaller one so long as regularization is choosen appropriately.

The downside is, large neural networks are more computing resources due to the increased number of parameters to be trained.

![image of neural networks and regularzation](images/NN-and-Regularization.png)


$$
J(\vec{W},b) = 
{1 \over m}
\sum_{i=1}^{m} L(f(\vec{X}^{(i)}), y^{(i)})
+ {\lambda \over 2m} \sum_{\text{all weights W}} (w^{2})
$$


**Unregularized MNIST Model**

```python
layer_2 = Dense(units=15, activation="relu")
layer_1 = Dense(units=25, activation="relu")
layer_3 = Dense(units=1, activation="sigmoid")

model = Sequential([layer_1, layer_2, layer_3])
```


**Regularized MNIST Model**

```python
# L2 is lambda
# there are other types of regularizers

layer_1 = Dense(units=25, activation="relu", kernel_regularizer=L2(0.01))
layer_2 = Dense(units=15, activation="relu", kernel_regularizer=L2(0.01))
layer_3 = Dense(units=1, activation="sigmoid", kernel_regularizer=L2(0.01))

model = Sequential([layer_1, layer_2, layer_3])
```


![image of nn with regularization example](images/NN-Regularization-Example.png)


## Topics to Learn

- 