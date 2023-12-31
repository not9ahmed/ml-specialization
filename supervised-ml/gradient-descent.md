# Gradient Descent

Used for training advanced models especially in deep learning

Have some function $J(w,b)$
for linear regression or any function
$min_{w_{1},w_{2},w_{3},w_{n},b}$ for $J(w_{1},w_{2},w_{3},w_{n},b)$

Want $min_{w,b}$   $J(w,b)$

**Outline**

    Start with some $w,b$ set $(w=0, b=0)$
    Keep changing $w,b$ to reduce $J(w,b)$
    Until we settle at or near a minimum
    May have  > 1 Minimum (Many minimums)

    also J not always a parabola

![image of Gradient Descent](images/Gradient-Descent.png)
<br/>
<br/>

In Gradient Descent based on the starting point, and taking a small step around to look where it's descencing in order to find the stepest descent.

Based on starting it can lead to different minimum, and this minimum can be called as **Local Minima**. It can lead to downhill of the Cost function $J$.

## Local Minimia

The lowest point where $J$ is considered the minimum and it's depending on the starting point parameters
![image of Local Minima](images/Local-Minima.png)

## Gradient Descent Algorithm

Repeat until convergence, reach the point at local minima, where parameters $w, b$ does not change much with additional steps

Formula for updating the weights
$$w =  w - \alpha {\partial \over \partial w}  J(w,b)$$

= : Assignment

$\alpha$ : Learning Rate. Controls how much a big step to take downhill. Big value means huge step, and small value means small step.

${\partial \over w}  J(w,b)$ : Dervitive step, determine the size of steps

Formula for updating the bias
$$b =  b - \alpha {\partial \over \partial b}  J(w,b)$$

**Simultaneously update $w$ and $b$ is required to update the parameters**

![image of Gradient Descent Algorithm](images/Gradient-Descent-Algorithm.png)

