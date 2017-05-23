---
layout: post
title:  "Linear Regression"
date:   2016-06-19 12:12:41 -0700
categories: Machine Learning 
---
**Linear Regression** is an important basis of both machine learning and adaptive
signal processing, the underlying assumption is that the output is a `linear combination` 
of the input. There are numerous interpretations of linear regression, the most common and 
perhaps the most interesting is the geometric explanation. 

Let's define the column of matrix X as a linear subspace of the dimensionality D which is 
embedded in N dimension. Matrix X is N by D and vector y is N by 1, where N > D. `The goal
is to find y_hat in this linear subspace such that it is closest to y.`

```python
     arg min(l2norm(y-y_hat)), y_hat is element of the span of X
```

