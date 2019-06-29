## Convolutional Neural Network using PyTorch

### General Analysis on PyTorch
One of the well known benefits of PyTorch is its simplicity. Compared to understanding the models for keras setting up the model for PyTorch was relatively easier even though it was the first time being exposed to this package. Also, from looking at the codes for the PyTorch model, another benefits we noticed was its ability to be replicated into a different image recognition model. 

Another benefits of PyTorch that we spent time exploring was its efficiency in memory usage and running time. Especially, we explored on PyTorch's ability generate data on multiple cores in parallel and feed into the model for efficient memory usage, which would be useful for large datsets. (We were able to partition the data to be multiprocessed, but because the model did not run successfully, we ended up submitting the non-multiprocessing version of the model)

### Approaches for the Competition

1. Data Split (test, validation) = (7:3)
2. Define class 'Cactus' to read in the dataset
3. Image Preprocessing: mean = [0.5, 0.5, 0.5] / std = [0.5, 0.5, 0.5]
4. Define class ' CNN' to build a model using `nn.Module`
5. Set up loss functin and the optimizer
6. Train the model with 25 epochs
7. Test the model with the validation set

- cv2 was used to read the images into the model
- When defining the `DataLoader` class, we set parameters in a way that makes batches look differnt among the epochs being ran in the model. We did want to try running the batches in parallel by setting `num_workers` to non zero, but the local computer wasn't able to handle the process.

After reading in the data with a defined class, the images were tranformed and generated into train and validation dataset for the model. Using the `nn.Module`, we defined the convolutional neural network model with five convolutional layer and batch norm, then activation and then pooling layer.


### Results

The initial submission scored 0.9990 and was at the 524th place on the Kaggle scoreboard.
We tried to make some changes to the number of hyperparameters, number of layers and even the train and test split proportion and was able to increase the score up to 0.9997. 
