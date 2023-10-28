# Deep Residual Learning for Image Recognition
Paper     : Deep Residual Learning for Image Recogition
Github   : 
Tag        : Backbone
solved   : Degradation (Accuracy get saturated)

## Main contribution
The model enable deep layers of models to be trained. The authors testing up to 152 layers and it still work fine (almost same performance as the lower layers model.), proving that it is feasible to use deeper layers model to enrich the feature encodings.

### Notorious vanishing/exploding gradients
Solved : Normalized Initialization, Intermediate batch normalizaiton 
### Degradation
With the network depth increasing, accuracy gets saturated and then degrades rapidly. Degradation is not caused by overfitting, and adding more layers to a suitably deep model leads to higher training error (Experimental result).  It indicates that not  all systems are easy to optimize.
If we get a shallow model and a similar model with deeper layers, we will found an **identity** mapping. So, theoretically, adding deeper layers should result in at least equal accuracy with the shallower model. But, the reality is not. So the author explicitly add identity mapping layers to the model, and it works.
`The authors reformulate the layers as learning residual functions with reference to the layer inputs, instead of learning unreferenced functions.`

## Implementation
The input is resized with shorter side randomly sampled in [256, 480] for scale augmentation. A [224 x 224] crop is randomly sampled from an image or its horizontal flip, with the per-pixel mean subtracted. The **standard color augmentation** is used. Batch normalization is used after convolution layer, before activation function. SGD and mini-batch of 256. The learning rate starts from 0.1 and is divided by 10 when the error plateaus, and the model is trained for up to **60 x 10^4** iterations. weight decay of 0.0001 and momentum of 0.9. Dropout is not used.  
## Questions