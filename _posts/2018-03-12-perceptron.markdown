---
layout: post
title:  "Notes about Perceptron"
date:   2018-03-12 08:02:35 +0300
categories: ml
---

> Buraya Perceptron seklini koy

We have a linearly separable dataset and we like to find that decision boundary
for that. Let's assume that we decided to choose perceptron as our tool.
In perceptron algorithm, we try to correct our model based on new observation
and a step function that provides +1 or -1 decision in a simplest way.
> Buraya step function seklini koy


Based on the figure 1, perceptron has two parts, the first part for incoming
connections accepts other connections including inputs to the model. For the
first part mathematically speaking we calculate:
\begin{equation}
\beta^T\underline{x} + \beta_0
\begin{equation}

Let's put aside the equation above for a moment, the general steps for any machine learning approach is to follow the scenario:
Assume we have a hypothesis function $$f$$
where $$f(x) \epsilon F $$ and we need some kind of scoring to evaluate how good our hypothesis function is.
So it could be:
\begin{equation}
S(f) = E_x,y L(y,f(x))
S(f) = 1/n \sum{i=1}^n L(y_i, f(x_i))
\end{equation}
If we approach that problem like an optimization problem, basically we are searching for the optimum hypothesis function in other words decision boundary which minimizes total distance of misclassified points.
\begin{equation}
\hat{f} = arg min_f\epsilon F S(f)
\end{equation}
> Buraya su olasi decision boundary cizimlerini koy

Going back to perceptron, we will try to apply above steps.
Let's define our scoring function for perceptron learning as :
\begin(equation)
\phi (\beta, \beta_0)
\end(equation)
representing the total distance of misclassified points to the decision boundary, then the aim is just to
minimize that total distance.
\begin{equation}
min_\beta,\beta_0 \phi (\beta, \beta_0)
\end{equation}
Actually scoring function could be based on any distinguishing feature so it could be the total number of
misclassified points.
We know that perceptron is a linear discriminative function in the form.
\underline{\beta^T}\underline{x} + \beta_0 = 0
>Buraya yukaridaki dogrunun seklini koy. X1 ve X2 icin

and assume that both $$x_1$$ $$x_2$$ are on the same line so satisfying the following equality.
\begin{align}
\underline{\beta^T}\underline{x_1} + \beta_0  = \underline{\beta^T}\underline{x_2} + \beta_0 \\\
\underline{\beta^T}\underline{x_1} + \cancel{\beta_0} = \underline{\beta^T}\underline{x_2} + \cancel{\beta_0} \\\
\underline{\beta^T}\underline{x_1} -  \underline{\beta^T}\underline{x_2}  = 0\\\
\beta^T(\underline{x_1} - \underline{x_2}) = 0
\end{align}
since the dot product of items in the last equation is 0, that means they are orthogonal, $$\underline{\beta} \perp \underline{x_1} - \underline{x_2} $$
>Buraya diklik icin sekil koy

>Buraya 2. sekli koy
For another point $$X_0$$ on the same line, the line equation should be valid.
\begin{equation}
\beta_TX_0 + \beta_0 = 0 \\\
\beta_0 = -\beta_TX_0
\end{equation}
 >Buraya 3. sekli koy

 So how do we calculate distance from a point not on the line or the line. We
 know that $$\beta$$ is perpendicular to the line so if we first project distance
 vector on to the $$\beta$$ we are done.
 The distance vector between the new point $$\underline{x}$$ and $$\underline{x_0}$$
 is $$ \underline{x} - \underline{x_0} $$ and if we project it on the $$\beta$$
 the result would be:
 \begin{equation}
 distance = \frac{\beta_TX}{\|\beta\|} -  \frac{\beta_TX}{\|\beta_0\|} \\\
 distance = \frac{\beta_TX}{\|\beta\|} -  \beta_0 \text{from the equality}(\beta_0 = -\beta_TX_0)\\\
 \end{equation}

 If the point is on the upper side of this discriminative line then the distance will
 be positive otherwise it is negative.
 How can we turn this distance function to a score function so that we can take
 derivative of it ? It should support both cases (positive and negative) ?
 Let's assume we choose absolute of distance as our scoring function, in that cases
 we can't differentiate both cases. What if we multiply result with itself again, I mean
\begin{equation}
d_i = y_i (\beta_TX + \beta_0)
\end{equation}
then we will have scoring function for valid cases (actual value and predicted value are aligned)
> sayfa 7
