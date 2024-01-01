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

$\alpha$: (alpha) Learning Rate. Controls how much a big step to take downhill. Big value means huge step, and small value means small step.

${\partial \over w}  J(w,b)$ : Parital dervitive step, determine the size of steps

Formula for updating the bias
$$b =  b - \alpha {\partial \over \partial b}  J(w,b)$$

**Simultaneously update $w$ and $b$ is required to update the parameters**

![image of Gradient Descent Algorithm](images/Gradient-Descent-Algorithm.png)

## Gradient Descent Intitution

![image of Gradient Descent Intitution](images/Gradient-Descent-Intitution.png)

Derivative point at this line is drawing a tangent line, and to draw the slope I can draw a triangle. The height $\div$ (width/base) = slope

$w =  w - [\alpha {\partial \over \partial w}  J(w,b)]$

$\alpha$ is the learning rate and it's always a positive number

### In case of positive

${\partial \over \partial w}  J(w,b) > 0$

$w =  w - \alpha$ * (positive number), - times + gives negative

so it moves to the left towards the minimum, due to negative slope



### In case of negative

${\partial \over \partial w}  J(w,b) < 0$

$w =  w - \alpha$ * (negative number), - times - gives positive

so it moves to the right towards the minimum, due to negative slope

<br/>

![image of Gradient Descent Examples](images/Gradient-Descent-Examples.png)

The 2 examples of updating the weight according the slope on the point choosen, in case of (+) slope the term $\alpha {\partial \over \partial w}  J(w,b)$ becomes negative, so it shifts to left <-- negative x-axis to reach minimum.

In case of (-) slope the term $\alpha {\partial \over \partial w}  J(w,b)$ becomes positive, so it shifts towards the right ro reach minimum.

