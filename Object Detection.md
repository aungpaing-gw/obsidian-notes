Identify all objects in an image with bounding boxes

## Inputs
- RecordIO or image format (jpg or png)
- with image format, supply a JSON file for annotation data for each image.

## Usage
- takes an image as input, outputs all instances of objects in the image with categories wand confidence scores
- VGG-16 | ResNet-50 as backbone and SDD for head
- Transfer Learning mode / incremental training
- Use augmentation to prevent overfitting

## Hyperparameters
- batch size, lr, optimizer

## Instance Types
- GPU instances for training (multi-GPU and multi-machine OK)
	- ML.p2.xlarge, ML.p2.8xlarge, ML.p2.16xlarge, ML.p3.2xlarge, ML.p3.8clarge, ML.p3.16xlarge
- Use CPU or GPU for inference
	- C5, M5, P2, P3 are all OK