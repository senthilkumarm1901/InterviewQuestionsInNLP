# Coding Questions related to Neural Networks built for NLP Applications

<details> <summary>1. <code>Numpy</code>What is the difference between <code>np.random.rand</code> and <code>np.random.randn</code>?</summary>
<br>
  
 `np.random.rand` = uniform distribution <br>
  `np.random.randn` = normal/gaussian distribution <br>
  
  Which one is better while initialization of weights in NN: <br>
  - No clear winner [2] <br>
  - Xavier initialization uses Uniform distribution
  - Some examples in TensorFlow's tutorials also use a truncated Normal distribution.
  
  No one uses sigmoid activation function in hidden layers. In case sigmoid is used, it performs bad with uniform distribution[1]
  - Range of sigmoid(x) is 0 to 1. sigmoid(0) = 0.5. The slope of sigmoid activation function is minimum when x is too large or too small.
  - When we use `np.random.rand` (uniform distribution), the gradients do not learn much as only tiny updates possible
   
  Source: <br>
  - [1] https://stackoverflow.com/questions/47240308/differences-between-numpy-random-rand-vs-numpy-random-randn-in-python <br>
  - [2] https://stats.stackexchange.com/questions/229669/when-should-i-use-the-normal-distribution-or-the-uniform-distribution-when-using
  
  
 </details>
 
 
 
 <details> <summary>2. Why weights initialization is very important? What does Xavier Initialization do?</summary>
<br>
  
  Why? <br>
  
  > initializing the network with the right weights can be the difference between the network converging in a reasonable amount of time and the network loss function not going anywhere even after hundreds of thousands of iterations.

  Vanishing Gradient <br>
> If the weights are too small, then the variance of the input signal starts diminishing as it passes through each layer in the network. The input eventually drops to a really low value and can no longer be useful. If we use sigmoid as the activation function, then we know that it is approximately linear when we go close to zero. This basically means that there won’t be any non-linearity. If that’s the case, then we lose the advantages of having multiple layers.
  
  Exploding Gradient <br>
  
 > If the weights are too large, then the variance of input data tends to rapidly increase with each passing layer. Eventually it becomes so large that it becomes useless. Why would it become useless? Because the sigmoid function tends to become flat for larger values
 
 What does Xavier Initialization do? Avoids Vanishing Gradient and Exploding Gradient
 > With each passing layer, we want the variance to remain the same. This helps us keep the **input signal from exploding to a high value or vanishing to zero**. In other words, we need to initialize the weights in such a way that the variance remains the same for x and y
  
  Source: <br>
  - https://prateekvjoshi.com/2016/03/29/understanding-xavier-initialization-in-deep-neural-networks/
