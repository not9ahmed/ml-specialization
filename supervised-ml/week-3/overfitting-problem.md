# The Problem of Overfitting


## Regression Example

In this section, we will see an example of different kind of fit of models to the training set on regression problem. Using the Housing prices example.

### Example 1: Underfit
**Algorithm has high Bias**  

$w_{1}x + b$

When the model does not fit the training set well.

- The learning algorithm has strong preconception/bias that the housing prices will be completely linear of the size.


### Example 2: Just Right
**Generalization, model preform well even on new dataset**  

$w_{1}x + w_{2}x^{2} + b$

When the model does fits the training set well.


### Example 3: Overfit
**Algorithm has high Variance**  

$w_{1}x + w_{2}x^{2} + w_{3}x^{3} + w_{4}x^{4} + b$

When the model does fit the training set ***extremely*** well

- Can Choose the parameters which results the cost being 0 on all training examples!!
- It cannot generalize to new examples which it have not seent before.
- Variance means the model tries so hard to hard to fit all the data.
- If training set little bit different, then the function that algorithm is trying yo fit will be different.

<br/>

The below image show cases how different type of model may fit the model, and the example in the middle is the best one.
![image of Regression Fit Example](images/Regression-Fit-Example.png)


## Classification

In this section, we will see an example of different kind of fit of models to the training set on classification problem. Using the Tumor Size example.

### Example 1: Underfit/ High Bias

The decision boundary is a line
- It does not fit the data very well

$z = w_{1} x_{1} + w_{2} x_{2} + b$

$f_{\vec{w},b} = g(z)$

$g$ is the sigmoid function


### Example 2: Just right

The decision boundary is a curve
- It does fit the data well
- Has higher level polynomial, but not a lot!

$z = w_{1} x_{1} + w_{2} x_{2} + w_{3} x_{1}^{2} + w_{4} x_{2}^{2} + w_{5} x_{1} x_{2} + b$

$f_{\vec{w},b} = g(z)$

$g$ is the sigmoid function


### Example 3: Overfitting/High Variance

The decision boundary is a very curvey line!
- It does fit the data perfectly.
- Has high level polynomial
- Cannot generalize to new training example

$z = w_{1} x_{1} + w_{2} x_{2} + w_{3} x_{1}^{2} x_{2}  + w_{4} x_{1}^{2} x_{2}^{2} + w_{5} x_{1}^{2} x_{2}^{3} + w_{6} x_{1}^{3} x_{2} + \dotso + b$

$f_{\vec{w},b} = g(z)$

$g$ is the sigmoid function

<br/>

Below image is ana example of classification problem with different models fit, and the example in the middle is the best model as it generalizes to new examples.
![image of Classification Example Fit](images/Classification-Example-Fit.png)


## Addressing Overfitting

Regularization to Reduce Overfitting



### Options to Overcome Overfitting


#### Option 1: Collect More Training Examples

With larger dataset, the learning model can fit function that it is less wiggly.

Can fit higher order polynomial or model with many features

If I have enough training examples, it would still be ok!

The below image showcases how increasing the number of training examples can resolve the overfitting problem
![image of Overfitting Option 1 more examples](images/Overfitting-Option-1.png)

<br/>

#### Option 2: Select Features to Include/Exclude

1. All features + insuffcient data => Overfitting

2. Selected Features (Size, bedrooms, age) => Just Right

**Feature Selection:**
Choosing the most appropriate set of features to use.

We will discuss algorithms that can identify the best features to use.

**Disadvantage:**
The algorithm may throw important set of information that I have about housing.  
Useful features could be lost



The image below showcases how feature selection can overcome the problem of overfitting.
![image of Overfitting Option 2 features selection](images/Overfitting-Option-2.png)


<br/>

#### Option 3: Regularization
**Reduce the size of parameters**

Encourages the learning algorithm to shrink the parameters value swithout demanding the parameters to be set 0.

Keeps all the features, but prevent the features from having overly large effect.

Smaller $w_{j}$ paramater $w_{1} \dotso w_{n}$

From:  
$f(x) = 28x - 385 x^{2} + 39 x^{3} - 174 x^{4} + 100$

To:  
$f(x) = 13x - 385 x^{2} + 0.0000014 x^{3} - 0.0001 x^{4} + 100$

