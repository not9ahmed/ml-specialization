# Skeweed Datasets

When working on machine learning model where the ratio of positive and negative examples is very skewed and not 50/50.


## Error Metrics for Skewed Datasets


### Rare Desease Classification Example

Trainer classifier $f_{\vec{W},b}$

($y$ = 1 if disease is present,
$y$ = 0 otherwise)

Find that you've got 1% error on test set (99% correct diagnoses)

Only 0.5% of patients have the disease.

Even a simple `print("y=0")` will achieve a 99.9% Accuracy, 0.5$ error due to diease being extremly rare.


Can't tell if getting 1% error is good result or not as it's a very rare disease.

Accuracy is not always a good measure to know if a model is having a good performance.

The image below shows that having a low error % sometimes is not useful as the disease is rare and so the simple print code will be more accurate but it's not useful.
![image of rare disease classification example](images/Rare-Disease-Classification-Example.png)


### Precision/Recall


$y = 1$ in presence of rare class we want to detect.

**Confusion Matrix:**



|              | Actual Class 1 | Actual Class 0 | |
|--------------|--------------------|----------------------|--|
| Predicted Class 1 | True Positive 15 | False Positive 5  | 25 |
| Predicted Class 0 | False Negative 10 | True Negative 70 | 80|
||25|75


First name (True/False) --> Prediction is correct or wrong
Second name (Positive/Negative) --> the actual class


**Precision:**  
(of all patients where we predicted $y = 1$, what fraction actually have the rare disease?)

$$
{\text{True positives} \over \text{\#Predicted positive}} 
= {\text{True positives} \over \text{True Pos + False Pos}} 
\\
= {15 \over {15 + 5}}
= {15 \over 20}
= 0.75
$$
Adding up the first row, of the predicted class is 1


**Recall:**  
(of all patients that actually have the rare disease, what fraction did we correctly detect as having it?)

$$
{\text{True postives} \over \text{\#actual positive}}
= {\text{True positive} \over \text{True pos + False neg}}
\\
= {15 \over {15 + 10}}
= {15 \over 25}
= 0.6
$$


![image of precision & recall](images/Precision-Recall.png)



## Trading Off Precision and Recall




## Topics to Study

- Precision/Recall