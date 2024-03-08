# Tree Ensembles


## Using Multiple Decision Trees


**Weakness of single decision tree:**  
highly sensitive to small changes in data

**Solution:**
To build a lot of decision trees which is called **<u>Tree Ensembles</u>**


### Trees are Highly Sensitive to Small Changes in Data

Changing a single example in the dataset

The highest information gain feature to split on will become the Whiskers feature.

The subsets of data will become totally different, and as a result the subtrees on left and right will be totally different.

So, the algorithm is so not very robust.

When using decsision tree you can get a better result by training multiple decision trees in order increase the performance.

![image of tree high senstivity](images/Trees-Sensitivity.png)


### Tree Ensemble

**Tree Ensemble:**  
A collection of trees

Each one is a a plausibe way of classifying a cat

Run the 3 decision trees on the new example, and they all make the vote of the final prediction.

The final prediction is the most vote class of all the decision trees.

![image of tree ensemble](images/Tree-Ensemble.png)


## Sampling with Replacement

With replacement is important beacause if I don't do replacement then I will get the same 4 tokens.

![image of sampling with replacement](images/Sampling-With-Replacement.png)

The way sampling with replacement applies when building ensemble trees

Construct multiple random training set that are different than the original dataset.

**It goes as follows:**

- We keep on taking a random example from the original dataset
- After taking the example, the example is returned
- We keep on doing that until the the complete subset is 10, and it may contain duplicate examples

![image of sample with replacement example](images/Sampling-With-Replacement-Example.png)


**Sampling with Replacement:**
Lets us construct new training set that similar but slightly different that the original dataset.


## Random Forest Algorithm

Creating tree ensemble using the sampling with replacement.

### Generating a Tree Sample

Given training set of size $m$


**For $b = 1$ to $B$:**

- Use Sampling with replacement to create a new training set of size $m$

- Train decision tree to the new dataset


$B$ recommended to be 64 or 100, the number of trees to build.

Setting $B$ never hurts performance, but after having a large number of B it will not have an effect. For example $B$ as 1000


**Bagged Decision Trees:**
The algorithm called bagged because it's like taking examples from a bag, and the $B$ stands for "bag"!


**Problem with Sampling with Replacement Procedure:**

- Sometimes it's always using the same splits the root node, and vert similar splits near the root node.


![image of generating a tree sample](images/Generating-A-Tree-Sample.png)


### Randomizing the Feature Choice

Randmoize th feature choice at each node that can cause the set of trees to become more different than each other.

- At each node, when choosing a feature to split, If $n$ feature are available.  

- Pick a random usubset of $k < n$ features and allow the algorithm to only choose from the subset of features.

- Pick $k$ features as the allowed features, then out of those $k$ features choose the one with the highest infromation gain as the feature to split on


**Typical choice for $k$:**  
is $k = \sqrt{n}$  
Used for larger features problem

**Random Forrest Algorithm**  
Works better than single decision tree.

The sampling with replacements cause algorithm to explore a lot of small changes to data already

and it's averaging over all changes to data from sampling with replacement process.

Any little change to training dataset will less likely to have big impact of the overall output of the overall random forrest algorithm.

![image of randomzing the feature choice](images/Randomizing-The-Feature-Choice.png)


## XGBoost




## When to Use Decision Trees





## Topic to Study

-