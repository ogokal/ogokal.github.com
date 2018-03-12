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
