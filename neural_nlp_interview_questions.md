# Questions related to Neural Networks built for NLP Applications

The following questions are prepared primarily from he teachings of `deeplearning.ai coursera specialization`:

<details> <summary>1. What is the advantage of `relu` over `sigmoid` activation function in neural network?</summary>
<br>
Ans: Relu can help in faster gradient descent compared to sigmoid. Relu does NOT have the expensive **exponential function** to compute like that of sigmoid
Also, gradient of sigmoid is atmost 0.25. So if there are many layers in NN, you will multiply these gradients, and the product of many smaller than 1 values goes to zero very quickly (vanishing gradient). <br>   
<br>

**Some facts:** <br> 
<img src="https://latex.codecogs.com/gif.latex?sigmoid(x)=\frac{1}{1&plus;e^{-x}}" title="sigmoid(x)=\frac{1}{1+e^{-x}}" /> <br>
<img src="https://latex.codecogs.com/gif.latex?relu(x)=max(0,x)" title="relu(x)=max(0,x)" /> <br>
- sigmoid value ranges from `0 to 1` (when x tends to minus infinity, denominator becomes too huge, hence value will be close to 0) <br>
- As x increases, sigmoid(x) tends to 1 and derivative of sigmoid(x) tends to 0 (iow: the gradient of sigmoids becomes increasingly small as the absolute value of x increases.) <br>
<img src="https://latex.codecogs.com/gif.latex?sigmoid'(x)&space;=&space;S'(x)&space;=&space;S(x)(1-&space;S(x))" title="sigmoid'(x) = S'(x) = S(x)(1- S(x))" /> <br>
<img src="https://latex.codecogs.com/gif.latex?if&space;S(x)&space;==&space;1,&space;S'(x)&space;=&space;1&space;(1-1)&space;=&space;0" title="if S(x) == 1, S'(x) = 1 (1-1) = 0" /> <br>
- relu value ranges from 0 to no upper limit! <br>
- gradient of relu is always a constant (because derivative of x over x is 1). Hence multiplying gradients will not explode it. The constant gradient of ReLUs results in faster learning. <br>
- But dying relu is a problem. if too many activations get below zero then most of the units(neurons) in network with Relu will simply output zero, in other words, die and thereby prohibiting learning.(This can be handled, to some extent, by using Leaky-Relu instead.) <br>
P.S
<br>

- Refer [here](https://stats.stackexchange.com/questions/126238/what-are-the-advantages-of-relu-over-sigmoid-function-in-deep-neural-networks) 
- (to create math equations like above use [this link](https://www.codecogs.com/latex/eqneditor.php)) 
 
</details>

<details> <summary>2. Why is hyperbolic tangent (`tanh`) preferred more than sigmoid activation function in NN? </summary>
<br>
 
 ![sigmoid-vs-tanh](https://i.stack.imgur.com/o0JA0.png) <br>
 
 - tanh function has larger derivatives and this (somehow?) helps in minimizing cost function faster <br>
 - the outputs using tanh centre around 0 rather than sigmoid's 0.5, and this "makes learning for the next layer a little bit easier". <br>
 
 reference [here](https://stats.stackexchange.com/questions/330559/why-is-tanh-almost-always-better-than-sigmoid-as-an-activation-function)
 </details>