The image below showcases how regulatization can overall improve the model overfitting issue, by shrinking the parameters $w_{j}$
![image of Overfitting Option 2 regularization](images/Overfitting-Option-3.png)


### Addressing Overfitting Recap:

**Options:**

1. Collect More Data
2. Select Features
   - Feature Selection (Course 2)
3. Reduce Size of Parameters
   - Regularization (Next Videos)

![image of Addressing Overfitting Summary](images/Addressing-Overfitting-Summary.png)


## Cost Function with Regularization

### Intitution

Make $w_{3}$, $w_{4}$ really small $(\approx 0)$

$min_{\vec{W},b} {1 \over 2m} \sum_{i=1}^{m} (f_{\vec{W},b}(\vec{X}^{(i)}) - y^{(i)})^{2}$

And I want to modify the cost function to fit the data by adding 
$+ 1000 w_{3}^{2} + 1000 w_{4}^{2}$

$min_{\vec{W},b} {1 \over 2m} \sum_{i=1}^{m} (f_{\vec{W},b}(\vec{X}^{(i)}) - y^{(i)})^{2} + 1000 w_{3}^{2} + 1000 w_{4}^{2}$

The model will be penelized/regularized if $w_{3}$ and $w_{4}$ are large

Because if I want to minimze the function $w_{3}$ and $w_{4}$ has to be small!!

The only way is to make $w_{3}, w_{4}$ small:

- $w_{3} = 0.001$
- $w_{4} = 0.002$

The result $w_{3}, w_{4}$ are close to 0, which is mean the two terms are somewhat canceled.

The fit to data much close to quadratic, but with small effect from $x^{3}, x^{4}$

The below image showcases how the regularization is done, and how little it effects the model when it's minimized.
![Image of the regulaization inituition](images/Regularization-Intitution.png)


### Regualrization

**Having small $w_{1}, w_{2}, w_{3},\dotso,w_{n},b$**

**Results:**  
- Simpler model
- Less likely to overfit

In the previous example we have penelized  
$w_{3} \approx 0$  
$w_{4} \approx 0$

Below is an example of housing price dataset with 100 features.

We have a lot of features, but we do not know which feature to penelize, so we penelize all the features/ $w_{j}$ parameters

Results smoother, less wiggly, and not prone to overfitting.

$n$ features, where $n= 100$

$w_{1}, w_{2}, \dotso , w_{100}, b$

<br/>

**To penelize all the parameters, we use the following formula:**

**Regularization Term is:** $+ {\lambda \over 2m} \sum_{j=1}^{n} w_{j}^{2}$"


$$
J(\vec{W},b) =
{1 \over 2m} \sum_{i=0}^{m} (f_{\vec{w},b}(\vec{x}^{(i)})
- y^{(i)})^{2} + {\lambda \over 2m} \sum_{j=1}^{n} w_{j}^{2}
$$

**$\lambda$:** Lambda, Regularization parameter  
$\lambda > 0$  
Similar to choosing learning rate $\alpha$, I now can choose lambda $\lambda$

$\lambda$ is divided by 2m, by scalling both terms the same way:
- makes choosing good values $\lambda$ easier
- Even if training set grows $n$ is the same value for $\lambda$ still works

$b$ is mostly not used in the regularization, but when used it looks like this:

**$b$ Regularization Term:**
${\lambda \over 2m}b^{2}$

$$
J(\vec{W},b) =
{1 \over 2m}
\sum_{i=0}^{m} (f_{\vec{w},b}(\vec{x}^{(i)})
- y^{(i)})^{2}
+ {\lambda \over 2m} \sum_{j=1}^{n} w_{j}^{2}
+ {\lambda \over 2m}b^{2}
$$

The below image showcases the regularizations term for $w_{j}$ and $b$, they both introduce new value named $\lambda$
![Image of the regulaization terms](images/Regularization-Terms.png)


### Regualrization Continued

$$
min_{\vec{W},b}
J(\vec{W},b) =
min_{\vec{W},b}
({1 \over 2m} \sum_{i=0}^{m} (f_{\vec{w},b}(\vec{x}^{(i)})
- y^{(i)})^{2} + {\lambda \over 2m} \sum_{j=1}^{n} w_{j}^{2}
+ {\lambda \over 2m}b^{2})
$$

