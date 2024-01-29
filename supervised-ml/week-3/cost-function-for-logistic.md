# Cost Function for Logistic Regression

Gives a way to meausre how set of parameters fit the data, and gives a way to choose better parameters

Mean Squared Error is not ideal for Logistic Regression


Th below image show cases s sample training for Logistic Regression.

The training set has $n$ number of fetaures, and $m$ number of examples:

- $i = 1 \dotso , m$ <-- Training Examples
- $j = 1 \dotso , n$ <-- Features

The Logistic Regression formula is 

$$f_{\vec{W}, b}(\vec{X}) = {1 \over {1 + e^{-(\vec{W} \cdot \vec{X} + b)}}}$$

![image of Cost-Function for Logistic Regression](images/Cost-Function-for-Logistic-Regression.png)


### Squared Error Cost

$$J(\vec{W}, b) = {1 \over m} \sum_{i=0}^{m}{1 \over 2}(f_{\vec{W}, b}(\vec{X}^{(i)}) - y^{i})^{2}$$