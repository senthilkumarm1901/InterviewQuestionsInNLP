# Questions related to Neural Networks built for NLP Applications

The following questions are prepared primarily from he teachings of `deeplearning.ai coursera specialization`:

<details> <summary>1. What is the advantage of <code>relu</code> over <code>sigmoid</code> activation function in neural network?</summary>
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

<details> <summary>2. Why is hyperbolic tangent (<code>tanh</code>) preferred more than sigmoid activation function in NN? </summary>
<br>
 
 ![sigmoid-vs-tanh](https://i.stack.imgur.com/o0JA0.png) <br>
 
 - tanh function has larger derivatives and this (somehow?) helps in minimizing cost function faster <br>
 - the outputs using tanh centre around 0 rather than sigmoid's 0.5, and this "makes learning for the next layer a little bit easier". <br>
 
 reference [here](https://stats.stackexchange.com/questions/330559/why-is-tanh-almost-always-better-than-sigmoid-as-an-activation-function)
 </details>

 
 <details> <summary>3. What are the differences between <code>L1</code> and <code>L2</code> regularization techniques? When do we use <code>dropout</code> ?</summary>
<br>
 - All 3 techiques lead to simpler NNs. Hence, more `generalizable` <br>
 - `cost_function` = `Loss` + `Regularization` <br>
 - Regularization: <br>
 `L2` (Ridge) Regularization: <br>
 
 ![](https://cdn.analyticsvidhya.com/wp-content/uploads/2018/04/Screen-Shot-2018-04-04-at-1.59.54-AM.png) <br>
 `L1` (Lasso) Regularization: <br>
 
 ![](https://cdn.analyticsvidhya.com/wp-content/uploads/2018/04/Screen-Shot-2018-04-04-at-1.59.57-AM.png) <br>
 
> From a practical standpoint, L1 tends to shrink coefficients to zero whereas L2 tends to shrink coefficients evenly. L1 is therefore useful for **feature selection**, as we can drop any variables associated with coefficients that go to zero. L2, on the other hand, is useful when you have collinear/codependent features. (An example pair of codependent features is `gender` and `ispregnant` since only females can be `ispregnant`.)

 <br>
 
> `Dropout` also simplifies NNs and is the most frequently used regularization technique in the field of deep learning (because it yields better results)
<br>
 
> The probability of choosing how many nodes should be dropped is the hyperparameter of the dropout function.
 
Sources: <br> 
- https://explained.ai/regularization/L1vsL2.html <br>
- https://www.analyticsvidhya.com/blog/2018/04/fundamentals-deep-learning-regularization-techniques/
 
 
 </details>
 
 <details> <summary>4. What are some of the typical set of <code>hyperparameters</code> tuned in a NN?</summary>
 
 - #hidden layers
 - #hidden units in each layer
 - #iterations (or epoch size)
 - #mini-batch size
 - choice of activation fn (e.g.: relu, tanh, etc.,)
 - choice of optimizer (e.g.: sgd, asgd, rmsprop,momentum, adam, etc.,)
 - learning rate
 - choice of regularization techniques
 
 </details>
 
 <details> <summary>5. What are the different <code>text representation models</code> employed in NLP?</summary>
 
TL;DR version from Source [1]
 - I) Categorical word representation (e.g.: One-hot Encoding/ Bag of words) <br> 
 - II) Weighted Word representation (e.g.: TF-IDF) <br>
 (both I and II suffer from the curse of high dimensionality; dimension length = vocab length) <br>
 - III) Representation Learning (trained based on a Self-supervised Learning technique like Language Model) <br>
     - a. Distributed Representations (e.g.: Word2Vec, FastText, GloVe) <br>
     - b. Contextual Embeddings (before Transformer) (e.g.: ULMFiT, ELMo, Context2Vector, USE made from Deep Averaging Networks) <br>
     - c. Transformer-based Pre-trained Language Models (not exhaustive) <br>
         - Universal Sentence Encoder (version made from Transformer Encoder)     
         - GPT1, 2 and 3 (OpenAI Transformer) <br>
			      - Bidirectional Encoder Representations from Transformers (BERT) <br>
			      - XLNet <br>
			      - ALBERT <br>
			      - RoBERTa <br>
			      - StructBERT <br>
			      - DistillBERT <br>
			      - MegatronLM <br>
			      - Ernie and Ernie 2.0 <br>
			      - BART <br>
         - T5 (Text2Text Transfer Transformer) <br>

Source: 
 - [1] A Comprehensive Survey on Word Representation Models: From Classical to State-Of-The-Art Word Representation Language Models https://arxiv.org/pdf/2010.15036v1.pdf <br>
 - Evolution of Transfer Learning in Natural Language Processing Paper: https://arxiv.org/pdf/1910.07370.pdf

 </details>
 
 
  </details>
 
 <details> <summary>6. Why adding more layers is better than adding more neurons in a single layer in NN?</summary>
 
 
[1] Yoshua Bengio Explanation <br>
> Adding a layer increases the depth, and allows the network to represent more complex, more non-linear functions, *which might otherwise not be representable efficiently by a less deep network*
 
[2] NNs with many layers perform significantly better than NNs with a single layer (of equal no. of parameters) because of more non-linearity in the NN with many layers
 
 Source: 
 - [1] https://www.quora.com/What-is-a-difference-between-adding-one-more-layer-and-increasing-neurons-in-one-layer
 - https://www.quora.com/Why-do-neural-networks-with-more-layers-perform-better-than-a-single-layer-MLP-with-a-number-of-neurons-that-leads-to-the-same-number-of-parameters
  </details>
