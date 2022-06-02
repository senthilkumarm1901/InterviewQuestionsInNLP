Very Generic basic common sense stuff (good to read anyway)<br>
   https://github.com/ageron/handson-ml/blob/master/ml-project-checklist.md<br>
   <br>

How to split data for ML?<br>
   https://link.springer.com/content/pdf/10.1007%2F978-3-319-23528-8_1.pdf<br>
   <br>

Some simple Credit domain Example (Model Classification): <br>
   http://ceur-ws.org/Vol-2029/op2.pdf<br>
   <br>
A simple paper on evaluation metrics for classification: <br>
   https://arxiv.org/ftp/arxiv/papers/1504/1504.04646.pdf<br>
   <br>
Codes-first or practice-first resources: <br>
   Basic Pre-processing on datasets with numerical and categorical data: <br>
   https://github.com/zotroneneis/machine_learning_basics/blob/master/data_preprocessing.ipynb<br>
   <br>
   On mainly Data Preprocessing at a high level: <br>
   https://towardsdatascience.com/data-pre-processing-techniques-you-should-know-8954662716d6<br>
   <br>

Some good sklearn resources to understand ML quickly: <br>
- Note all html from Andreas Muller are good to dig deeper;<br>
   	https://github.com/amueller/ml-workshop-1-of-4/tree/master/slides<br>
   	https://github.com/amueller/ml-workshop-2-of-4/tree/master/slides<br>
   	https://github.com/amueller/ml-workshop-4-of-4/tree/master/slides<br>
   	https://github.com/amueller/ml-workshop-3-of-4/tree/master/slides<br>

   
Good StackExchange Links: <br>
- Why Training Accuracy < Validation Accuracy (or Training Error > Validation Error)? <br>
- URL: https://stats.stackexchange.com/questions/187335/validation-error-less-than-training-error <br>

```Generally speaking though, training error will almost always underestimate your validation error. However it is possible for the validation error to be less than the training. You can think of it two ways:

Your training set had many 'hard' cases to learn
Your validation set had mostly 'easy' cases to predict
That is why it is important that you really evaluate your model training methodology. If you don't split your data for training properly your results will lead to confusing, if not simply incorrect, conclusions.

I think of model evaluation in four different categories:

Underfitting – Validation and training error high

Overfitting – Validation error is high, training error low

Good fit – Validation error low, slightly higher than the training error

Unknown fit - Validation error low, training error 'high'
```

A good resource on questions, processes and preparation for Machine Learning Interviews by Khang Pham. <br>
- Web page: https://mlengineer.io/
- GitHub: https://lnkd.in/dcCGw35F
