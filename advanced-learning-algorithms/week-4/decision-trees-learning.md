# Decision Trees Learning


## Measuring Purity

- If the examples all cats single class, then it's all pure.

- If the examples not all cats single class, then it's all pure.

### Entropy As a Measure of Impurity

$p_{1} =$ fraction of examples that car cats


#### Example:

**2 cats and 4 dogs:**  
$p_{1} = 0  \;\;\;\;\;\;\;\;\; H(P_{1}) = 0$

**2 cats and 4 dogs:**  
$p_{1} = 2/6  \;\;\;\;\; H(P_{1}) = 0.92$

**3 cats and 3 dogs:**  
$p_{1} = 3/6  \;\;\;\;\; H(P_{1}) = 1$

**5 cats and 1 dogs:**  
$p_{1} = 5/6  \;\;\;\;\; H(P_{1}) = 0.65$

**6 cats and 0 dogs:**  
$p_{1} = 6/6  \;\;\;\;\; H(P_{1}) = 0$

**Entropy Function (H):**
$H(p_{1})$


- As we go 3/6 to 6/6, the impurity decreases from 1 to 0.

- As we go from 3/6 to 6/6, the purity increases from 0 to 1.


![image of entropy as a measure of impurity](images/Entropy-As-Measure-Of-Impurity.png)


$p_{1} =$ fraction of examples that car cats

$p_{0} = 1- p_{1}$


**Entropy Function**

$$
H(p_{1}) = - p_{1} log_{2} (p_{1}) - p_{0} log_{2} (p_{0}) \\
\qquad\qquad\qquad 
=  - p_{1} log_{2}(p_{1}) - (1- p_{1}) log_{2} (1- p_{1}) 
$$

We take the $log_{2}$ just to make the peak 1, and it will make interpreting the numbers easier.

Note: "$0log(0)$ = 0"

By convention instead of taking $log(0)$ as infinity it will be 0.


**Gini Criteria**
Is another form for computing the  loss for decision tree.


The entropy function looks similar to logistic loss!


The below image is the formula for computing the entropy in decision tree.
![image of entropy formula](images/Entropy-Formula.png)


## Choosing Split: Information Gain








## Using One-Hot Encodeding of Categorical Features








## Continuous Valued Features








## Regression Trees







## Topic to Study

- 