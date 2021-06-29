# Questions related to Traditional ML and NLP

<details> <summary>1. What are <code>discriminative</code> and <code>generative</code> ML models? Explain with examples</summary>
<br>
  
  Difference between `discriminative` and `generative` models [1]: 
  
  >  a discriminative machine learning trains a model by learning parameters that maximise the conditional probability P(Y|X), but a generative model learns parameters by maximising the joint probability P(X,Y)
  
  Generative Models [1] <br>
  > Generative models are a class of statistical models that generate new data instances. These models are generally/mostly used in *unsupervised machine learning*. E.g.: Naive Bayes, Latent Dirichlet Allocation, Gaussian Mixture Models etc., 
 
  <br>
  
  Discriminative Models [1] <br>
  > The discriminative model is used particularly for supervised machine learning. Also called a conditional model, it learns the boundaries between classes or labels in a dataset. E.g.: SVM, Logistic Regression, Decision Trees, etc.,
  
  Source: <br>
  - https://analyticsindiamag.com/what-are-discriminative-generative-models-how-do-they-differ/
  
  </details>
  
 <details> <summary> 2. What is the difference between	Ordinary least squares  (to minimize loss function) and gradient descent in a Linear Regression? </summary>
- OLS - non-iterative statistical optimization model to minimize loss function and hence to find m and b in the minima; a linear algebra problem; **must fit in memory** <br>
- GD - iterative model to minimize loss function to find m and b; **need not fit in memory**;<br>
  
  </details>

 <details> <summary> 3. Can Gradient Descent be applied to non-DL algorithms? </summary>
- Yes !!! <br>
- E.g.: Hidden Markov Model, K-Means, Linear Regression
  </details>
  
 <details> <summary> 4. What is K-Means objective/cost/error/loss function? How can the cost function be optimized? </summary>
  
- `Sum of Squared (Euclidean) distances` of each data point to assigned/closest centroid/cluster center 
<br>
  Optimization ALgorithms: <br>
- Expectation Maximization <br>
- Gradient Descent <br>
  
  Source: <br>
  - https://www.saedsayad.com/clustering_kmeans.htm#:~:text=The%20objective%20of%20K%2DMeans,to%20the%20Euclidean%20distance%20function.

</details>
