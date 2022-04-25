---
title: Quantization
date: 2022-04-27
image: /assets/images/2021/coolimage.jpg
---

Currently working on this post!

A neural network as we now is composed of layers and each layer is composed of several neurons. When we reach the neuron level, every neuron is represented by f(x) = w^T*x + b, where the input vector x is multiplied with a weight matrix, w^T. Based on what device we are using such as CPU or GPU, the weight matrix and input vector are to be loaded in the RAM or VRAM, respectively. Therefore, the memory footprint of each computation during training in the backpropagation or inference that is multiplication of weight matrix with neuron input depends on the size of each element in the w^T. For example, if the weigts are in fp32 format, then we have one sign bit, 8 bits for exponent and 23 bits for mantissa. In total occupying 32 bits memory. Therefore, when we have a large neural network where each inference takes over millions of multiplication, we are looking at conducting multiplication operations on 32-bit length vectors. This results in significantly large memory usage which in turn increases the energy consumption and subsequently results in slower executions. 

Thank to quantization, we can downsize these large neural networks at a neuronal level by simply converting the format of the weights in the neural network. Although we talked about a DNN in the above example, the same applies for CNN, RNN, LSTMs. 

In table-1 we show all different formats and their memory footprint. You might notice that fp16 and bfloat16 have the same memory footprint. However, bfloat16 provides larger range by reducing the number of bits in mantissa and increasing the number of bits in the exponent. Therefore, using bfloat16 is more favorable over fp16 for a boost in the accuracy. 


# Implementation of quantization in Intel oneAPI


<!-- 
Quantization in neural networks means down
The weights learned in a neural network can be of any bit length such as int8, bfloat16, fp16, and fp32, where fp32 has the largest number of bits and int8 has the least. In large networks, due to explosion of many weights, I 
 idea of converting  -->
<!-- 
Quantization is a process of downcasting floating-point digits from a higher dimension to a lower dimension. Due to this, we can achieve faster inference time and reduce computational overhead on edge devices. In our model, we have quantized the weights from float-32 format to float-16 format at each layer and for each activation function. When we applied quantization technique to the model, the inference time decreased from $172$ ms to $82$ ms, giving a two-fold improvement in the inference time.  -->