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





## Establishing a Baseline Level of Performance







## Learning Curves





## Deciding What to Try Next






## Bias/Variance and Neural Networks





## Topics to Learn

- 