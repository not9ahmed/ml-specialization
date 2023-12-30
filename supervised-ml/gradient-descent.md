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