The cost function can be define as (1) + (2):  
- The (1) is the mean squared error, the goal to fit the data
- The (2) is the regularization term for $w_{j}$, the goal to keep $w_{j}$ small


$\lambda$ values specifies relative importance/tradeoff on how to balance the 2 goals:
- Mean Squared Error: Fit Data
- Keep $w_{j}$ small

<br/>

**Example:** Choose $\lambda = 10^{10}$

$f_{\vec{W},b} (\vec{X}) = w_{1} x + w_{2} x^{2} + w_{3} x^{3} + w_{4} x^{4} + b$

$f_{\vec{W},b} (\vec{X}) = 0 + 0 + 0 + 0 + b$

$f_{\vec{W},b} (\vec{X}) = b$ => Underfit

and if $\lambda =0$ => it will Overfit!


In the following image we can observe thet there are now 2 terms in the cost function $J(\vec{W},b)$ which are the mean squared error, and regularization term. Choosing the right $\lambda$ is essential in order avoid the overfitting problem.
![image of regularization lambda](images/Regularization-Lambda.png)


**Question:** For a model that includes the regularization parameter $\lambda$ (lambda), increasing $\lambda$ will tend to…

**Answer:**  
Decrease the size of parameters $w_{1}, w_{2}, \dotso, w_{n}$, 

**Explaination:**  
Increasing the regularization parameter 
$\lambda$ lambda reduces overfitting by reducing the size of the parameters. For some parameters that are near zero, this reduces the effect of the associated features.


## Regularized Linear Regression

$$
min_{\vec{W},b} J(\vec{W},b) =
min_{\vec{W},b}(
{1 \over 2m}
{
   \sum_{i=1}^{m} (f_{\vec{W},b} (\vec{X}^{(i)})
   - y^{(i)})^{2}
}
+ {\lambda \over 2m}
{
   \sum_{j=1}^{n} {W_{j}^{2}}
})
$$

$\lambda$:  Regularization Parameter


$j = 1 \dotso n$

repeat {
$$
w_{j} = w_{j} - \alpha {
    {\partial}
    \over
    {\partial w_{j}}
    }J(\vec{W}, b)
    
    \leftarrow (1)
$$


$$
b = b - \alpha {
    {\partial}
    \over
    {\partial b}
    }J(\vec{W}, b)

    \leftarrow (2)
$$
} Simultaneous updates


The updated paraemeters for regularized linear regression are the same, but the cost is defined differently, due to the regularization term!


(1)
$$
    {
      {\partial}
      \over{
         \partial w_{j}
         }
    }J(\vec{W}, b)
    = {1 \over m} \sum_{i=1}^{m} (f_{\vec{W}, b} (\vec{X}^{(i)}) 
    - y^{(i)}) x_{j}^{(i)}
    + {\lambda \over m} W_{j}
$$
The regulariztion deriviate term has been added $(+ {\lambda \over m} W_{j})$ 


(2)
$$
    {
      {\partial}
      \over
      {\partial b}
    }J(\vec{W}, b)
    = {1 \over m} \sum_{i=1}^{m} (f_{\vec{W}, b} (\vec{X}^{(i)}) - y^{(i)})
$$
We don't have to regularize $b$


The below image showcases ho the gradient have changes slightly to accommodate the changes in the cost function, which resulted in adding the term $(+{\lambda \over m} W_{j})$
![image of the regualized linear regression](images/Regularized-Linear-Regression.png)



### Implementing Gradient Descent

repeat {
$$
w_{j} = w_{j}
   - \alpha {
   \Biggl[
    {1 \over m} \sum_{i=1}^{m} (f_{\vec{W}, b} (\vec{X}^{(i)}) 
    - y^{(i)}) x_{j}^{(i)}
    + {\lambda \over m} W_{j}
   \Biggr]
}
$$


$$
b = b - \alpha {
      \Biggl[
      {1 \over m} \sum_{i=1}^{m} (f_{\vec{W}, b} (\vec{X}^{(i)}) 
      - y^{(i)})
      \Biggr]
   }
$$
} Simultaneous updates for all these parameters


