Taking a model that was pretrained on one dataset, freezing the initial layers and letting it relearn the last few layers of the model on a different dataset.
The benefits of this are:
- It is computationally less expensive than training a full neural network from scratch.
- When you don't have a lot of data or data labeling is expensive, using a pretrained model can provide better model performance than training a model from scratch.