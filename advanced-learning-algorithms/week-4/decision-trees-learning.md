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


To decide which feature to split on a node. It will based on a choice of feature that will reduce entropy, or reduce impurity, or maximizes purity.


**Information Gain:**  
The reduction of entropy 


### Choosing a Split

$p_{1}$ will refer to the example being in class cat.


The weighted average:
$$
\left(
{   
    {\text{\# of examples in branch 1}
    \over \text{total examples}
    }
H(p_{1} \text{branch 1})}
+
    {\text{\# of examples in branch 2}
    \over \text{total examples}
}
H(p_{1} \text{branch 2})
\right)
$$



#### Ear Shape Feature

At the root node: 
$p_{1} = 5/10 = 0.5$

The entropy at the root node: 
$H(0.5) = 1$

1. Pointy
   - $p_{1} = 4/5 = 0.8$
   - $H(0.8) = 0.72$

2. Floppy
   - $p_{1} = 1/5 = 0.2$
   - $H(0.2) = 0.72$

The Information Gain:
$$
H(0.5) -
\left(
{{5 \over 10} H(0.8)} + {{5 \over 10} H(0.2)}
\right) \\
= 0.28
$$

Will be selected as the root node, as it's the larget value.


#### Face Shape Feature

At the root node: 
$p_{1} = 5/10 = 0.5$

The entropy at the root node: 
$H(0.5) = 1$

1. Round
   - $p_{1} = 4/7 = 0.57$
   - $H(0.57) = 0.99$

2. Not Round
   - $p_{1} = 1/3 = 0.33$
   - $H(0.33) = 0.92$


The Information Gain:
$$
H(0.5) -
\left(
{{7 \over 10} H(0.57)} + {{3 \over 10} H(0.33)}
\right) \\
= 0.03
$$


#### Whiskers Feature

At the root node: 
$p_{1} = 5/10 = 0.5$

The entropy at the root node: 
$H(0.5) = 1$

1. Present
   - $p_{1} = 3/4 = 0.75$
   - $H(0.75) = 0.81$

2. Absent
   - $p_{1} = 2/6 = 0.33$
   - $H(0.33) = 0.92$


The Information Gain:
$$
H(0.5) -
\left(
{{4 \over 10} H(0.75)} + {{6 \over 10} H(0.33)}
\right) \\
= 0.13
$$


Because how important it's to have low entropy on right or left branch will depend on the number examples on the right or left branch.


**The Information Gain:**  
It measures the reduction in entropy you get in tree resulting from making a split.

Because the entropy was originally one at the root node and by making the split the entropy value gets lower and the difference is called "reduction in entropy"

The reduction in entropy is one of the stopping critieria, and if the the reduction is very small, then stop. Because it may lead to overfitting problem.

![image of choosing a split](images/Choosing-A-Split.png)


### Information Gain


$p_{1}^{root} = 5/10 = 0.5$

**For Left Sub-Branch**

1. The number of examples of class cat in the left sub-branch over total left branch examples:  
    - $p_{1}^{left} = 4/5$

2. The fraction of examples of all the examples of the root node that went to the left sub-branch:  
   - $w^{left} = 5/10$


**For Right Sub-Branch**

1. The number of examples of class cat in the right sub-branch over total right branch examples:  
    - $p_{1}^{right} = 1/5$

2. The fraction of examples of all the examples of the root node that went to the left sub-branch:  
    - $w^{right} = 5/10$



**Information Gain:**

$$
= H(p_{1}^{\text{root}})-
\left(
w^{\text{left}} H (p_{1}^{\text{left}})
+ w^{\text{right}} H (p_{1}^{\text{right}})

\right)
$$


Can calculate the information gain split on a node, and pick the one with the highest infromation gain, and it will result in increasing the purity of the subset data in the left sub-branches and right sub-branches.
![image of information gain](images/Information-Gain.png)


## Using One-Hot Encodeding of Categorical Features








## Continuous Valued Features








## Regression Trees







## Topic to Study

- 