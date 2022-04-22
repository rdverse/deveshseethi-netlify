---
title: Quantization
date: 2022-04-24
image: /assets/images/2021/coolimage.jpg
---

Currently working on this post!

Resources : 


The weights learned in a neural network can be of any bit length such as int8, bfloat16, fp16, and fp32, where fp32 has the largest number of bits and int8 has the least. In large networks, due to explosion of many weights, I 
 idea of converting 

Quantization is a process of downcasting floating-point digits from a higher dimension to a lower dimension. Due to this, we can achieve faster inference time and reduce computational overhead on edge devices. In our model, we have quantized the weights from float-32 format to float-16 format at each layer and for each activation function. When we applied quantization technique to the model, the inference time decreased from $172$ ms to $82$ ms, giving a two-fold improvement in the inference time. 