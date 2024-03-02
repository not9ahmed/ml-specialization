# Decision Trees



## Decision Tree Model


### Cat Classification Problem

I'm running a aat adoptation center, and given an image the classifier will tell wether the animal is cat or not.


**Input features $X$ takes on categorical values (discrete values).**

1. Ear shape $x_{1}$
2. Face shape $x_{2}$
3. Whiskers $x_{3}$

Binary Classification $y$ (0/1)

Cat? (0/1)

![image of cat classification example](images/Cat-Classification-Example.png)


### Decision Trees

Model after training decision tree learning algorithm on the dataset.


**Root Node:** 
Top most node in decisionn tree 


**Decision Nodes:** 
Each oval in decision trees.  
They look at particular feature, and based on the value it decide to either go left or right


**Leaf Nodes:** 
They make a prediction.

![image of decision tree](images/Decision-Tree.png)


### Other Examples of Decision Trees

The learning algorithm will create multiple decision trees, and chooses one that does well on training set and generalizes to new data which is the cross validation set.

![image of decision tree example](images/Decision-Tree-Examples.png)


## Decision Tree Learning



