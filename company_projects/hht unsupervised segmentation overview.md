# HHT Unsupervised segmentation overview

## Models
1. [[mask contrast]]
2. self-supervised
3. differential feature clustering
4. Dataset GAN

| Model                           | evaluate   | fine tuned | github official repo                                                              |
| ------------------------------- | ---------- | ---------- | --------------------------------------------------------------------------------- |
| mask contrast                   | PASCAL VOC | None       | https://github.com/wvangansbeke/Unsupervised-Semantic-Segmentation                |
| self-supervision                | CHAOS      | CHAOS      | https://github.com/cheng-01037/Self-supervised-Fewshot-Medical-Image-Segmentation |
| Differential Feature Clustering | BSDS500    | BSDS500    |                                                                                   |
| Dataset GAN                     |            |            |                                                                                   |


## Datasets
| Dataset                   | Remark          | Url                                                                                |
| ------------------------- | --------------- | ---------------------------------------------------------------------------------- |
| BSDS500 (Differential FC) | HomePage        | https://www2.eecs.berkeley.edu/Research/Projects/CS/vision/bsds/                   |
|                           | Kaggle Download | https://www.kaggle.com/balraj98/berkeley-segmentation-dataset-500-bsds500/download |
| CHAOS (Slef-supervision)  | Train           | https://zenodo.org/record/3431873/files/CHAOS_Train_Sets.zip?download=1            |
|                           | Test            | https://zenodo.org/record/3431873/files/CHAOS_Test_Sets.zip?download=1             | 


## Folder Structure

### Origin folder (user preparation)
```python
hht_unsupervised

	| - utils_fun.py (for dataset splitting)
	| -  De-Noising / Segmentation

		# User prepare
		| - dataset
			| - dataset Folder (eg. Fibres)
				| - [*.jpg | *.png]
		# User prepare (detail please refer to README.md)
		| - pretrained
			| - model A
				| - original_pretrained_model
					| - [model.pth | .pt | .pth.tar]
				| - SEM_trained_model
					| - [model.pth | .pt | .pth.tar]

		# De-noising && Segmentation
		| - train_main.py
		| - test_main.py
		
		# Overall configurations
		| - config.yml

		| - ModelA
			# Model architecture configurations
			| - model_config.yml

		| - ModelB
			| - train_config.yml
			| - test_config.yml

		# Segmentation
		| - modelA.py   (output train_modelA, test_modelA `API`)
		| - modelB.py
		| - modelC.py
```


### After train
Running `python train_main.py`
```python
hht_unsupervised
  | - De-noising | Segmentation
		# Dataset auto split
		| - dataset
			| - dataset Folder (eg. Fibres)
				| - [*.jpg | *.png]
			| - splitted-Fibres
				| - train
					| - [*.jpg | *.png]
				| - valid
				| - test

	| ...

	| - fine_tuned
	  | - model A / model.pth
	  | - model B / model.pth

```


### After Evaluation
Running `python test_main.py`
Default run inference with model trained on `SEM Dataset`.
```python
hht_unsupervised
  | - De-noising | Segmentation

	| ...

	| - fine_tuned
	  | - model A / model.pth
	  | - model B / model.pth

	| - outputs_dir
	  | - model A / *.jpg
	  | - model B / *.jpg

```

### Config Files
`config.yml `file

```python
dataset:
  # Dataset to be splitted
  root_dataset  : [dataset/Fibres/, dataset/Particles/, dataset/Porous_Sponge]    
  splitted_dataset : dataset/splitted-dataset/
  # valid dataset is sampled from train dataset. train + test = 1
  split_ratio   : [0.8, 0.2, 0.2]    
  train_path    : train
  valid_path    : valid
  test_path     : test


train:
  epochs: 80

  modelA:
    train_config_path: train_config.yml
	pretrained       : pretrain.pth.tar
    output:
      save_path      : fine_tuned/model A
      other configs  : config value
 

test:
  modelA:
    test_config_path : test_config.yml
    # Model trained on SEM Dataset
    model_path       : fine_tuned/mask-contrast
    # Visualization output dir
    save_path        : outputs_dir/mask-contrast
  
  modelB:
    test_config_path  : model_config.yml
    model_path        : ""
    save_path         : outputs_dir/differential-clustering

```

Example: `train_config` file

```python
# Dataset
train_db_name: SEMSegmentation
train_db_kwargs:
   saliency: unsupervised_model
num_workers: 2
train_batch_size: 4

# Model
backbone: resnet50
backbone_kwargs:
   dilated: True
   pretraining: imagenet_moco 
   moco_state_dict: ../segmentation_weights/moco_v2_800ep_pretrain.pth.tar
model_kwargs:
   ndim: 32
   head: linear
   upsample: True
   use_classification_head: True
head: deeplab
freeze_layers: False

# Optimizer
epochs: 80
optimizer: sgd
optimizer_kwargs:
   lr: 0.004
   weight_decay: 0.0001
   momentum: 0.9
   nesterov: False
scheduler: poly

# MoCo
moco_kwargs:
   T: 0.5 # Temperature
   m: 0.999 # Momentum
   K: 256 # Negatives
```



# Stylegan

- environment : Python 3.7 and 3.8
- manual annotation is needed (impossible to automate)

# Self-supervision
- will reply later

## Automation
- client want to adjust the parameters.
- change the file model path
- loss output file name 
- ratio of training and testing dataset
- Image size is changeable. downscale.