The below image showcases how  gradient descent is implemented with the regularized term for $W_{j}$, and how the new partial derivative of $J(\vec{W},b)$ is substituted in the gradient descent. The new term which was added is $(+ {\lambda \over m} W_{j})$
![image of implementing gradient descent](images/Implementing-Gradient-Descent.png)


### The below notes are the Maths behind Gradient Descent with Regularization Term formula:


By rearranging the formula, and moving the regularization term to be after the old $w_{j}$ term
$$
w_{j} = w_{j}
- \alpha {\lambda \over m} w_{j}
- \alpha {
    {1 \over m} \sum_{i=1}^{m} (f_{\vec{W}, b} (\vec{X}^{(i)}) 
    - y^{(i)}) x_{j}^{(i)}
}
$$

Then taking $W_{j}$ as a common factor from the first part, the fomrula should be the following
$$
w_{j} = w_{j} {
   (1 - \alpha {\lambda \over m})
}
- \alpha {
    {1 \over m} \sum_{i=1}^{m} (f_{\vec{W}, b} (\vec{X}^{(i)}) 
    - y^{(i)}) x_{j}^{(i)}
}
$$
Where the second term $\alpha{1 \over m}$ is the usual update which was covered before using regularization.

The term $"w_{j} {(1 - \alpha {\lambda \over m})}-"$ has been added to the original update term.


**Example of values of the parameters $\lambda, \alpha, m$ where $m$ is the number of examples:**

- $\lambda = 1$
- $\alpha = 0.01$
- $m =50$

$\alpha {\lambda \over m} = 0.01 {1 \over 50} = 0.0002$

$w_{j}(1 - \alpha {\lambda \over m} ) = w_{j}(1 - 0.0002) = w_{j}(0.9998)$

So on every iteration I'm taking the $w_{j}$ and multiplying it by 0.9998, before carrying the usual update.

This will resuling in shrinking the value of $w_{j}$ just by little bit (number slighlty less than 1).


The below image depcicts a simplification of the gradient descent updating terms. The final formula now has the regularization term in the start, and then subtracted by the usual update term.
![image of implementing gradient descent with simplified terms](images/Implementing-Gradient-Descent-Simplified.png)


### How we Got the Derivative Term

$$
{\partial \over {\partial w_{j}}} J(\vec{W},b) =
{\partial \over {\partial w_{j}}} \biggl[
   {1 \over {2m}}
   {\sum_{i=1}^{m} (f_{\vec{W},b} (\vec{X}^{(i)})
   - y^{(i)})^{2}
   + {\lambda \over 2m}
   {\sum_{j=1}^{n} w_{j}^{2}}
   }

\biggr]
$$

Where $f_{\vec{W},b} (\vec{X}^{(i)})$ is defined as $\vec{W} \cdot \vec{X}^{(i)} + b$

By the rules of calculas the derivatives look like this:

$$
   = {1 \over 2m} \sum_{i=1}^{m} 
   \biggl[
   (\vec{W} \cdot \vec{X}^{(i)} + b - y^{(i)}) 2 x_{j}^{(i)}
   \biggr]
   + {\lambda \over 2m} 2 w_{j}
$$
- Now it does not have the summation $\sum_{j=1}^{n}$ term for the regularization term.
- The 2 will be canceled out in the 2 terms.


The result now looks like this
$$
   = {1 \over m} \sum_{i=1}^{m} 
   \biggl[
   (\vec{W} \cdot \vec{X}^{(i)} + b - y^{(i)}) x_{j}^{(i)}
   \biggr]
   + {\lambda \over m} w_{j}
$$


Now we can substitute the $f_{\vec{W},b} (\vec{X}^{(i)})$ term again, and it should be the following formula
$$
   = {1 \over m} \sum_{i=1}^{m} 
   \biggl[
   (f_{\vec{W},b} (\vec{X}^{(i)}) - y^{(i)}) x_{j}^{(i)}
   \biggr]
   + {\lambda \over m} w_{j}
$$

The term above is used for computing the gradient for regularized linear regression.

It can reduce the overfitting, on relatiely small dataset.


## Regularized Logistic Regression

High order polynomial that will be passed to sigmoid function
$$
z = w_{1} x_{1} + w_{2} x_{2} + w_{3} x_{1}^{2} x_{2}
+ w_{4} x_{1}^{2} x_{2}^{2} + w_{5} x_{1}^{2} x_{2}^{3} + \dots
+ b
$$

