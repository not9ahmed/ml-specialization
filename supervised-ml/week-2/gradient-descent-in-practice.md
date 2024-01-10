# Gradient Descent in Practice

## Feature Scaling

Used to enable Gradient Descent to run faster

### Feature and parameter values

**Example**

price = $w_{1} x_{1} + w_{2} x_{2} + b$

$x_{1}=$ size (feet$^{2}$) -> Range: (300-2,000) Large

$x_{2}=$ #Bedrooms -> Range: (300-2,000) Small

<br/>

House : $x_{1} = 2000$, $x_{2} = 5$, price = $500K -> $y$ or target

Size of parameters $w_{1}, w_{2}$?

**Training Example 1:**

$w_{1} = 50$, $w_{2} = 0.1$, $b = 50$

price = $w_{1} x_{1} + w_{2} x_{2} + b$

price = $(50 * 2000) + (0.1 * 5) + 50$

- size = 50 * 2000 = $100,000K
- \# of rooms = (0.1 * 5) = $0.5K
- $b$ = $50K

price = $100,050.50K

Which is very far, so it is bad parameter choice

---

**Training Example 2:**

$w_{1}$ is small, and $w_{2}$ is large

$w_{1} = 0.1$, $w_{2} = 50$, $b = 50$

price = $w_{1} x_{1} + w_{2} x_{2} + b$

price = $(0.1 * 2000) + (50 * 5) + 50$

- size = 0.1 * 2000 = $200K
- \# of rooms = 50 * 5 = $250K
- $b$ = $50K

price = $500,000K

which is more reasonable

#### Conclusion

If the feature is of large value, the weight should be relativly small.
If the feature is of small value, the weight should be large.

![image of Feature Scaling](images/Feature-Scaling.png)

---

### Feature Scaling Relationship

**Ploting the features on scatter plot, we can observe the following:**

- Size in feet $x_{1}$ in the x-axis will have large range (300-2000), so the size of feature should be large.
- \# bedrooms $x_{2}$ in the y-axis will have small range (0-5), so the size of feature should be small.

**Ploting the parameters on contour plot, we can observe the following:**

- Size in feet parameter $w_{1}$ in the x-axis will have narrow range (0-1) horizontally. so the size of parameter should be small.
- \# bedrooms parameter $w_{2}$ in the y-axis will have large range (10-100) vertically. From the ellipses which are formed. So the size of feature should be large.

![image of Feature Scaling Relation](images/Feature-Scaling-Relation.png)

<br/>
<br/>

If the dataset is used as it is, and used gradient descent.

- It will jump back and forth to reach the minimum due to contours being tall and skinny. Which will take much more time find the global minimum.

**To resolve the problem:**

Scale the feature/ Performing Transformation to the data/ rescale

- The range for both features will have comparable range of values.

- Gradient descent was ran on Cost function the contour will look more like circle, and gradeint descent will find the path to global minimum much easier.

The following image showcases rescaling of features
![image of Feature Rescaling](images/Feature-Rescaling.png)

#### Feature Scaling is very important to speed up Gradient Descent

## Feature Scaling Works Examples

### Feature Scaling By Dividing by Max

Which divides the feature by the max value, and range will be between 0 and 1.

**Feature 1:**

$300 \le x_{1} \le 2000$, where 2000 is the max

$x_{1, scaled} = {x_{1}\over 2000}$

$0.15 \le x_{1,scaled} \le 1$

---

**Feature 2:**

$0 \le x_{2} \le 5$, where 5 is the max

$x_{2, scaled} = {x_{1}\over 5}$

$0 \le x_{2,scaled} \le 1$

The below image show cases how feature scaling by max value work.
It can distribute the number with range of 0 and 1
![image of Feature Scaling Example](images/Feature-Scaling-Example.png)

### Feature Scaling By Mean Normalization

Rescale the feature to be centered around 0, and range is within -1 and +1.

First find mean/average of a feature $\mu_{1}$

$\mu$: Mean

**Feature 1:**

$\mu_{1} = 600$

$300 \le x_{1} \le 2000$

$x_{1} = {{x_{1} - \mu_{1}} \over {max-min}}$

$x_{1} = {{x_{1} - 600} \over {2000-300}}$

$x_{1} = {{x_{1} - 600} \over {1700}}$

Substitute in the range

${{300 - 600} \over {1700}}\le x_{1} \le {{2000 - 600} \over {1700}}$

$-0.18 \le x_{1,scaled} \le 0.82$

---

**Feature 2:**

$\mu_{2} = 2.3$

$0 \le x_{2} \le 5$

$x_{2} = {{x_{2} - \mu_{1}} \over {max-min}}$

$x_{2} = {{x_{2} - 2.3} \over {5-0}}$

$x_{2} = {{x_{2} - 2.3} \over {5}}$

Substitute in the range

${{0 - 2.3} \over {5}}\le x_{2} \le {{5 - 2.3} \over {5}}$

$-0.46 \le x_{2,scaled} \le 0.54$

Below is an image which show features scalling with mean normalization  method
![image of Feature Scaling with Mean Normalization Example](images/Feature-Scaling-Mean-Example.png)

### Feature Scaling By Z-Score Normalization

We need to calculate Standard Deviation $\sigma$ fo each feature in order to compute Z-Score normalization.

Also, mean is needed to be calculated $\mu$

$\sigma$: Standard Deviation, Bell Curve, Gaussian Distribution, Normal Distribution

**Feature 1:**

$\mu_{1} = 600$

$\sigma_{1} = 450$

$300 \le x_{1} \le 2000$

$x_{1} = {{x_{1} - \mu_{1}} \over \sigma{1}}$

$x_{1} = {{x_{1} - 600} \over 450}$

Substitute in the range

${{300 - 600} \over 450}\le x_{1} \le {{2000 - 600} \over {450}}$

$-0.67 \le x_{1,scaled} \le 3.1$

---

**Feature 2:**

$\mu_{2} = 2.3$

$\sigma_{2} = 1.4$

$0 \le x_{2} \le 5$

$x_{2} = {{x_{2} - \mu_{2}} \over \sigma{2}}$

$x_{2} = {{x_{2} - 2.3} \over 1.4}$

Substitute in the range

${{0 - 2.3} \over 1.4}\le x_{2} \le {{5 - 2.3} \over {1.4}}$

$-1.64 \le x_{1,scaled} \le 1.93$

Below image showcase z-score normalization which takes into consideration the standard deviation $\sigma$ and mean $\mu$.
The range is within -3 and +3 unlike the mean which was in -1 and +1.
![image of Feature Scaling with Z-Score Normalization Example](images/Feature-Scaling-Z-Score-Example.png)

### Feature Scalling Aim

Aim for about the below ranges for each feature $x_{j}$

Accaptable Ranges:

- $-1 \le x_{j} \le 1$
- $-3 \le x_{j} \le 3$
- $-0.3 \le x_{j} \le 0.3$

Okay, no rescalling required:

- $0 \le x_{j} \le 3$
- $-2 \le x_{j} \le 0.5$

Too Large, and too small, both require scalling. Too large will cause gradient descent to run slow:

- $-100 \le x_{j} \le 100$, too large
- $-0.001 \le x_{j} \le 0.001$, too small
- $-98.6 \le x_{j} \le 105$, (temprature around 100) too large

<!-- study standard deviation -->



<!-- ## Checking Gradient Descent for Convergence -->

<!-- ## Choosing the Learning Rate -->

## Topics to Learn

- Standard Deviation $\sigma$
