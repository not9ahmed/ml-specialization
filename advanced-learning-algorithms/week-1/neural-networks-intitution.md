# Neural Networks Intitution


## Neurons and the Brain

Neural networks also called artifical neural networks


**Origins:**
- Algorithms that try to mimic the brain.
- Used in the 1980's and early 1990's.
- Fell out of favor in the late 1990's.
- Resurgence from around 2005.

Modern Deep learning helped in rebranding the neural networks.

**Modern Neural Networks/Deep Learning Applications are:**
- Speech Recognition imporved due to deep learning
- Computer Vision & Images due to imagenet
- Text (NLP Natural Language Processing) used in international translation.
- Other Appplication: Climate Change, product recommendation


The following diagram showcases how the neurons work:
- All human thoughts from neurons like these in brain and mind
- The neurons send electrical impluses/ or form othe connections with neurons
- Has number of inputs, which it recieves electrical impluses from other neurons.
- The neuron then carries computations, and send outputs to other neurons
- and the same happens to the recieving network
![image of the human nerons](images/Neurons-in-Brain.png)

<br/>


The below image shows a comparison between the biological neurons, and the simplified mathematical neurons. The two neurons take some input values, then carry out a computation then it sends the result to other neurons.
![image of Biological vs Simplified Mathematical Neurons](images/Biological-vs-Maths-Neurons.png)


### Why Now?

Why has neural networks has taken off??

Amount of digital data has exploded

**The traditional machine learning algorithms logistic & linear regression faced some issue which are:**
- Even if they were feed more data, it was difficult to get the performance going up.
- They cannot utilize the large amount of data.
- They cannot scale with the large amount of data.


**Large Neural Networks** are better choice for very large amount of data!  
- To take advantage of the huge of amount of data for speech recognition.
So that's why Deep Learning took off
- Faster Computer Processors (GPUs) also helped in making Deep Learning trending.


The following image showcases why the neural networks are trending now, which is due to the huge amount of data, and faster CPUs.
![image of why neural networks are again trending](images/Why-Now.png)


## Demand Prediction

Example: Predict if the product is top seller

Used by retailers to plan better inventory level and marketinng campaigns

$$
x = price \rightarrow input
$$


$$
a = f(x) = {1 \over {1 + e^{-(wx + b)}}} \rightarrow output
$$

$a$ stands for activiation, and it's the probability of being top seller.  

In neuroscience, $a$ Stands for how much neuron is sending high output to other neurons downstream from it

Neuron is tiny computer, and its' main job is take input number, and outputs one or more number. The output is the probability of being topseller.

Building neural networks is just wiring different number of neurons together to build a robust mode.

The below image showcases an examply of find the bestseller product using logistic regression.
![image of the demand prediction](images/Deman-Prediction.png)

<br/>





**Layer:** is grouping of neurons, and takes as input same or similar features and outputs a few numbers togther.
It can have multiple neuron, or single neuron.

**Output Layer:** The output of the layer is the probability predicted by neural network.

**Activation:** The features connect to a neuron
comes from bio neurons, degree that bio neurons sends high output value or electrical impluses to other downsream neurons from it.

**The Neural Network flow:**
1. Input Layer: inputs 4 numbers
2. First/Hidden layer: uses 4 number to compute 3 new numbers "activation values"
3. Output layer: uses the 3 numbers from activation then output the probability.

In practice, all the features are connected to each neuron in the first/hidden layer.


Input layer will be represneted as a vector $\vec{X}$, and it's feature vector. The output will be feed to the first layer.

The activation values represented as a vector $\vec{a}$ and will be feed to output layer.


**Why Is It called Hidden Layer?**
In training set I can observe $(x, y)$ values so I know correct values.

However, for the values $(x, y)$ in the hidden layer affordability, awareness, preceived quality I don't know the actual values.



log reg unit 


log reg but version that can learn its own features that makes it easier to make prediction.



The following image showcases how construct a neural network, with each neuron being linked to a certain feature. 
![image of simple nn example](images/Simple-NN-Example.png)




