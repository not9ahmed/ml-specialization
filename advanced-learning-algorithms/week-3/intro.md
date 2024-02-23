# Advice for Applying Machine Learning



## Deciding What to Try next


### Debugging a learning algorithm

You've implemented regularized linear regression on housing prices.

$$
J(\vec{W},b) = {1 \over 2m} \sum_{i=1}^{m} (f_{\vec{W},b}(\vec{X}^{(i)})- y^{(i)})^{2} + {\lambda \over 2m} \sum_{j=1}^{n} W_{j}^{2}
$$

But it makes unpredicatable large errors in the predictions.  
What should be done?


1. Get mor Training Example
2. Try smaller sets of features
3. Try getting additional set of features
4. Try adding polynomial features $(x_{1}^{2}, x_{2}^{2}, x_{1} x_{3}, etc)$
5. Try decreasing $\lambda$
6. Try increasing $\lambda$


![image of Debugging Learning Algorithm](images/Debugging-Learning-Algorithm.png)

### Machine Learning Diagnostic

**Diagonstic:**  
A test that you can run to gain insight into what is/isn't working with a learning algorithm, to gain guidance into improving its performance.


It will if it is worth weeks or months in collecting data, which will lead to improving performance sometimes.


Diagnostics can take time to implement
but doing so can be very good use of your time.

![image of ML Diagnostic](images/ML-Diagnostic.png)


