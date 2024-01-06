# Multiple Linear Regression

Thie module will discusss Multiple features (variables)

<br/>

Previously, In One feature/ Univariate, Size in feet (x) and price (y)

The model will look like
$$f_{w,b}(x) = wx + b$$

![image of Single-Feature](images/Single-Feature.png)

<br/>

In Multiple Features (variables)

size in feet, number of bedroom, nimber of floors, age of home, price in $1000's

Features will be denoted by
$x_{1}, x_{2}, x_{3}, x_{4}$

$X_{j} = j^{th}$ Feature

$n =$ number of features

$\vec{X}^{(i)} =$ features of $i^{th}$ training example, which is a list or vector of features in one row of dataset. It is also called row vector. Example of $i =3$ which is row 2

$\vec{X}^{(2)} =$ [1416 3 2 40], the $\vec{X}$ represents a vector

$x_{j}^{(i)} =$ value of feature $j$ in the $i^{th}$ training example. Example $x_{3}^{(2)}$ will be row=2 and column=3 (or feature 3)

Screenshot of an example of multiple features dataset
![image of Multiple-Features](images/Multiple-Features.png)

<br/>
<br/>

For housing pricing it can be observed that each feature effects the pricing as the following.

- The size increases the pricing by 0.1 $1000.
- The number of beddrooms increases the pricing by 4 * $1000.
- The number of floors increases the pricing by 10 * $1000.
- The number of years decreases the pricing by -2 * $2000.
- The base price starts of 80 assuming the rest of features is 0.

![image of House Model Example](images/House-Model-Example.png)

Previously the model 1 feature it was like this

$$f_{w,b}(X) = wx + b$$

For $n$ features the model will look like this

$$f_{\vec{w},b}(\vec{X}) = w_{1} x_{1} + w_{2} x_{2} + \dotso + w_{n} x_{n} + b$$

Parameters of the model:

Represents a vector of weights, and it is a row vector
$$\vec{w} = [w_{1} \space w_{2} \space w_{3} \space \dotso \space w_{n}]$$

$b$ is a number

Represents a vector of features, and it is a row vector
$$\vec{X} = [x_{1} \space x_{2} \space x_{3} \space \dotso \space x_{n}]$$

Rewriting the model, to represent the vector and it should be the below
<br/>
Where $\cdot$ represents a dot product from Linear Algebra

**Multiple Linear Regression:** Linear regession with multiple input variables

$$f_{\vec{w},b}(\vec{X}) = \vec{W} \cdot \vec{X}  + b = w_{1} x_{1} + w_{2} x_{2} + \dotso + w_{n} x_{n} + b$$

(It is NOT called multvariate regression and it something else)

**Vectorization** can be used which make it simple to implement this and other learning algorithms.

## Vectorization

- Will make code shorter
- It will make code run more effciently
- Take advantage of modern numerical linear algerbra libraries, and use GPU to speed up execute code

### Parameters and Features

$\vec{W} = [w_{1} \space  w_{3} \space w_{3}]$,    n=3

$b$ is bias and it is a number

$\vec{X} = [x_{1} \space  x_{3} \space x_{3}]$,    n=3

Linear Algebra: count from 1

Using NumPy Library in python

in python it starts from 0, so w[0], w[1], w[2]

```python
w = np.array([1.0, 2.5, -3.3])
b = 4
x = np.array([10, 20, 30])
```

code starts from 0

#### Without vectorization, n = 100,000 (bad)

$$f_{\vec{w},b}(\vec{X}) = w_{1} x_{1} + w_{2} x_{2}  + w_{3} x_{3} + b$$

```python
f = w[0] * x[0] +
    w[1] * x[1] +
    w[2] * x[2] + b
```

#### Without vectorization, but with for loop

$$f_{\vec{w},b}(\vec{X}) = \vec{W} \cdot \vec{X}  + b = w_{1} x_{1} + w_{2} x_{2} + \dotso + w_{n} x_{n} + b$$

$$f_{\vec{w},b}(\vec{X}) = (\sum\limits_{i = 1}^{n} {w_{j}} x_{j}) + b$$

$$\sum\limits_{i = 1}^{n} -> j =1 \dotso n$$
$j=1,2,4$

```range(0, n) -> j=0...n-1```

```python
f = 0
for j in range(0, n)
    f = f + w[j] * x[j]
f = f + b
```

#### vectorization, but with for loop

$$f_{\vec{w},b}(\vec{X}) = \vec{W} \cdot \vec{X}  + b$$

This implement $\cdot$ (dot product) in a vectorized implementation of product operation of $\vec{W}, \vec{X}$. It will run much faster, and the code will be much cleaner

**Reason:**
NumPy will be able to use parallel hardware to speedup execution.

```python
f = np.dot(w,x) + b
```

<br/>

The following screenshot shows example of running vectorization with the dot product in NumPy which runs faster than the other implementations.
![image of Vectorization](images/Vectorization.png)

