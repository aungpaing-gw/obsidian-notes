Prevent Overfitting, high accuracy in training and low in validation.

- Use fewer layer, shallower network
- Use dropout
- Early stopping
- L1 and L2 Regularization

## L1 and L2 Regularization
A regularization term is added as weights are learned.
- L1 is the sum of weights
	- performs feature selection - certain features go to 0
	- Computationally inefficient
	- Sparse output
- L2 is the sum of square of the weight
	- All features remain considered, just weighted
	- Computationally efficient
	- Dense output