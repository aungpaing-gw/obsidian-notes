Assign one or more labels to an image

## Inputs
- Apache MXNet RecordIO
	- Not Protobuf!
	- This is for interoperability with other deep learning frameworks.
- Raw JPG or PNG images.
- Image format requires .lst files to associate image index, class label, and path to the image
- Augmented Manifest image format enables Pipe mode

## Usages
- ResNet CNN under the hood
- Default image size is 3-channel 224 x 224 (imageNet's dataset)

## Hyperparameters
- lr, batch_size, optimizer, L1, L2, gamma

## Instance Types
- GPU instances for training (P2, P3), Multi-GPU and multi-machine OK.
- CPU or GPU for inference (C4, P2, P3)