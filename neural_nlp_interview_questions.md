# Questions related to Neural Networks built for NLP Applications

The following questions are prepared primarily from he teachings of `deeplearning.ai coursera specialization`:

<details> <summary>1. What is the advantage of `relu` over `sigmoid` activation function in neural network?</summary>
<br>
Ans: Relu can help in faster gradient descent compared to sigmoid. Relu does NOT have the expensive **exponential function** to compute like that of sigmoid
Also, gradient of sigmoid is atmost 0.25. So if there are many layers in NN, you will multiply these gradients, and the product of many smaller than 1 values goes to zero very quickly (vanishing gradient). <br>   
<br>

**Some facts:** <br> 
![](./docs/sigmoid.png) <br>
![](./docs/relu.png) <br>
- sigmoid value ranges from `0 to 1` (when x tends to minus infinity, denominator becomes too huge, hence value will be close to 0) <br>
- As x increases, sigmoid(x) tends to 1 and derivative of sigmoid(x) tends to 0 (the gradient of sigmoids becomes increasingly small as the absolute value of x increases.) <br>
![](./docs/first_derivative_of_sigmoid(1).png) <br>
![](./docs/first_derivative_of_sigmoid(2).png) <br>
 
- relu value ranges from 0 to no upper limit! <br>
- gradient of relu is always a constant (because derivative of x over x is 1). Hence multiplying gradients will not explode it. The constant gradient of ReLUs results in faster learning. <br>
- But dying relu is a problem. if too many activations get below zero then most of the units(neurons) in network with Relu will simply output zero, in other words, die and thereby prohibiting learning.(This can be handled, to some extent, by using Leaky-Relu instead.) <br>
P.S
<br>

- Refer [here](https://stats.stackexchange.com/questions/126238/what-are-the-advantages-of-relu-over-sigmoid-function-in-deep-neural-networks) for detailed discussion
- (to create math equations like above use [this link](http://mathurl.com/)) 
 
 ![\Large x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}](https://latex.codecogs.com/svg.latex?x%3D%5Cfrac%7B-b%5Cpm%5Csqrt%7Bb%5E2-4ac%7D%7D%7B2a%7D)
 
</details>

<details> <summary>2. Why is hyperbolic tangent (`tanh`) preferred more than sigmoid activation function in NN? </summary>
<br>
 
 ![sigmoid-vs-tanh](https://i.stack.imgur.com/o0JA0.png) <br>
 
 - tanh function has larger derivatives and this (somehow?) helps in minimizing cost function faster <br>
 - the outputs using tanh centre around 0 rather than sigmoid's 0.5, and this "makes learning for the next layer a little bit easier". <br>
 
 reference [here](https://stats.stackexchange.com/questions/330559/why-is-tanh-almost-always-better-than-sigmoid-as-an-activation-function)
 </details>
