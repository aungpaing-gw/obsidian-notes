- Pixel-level object classification
- Useful for self-driving vehicles, medical imaging diagnostics, robot sensing

## Inputs
- JPG images and PNG annotations
- For both training validation
- Label maps to describe annotations
- Augmented manifest image format supported for Pipe mode.
- JPG images accepted for inference.

## Model
- Build on MXNet Gluon and Gluon CV
- Choice of 3 algorithms:
	- Fully-Convolutional Network (FCN)
	- Pyramid Scene Parsing (PSP)
	- DeepLabV3
- Backbones
	- ResNet50
	- ResNet101
	- Both trained on ImageNet

## Instance Types
- Only GPU supported for training (P2 or P3) on a single machine only.
	- Specifically ml.p2.xlarge, ml.p2.8xlarge, ml.p2.16xlarge,
	- ml.p3.2xlarge, ml.p3.8xlarge, or ml.p3.16xlarge
- Inference on CPU (C5 or M5) or GPU (P2 or P3)