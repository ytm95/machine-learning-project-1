
## Convolutional Neural Networks Model 

  Since this is an Image Recognition problem, we are using Convolutional Neural Networks, which have been designed for unstructured data like images and text data. We use `Keras` and `Tensorflow` to take advantage of the computational abilities of `Tensorflow` with the ease of programming of `Keras`. We use `scikitlearn` to implement a random grid search and perform k-cross-validation. `OpenCV` is used to read in the images. 
 
 ### 1. Pre-processing for Neural Network
 
#### Reading in data 
 
 The training and test images are in `.jpg` format read in and are converted into `numpy` arrays. There are 3 color channels and the images were of size 32 by 32 pixels. Thus the array is of size `[32,32,3]`. Labels were joined to the training images dataset by joining on the Image ID. The data was divided by 255 to normalize it. 
 
#### Image data augmentation
 
In order to improve the performance of our NN model, we perform data augmentation. Data augmentation is a technique to artificially create new training data from existing training data. It involves creating transformed versions of images such as shifts, flips, zooms, etc. and adding these to the training dataset.

### 2. Building the model
 
We use a few convolutional layers, each followed by normalization and a dropout. We did not use pooling since we found that our model performed better without pooling. Our images are already quite pixelated and we did not particularly need to compress data, so maybe that could be a possible explanation.
The convolutional layers are followed by a flattening layer and few layers of hidden units, each having an L1-L2 regularizer. Finally we pass the output through a single output unit. 
 
#### Grid Search

We decided to use grid search over the following hyperparameters:
* Optimizer
* Learning Rate
* Activation function
* Number of neurons/hidden units in each layer
* Number of filters in convolutional layers
* Dropout rates 
* L1 and L2 regularization

We run a random grid search instead of a cartesian grid search to reduce the computation time. We use 3-fold cross validation during the grid search on the entire dataset for 80 epochs. We use a loss function of `mean_squared_error` (this surprisingly gives us better results than using `binary_crossentropy` which is usually used in binary classification problems) and choose the best performing model to predict on our test data. 

The grid search notebook can be found [here](https://github.com/netinupur/machine-learning-project/blob/master/1-keras-and-tensorflow/CNN%20from%20Kaggle%20with%20random%20gridsearch.ipynb)

The final model and results can be found [in this notebook](https://github.com/netinupur/machine-learning-project/blob/master/1-keras-and-tensorflow/Keras_CNN_best_model.ipynb)
