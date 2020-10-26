---
layout: post
title:  "Uncertainty in Deep Learning"
date:   2020-10-26
category: ai
tags: [Deep Learning, Uncertainty, Bayesian]
---


Yarin Gal  

Deep Learning에 Uncertainty를 처음 도입해 하나의 큰 분야로 만듬.  


[Thesis](http://mlg.eng.cam.ac.uk/yarin/thesis/thesis.pdf)  
[Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learing(ICML, 2016)](http://proceedings.mlr.press/v48/gal16.pdf)  

[Easy Korean Video](https://www.youtube.com/watch?v=aU91bDGmy7I)

Production에서 틀리는 것 보다는 "모른다"고 하는 게 낫다.  
특히, 자율주행이나 의료처럼 틀렸을 때의 리스크가 아주 클 때.

RL에서도 bayesian을 사용하면  
언제 exploration을 하고 exploitation을 할 건지  
epsilon-greedy 보다 더 좋은 policy를 정할 수 있다.  


softmax 결과는 uncertainty가 아니다.  


Thesis: Bayesian neuralnet 과 dropout은 동일하다.  
Paper: Gaussian process와 dropout은 동일하다.  

Bayesian Neural Networks 에서는 model parameter를 deterministic한 point로 보지 않고 distribution으로 본다.  이를 근사하기 위해서 variational inverence를 사용한다.  

NN에 dropout을 적용한 것은 Bayesian Neuralnetworks의 objective와 같다.  

dropout은 ensemble의 개념이다.

여러 모델에 동일한 input을 넣어 output을 구하면 predictive mean/variance를 계산할 수 있으며  
predictive variance가 uncertainty를 나타낸다.  

ReLU에 비해 tanh가 더 잘 saturated되어 uncertainty가 bound 된다.  