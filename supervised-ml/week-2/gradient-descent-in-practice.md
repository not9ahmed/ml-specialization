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

![image of Feature-Scaling](images/Feature-Scaling.png)

---



<!-- ## Checking Gradient Descent for Convergence -->

<!-- ## Choosing the Learning Rate -->
