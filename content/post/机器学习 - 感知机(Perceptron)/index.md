---
title: Machine Learning - Perceptron
subtitle: This post is an exposition of perceptron in machine learning.

# Summary for listings and search engines
summary: This post is an exposition of perceptron in machine learning.

tags: 
- Machine Learning

categories: 
- Machine Learning

# Date published
date: '2022-03-07'

# Date updated
lastmod: '2022-03-07'

math: true
---

## 1 Introduction

Perceptron is a simple model for binary classification. Its construction idea is to use a hyperplane to divide data into positive and negative categories, and output $+1$ or $-1$. Perceptron can be optimized by gradient descent method, but its optimization algorithm only converges when the data is linearly separable. The perceptron was proposed by Rosenblatt in 1957.

## 2 Model construction
According to the above construction idea, the perceptron needs to map a data with a feature space of $X \subseteq R^n$ to the output space of $Y=\{+1,-1\}$. Use $x\in X$ to represent the feature vector of the training data, and $y\in Y$ to represent the output value. As mentioned earlier, the perceptron uses the hyperplane to distinguish the positive class from the negative class, so the equation of the hyperplane can be written first

$$
w\cdot x +b=0
$$

where $w$ is called the weight vector. Because the dot multiplication of $w$ and $x$ is actually a weighted sum with the characteristics of the input data. Then, we need to map the results of hyperplane calculation to 0 and 1, and the $sgn$ function is selected by the perceptron. Therefore, the mathematical expression of the perceptron model is

$$
f(x) = sgn(w\cdot x+b)
$$

Its parameters are the weight vector $w$ and the constant $b$. Corresponding to the hyperplane, $w$ is the normal vector of the hyperplane and $b$ is the intercept of the hyperplane.


## 3 Learning strategies of perceptron
In order to optimize the parameters of the perceptron, we need to find its loss function. It is easy to think that the loss function can be measured by the number of classification errors, but the number of errors is discrete, and this function is non differentiable, so gradient descent is not necessary. Therefore, considering the total distance from the misclassified point to the hyperplane S, the calculation method from a point to the hyperplane is

$$
\frac{1}{||w||}|w\cdot x_0+b|
$$

where $||w||$ is $L_2$ norm of $w$.

If we analyze the two situations when the perceptron misclassifies, that is, the negative judgment of the positive sample and the positive judgment of the negative sample. For the first, $w\cdot x_i+b >0$, the perceptron should have output 1, but when it is misclassified, it outputs -1, so $-(w\cdot x_i+b)y_i>0$, for the second, $w\cdot x_i+b <0$, the perceptron should output -1, but it outputs 1, so $-(w\cdot x_i+b)y_i>0$, so if the perceptron misclassifies a data, there will always be

$$
-y_i(w\cdot x_i+b)>0
$$

Therefore, the absolute value in the distance calculation formula can be removed to obtain a new distance calculation formula
$$
-\frac{1}{||w||}y_i(w\cdot x_i+b)
$$
Therefore, we sum the distances from all points to the hyperplane to obtain the calculation formula of the total distance
$$
-\frac{1}{||w||}\sum_{x_i\in M}y_i(w\cdot x_i+b)
$$

Now do not consider the weight of $L_2$ norm, then the loss function of the perceptron is
$$
L(w,b) = -\sum_{x_i\in M}y_i(w\cdot x_i+b)
$$

This function means that if there are fewer misclassifications and the point of misclassification is closer to the hyperplane, the loss function will be smaller.



## 4 Optimization
The optimization problem of perceptron is to solve the parameters $w$ and $b$ of the minimum loss function.

$$
\min_{w,b}L(w,b) = -\sum_{x_i\in M}y_i(w\cdot x_i+b)
$$

Then, the stochastic gradient descent method is used for optimization. First, a random $w_0$ and $b_0$, then find the gradient

For normal vector $w$
$$
\nabla_w L(w,b) = -\sum_{x_i\in M}y_ix_i 
$$

For intercept $b$
$$
\nabla_b L(w,b) = -\sum_{x_i\in M}y_i
$$

Therefore, if a misclassified data is randomly selected, the update method is
$$
\begin{cases}
w^* = w-(-\eta y_ix_i)=w+\eta y_ix_i \\
b^* = b-(-\eta y_i) = b+\eta y_i
\end{cases}
$$

Where $\eta$ is the learning rate.

Therefore, the algorithm suitable for programming implementation should be
1. Random $w_0$, $b_0$
2. Select a data $(x_i, y_i)$ in the training set
3. If $y_i(w\cdot x_i+b)\leq 0$
4. Use the update method to update the parameters
5. Loop to step 2 until the perceptron does not generate misclassified data.


So far, the construction of perceptron, learning strategy and optimization algorithm have been explained.