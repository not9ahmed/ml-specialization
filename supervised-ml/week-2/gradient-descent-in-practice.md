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





<!-- ## Checking Gradient Descent for Convergence -->

<!-- ## Choosing the Learning Rate -->
