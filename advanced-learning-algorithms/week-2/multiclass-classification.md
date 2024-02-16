# Multiclass Classification

Classification problems where there is more than 2 possible classes.

## Multiclass


**Multiclass Classification Problem:**  
target $y$ can take on more than ***two*** possible values.


### Minist Example

**Examples:**
- Classifying number (0,1,2,3,4,5,6,7,8,9)
- Diagnosing problem (Many diseases)
- Visual Defect Inspection of Manufactury parts, discoloration, chipped

![image of multiclass problems](images/Mnist.png)


### Multiclass Classification Problem

Previously we had a dataset with 2 possible classes:
- $P(y = 1 | \vec{X})$
- not 1


Now with Multiclass:
- Class= 1, $P(y = 1 | \vec{X})$
- Class= 2, $P(y = 2 | \vec{X})$
- Class= 3, $P(y = 3 | \vec{X})$
- Class= 4, $P(y = 4 | \vec{X})$


The below image illustruates how the multiclass classification will work. It will have many decision boundaries to seperate each class of the dataset instead of one single line like before with logistic regression.
![image of multiclass classification example](images/Multiclass-Classification-Example.png)



