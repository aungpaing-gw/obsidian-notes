[source](https://pytorch.org/blog/introduction-to-quantization-on-pytorch/)

## What is quantization
Quantization refers to techniques for doing both computations and memory accesses with lower precision data, usually int8 compared to floating point implementations. This enables performance gains in several important areas:

-   4x reduction in model size;
-   2-4x reduction in memory bandwidth;
-   2-4x faster inference due to savings in memory bandwidth and faster compute with int8 arithmetic (the exact speed up varies depending on the hardware, the runtime, and the model).

## Device and Operator Support
The set of available operators and the quantization numerics also depend on the backend being used to run quantized models. Currently quantized operators are supported only for CPU inference in the following backends: x86 and ARM. 

However, quantization aware training occurs in full floating point and can run on either GPU or CPU. Quantization aware training is typically only used in CNN models when post training static or dynamic quantization doesn’t yield sufficient accuracy. This can occur with models that are highly optimized to achieve small size (such as Mobilenet).


## Choosing an approach
The choice of which scheme to use depends on multiple factors:

1.  Model/Target requirements: Some models might be sensitive to quantization, requiring quantization aware training.
2.  Operator/Backend support: Some backends require fully quantized operators.


[source](https://pytorch.org/tutorials/recipes/quantization.html)
## Introduction
Quantization is a technique that converts 32-bit floating numbers in the model parameters to 8-bit integers. With quantization, the model size and memory footprint can be reduced to 1/4 of its original size, and the inference can be made about 2-4 times faster, while the accuracy stays about the same.


[Docs>Quantization](https://pytorch.org/docs/stable/quantization.html)
[Backend/Hardware Support](https://pytorch.org/docs/stable/quantization.html#backend-hardware-support)



Install pytorch_tensorrt
pip install torch-tensorrt==1.1.0 --find-links https://github.com/pytorch/TensorRT/releases/expanded_assets/v1.1.0