$$
f_{\vec{W},b} = {1 \over {1 + e^{-z}}}
$$

The decision boundary will end up being overly complex.

**Cost function:**
$$
J(\vec{W},b) = 
-{1 \over m}
\sum_{i=1}^{m}
   \Biggl[- y^{(i)}
   \log
      \biggl(
      f_{\mathbf{w},b}(\mathbf{\vec{X}}^{(i)})
      \biggr)
   - (1-y^{(i)})
   \log
      \biggl(1 - f_{\mathbf{w},b}( \mathbf{\vec{X}}^{(i)} ) \biggr)
   \Biggr]
+ {\lambda \over 2m} \sum_{j=1}^{n} {w_{j}^2}
$$


Where the new add $+ {\lambda \over 2m} \sum_{j=1}^{n} {w_{j}^2}$
is the regularization term.


$min_{\vec{W},b} \rightarrow w_{j} \downarrow$ prevents the parameters $w_{1}, w_{2}, \dotso w_{n}$ from being too large.

Even though I'm fitting high order poly with a lot of parameter, the decision boundary still looks simpler, and generalizes to new examples.


The below image showcases the regularized logistic regression cost function which not it contains the term $+ {\lambda \over 2m} \sum_{j=1}^{n} {w_{j}^2}$, and it help preventing the decision boundary from being very complex!
![image of regularized logistic regression](images/Regularized-Logistic-Regression.png)

<br/>

## Regularized Logistic Regression - Gradient Descent


**Cost function:**
$$
min_{\vec{W},b}
J(\vec{W},b) = 
-{1 \over m}
\sum_{i=1}^{m}
   \Biggl[- y^{(i)}
   \log
      \biggl(
      f_{\mathbf{w},b}(\mathbf{\vec{X}}^{(i)})
      \biggr)
   - (1-y^{(i)})
   \log
      \biggl(1 - f_{\mathbf{w},b}( \mathbf{\vec{X}}^{(i)} ) \biggr)
   \Biggr]
+ {\lambda \over 2m} \sum_{j=1}^{n} {w_{j}^2}
$$


**(Same as updated rules for the Regularized Linear Regression)**  
$j = 1 \dotso n$

repeat {
$$
w_{j} = w_{j} - \alpha {
    {\partial}
    \over
    {\partial w_{j}}
    }J(\vec{W}, b)
    
    \leftarrow (1)
$$


$$
b = b - \alpha {
    {\partial}
    \over
    {\partial b}
    }J(\vec{W}, b)

    \leftarrow (2)
$$
} Simultaneous updates


The updated paraemeters for regularized logistic regression are the same as linear regression, but the cost is defined differently, due to the regularization term!

**(Same as linear regression)**

However, the term $f_{\vec{W},b} (\vec{X}^{(i)})$ is using logistic regression/ sigmoid function/$g(z)$

(1)
$$
    {
      {\partial}
      \over{
         \partial w_{j}
         }
    }J(\vec{W}, b)
    = {1 \over m} \sum_{i=1}^{m} (f_{\vec{W}, b} (\vec{X}^{(i)}) 
    - y^{(i)}) x_{j}^{(i)}
    + {\lambda \over m} W_{j}
$$
The regulariztion deriviate term has been added $(+ {\lambda \over m} W_{j})$  


(2)
$$
    {
      {\partial}
      \over
      {\partial b}
    }J(\vec{W}, b)
    = {1 \over m} \sum_{i=1}^{m} (f_{\vec{W}, b} (\vec{X}^{(i)}) - y^{(i)})
$$
We don't have to regularize $b$



The below image displays how we are updating the parameters in a regularized logistic regression:
- Only the following term $(+ {\lambda \over m} W_{j})$ has been added to the $w_{j}$ gradient descent term.  
- Plus, the key difference here and regularized linear regression is that $f_{\vec{W},b} (\vec{X}^{(i)})$ being the sigmoid/logistic regression/$g(z)$.
![image of regularized logistic function with gradient descent](images/Regularized-Logistic-Function-Continued.png)

<br/>

The below image gives a question on the key difference between regularized linear regression and regularized logistic regression.
![image of video question on regularized logistic regression](images/Regularized-Logistic-Regression-Question.png)





## Topics to Learn

- 