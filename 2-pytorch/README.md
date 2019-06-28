## Convolutional Neural Network using PyTorch

### General Analysis on PyTorch
One of the well known benefits of PyTorch is its simplicity. Compared to understanding the models for keras setting up the model for PyTorch was relatively easier even though it was the first time being exposed to this package. Also, from looking at the codes for the PyTorch model, another benefits we noticed was its ability to be replicated into a different image recognition model. 



### Approaches for the Competition

- cv2 was used to read the images into the model
- When defining the `DataLoader` class, we set parameters in a way that makes batches look differnt among the epochs being ran in the model. We did want to try running the batches in parallel by setting `num_workers` to non zero, but the local computer wasn't able to handle the process.

### Results
