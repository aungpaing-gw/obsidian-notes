# A ConvNext for the 2020s
*Authors : Zhuang Liu, Hanzi Mao, Chao-Yuan Wu, Christoph Feichtenhofer, Trevor Darrell, Saining Xie*
*Organization : Facebook AI Research (FAIR), UC Berkeley*
Code: [Facebook Research / github](https://github.com/facebookresearch/ConvNeXt)

## Abstraction
After introduction of [[Swin-Transformer]] , transformer have proved powerful in the computer vision task. In this paper, the authors tried to 'modernize' a standard ResNet toward the design of a vision transformer. And proved that some modifications can be made to improve the performance of a standard ConvNet model.

## Keypoints (modernize roadmap)
1. Training Techniques (results show that a significant portion of the performance difference between ConvNets and [[ViT]] may be due to training techniques)
	- 300 epochs
	- [[AdamW optimizer]]
	- Data Augmentation : [[Mixup]], [[Cutmix]], RandAugment, Random Erasing
	- Regularization : [[Stochastic Depth]], [[Label Smoothing]]
	- [[Cosine decaying Schedule]].
	- [[Exponential Moving Average]].
2. Macro Design
	- Change Stage compute ratio `[(3, 4, 6, 3) to (3, 3, 9, 3)]`
	- Change stem to **Patchify** ( 4 x 4 non-overlapping convolution )
3. ResNeXt-ify
	- grouped convolution
4. Inverted Bottleneck
	- ![[convnext_inverted.png]]
5. Large Kernel Size
	- 7 x 7 depthwise convolution
6. Micro Design
	- Replace ReLU with GELU.
	- Fewer activation functions.
	- Fewer normalizaiton layer.
	- Substituting BN with LN.
	- Separate downsampling layers.
		- 2x2 conv layer with stride 2
		- adding normalization layers wherever spatial resolution is changed can help stablize training.


### ResNeXt-ify
>Depthwise convolution = grouped convolution where the number of groups equals the number of channels, it has been popularized by MobileNet and Xception, due to better FLOPs / accuracy trade-off.

>Depthwise convolution is similiar to the weighted sum operation in self-attention, which operates on a per-channel basis.

The combination of depthwise and 1 x 1 convs leads to a separation of spatial and channel mixing, a property shared by[[ ViT]], where each operation either mixes information across spatial or channel dimension, but not both.

## Conclusion
ConNeXt achieve transformer like module by using depthwise convolution layer, which separate spatial and channel learning separatly.
Also, this paper study the effect of different modules on the model performance.