## Transfer learning model

### Overview 
In this part, we use transfer learning to build a model for our competition. Transfer learning means that we use a pre-trained model and change it to fit our data. We do this by changing the top layers of the pre-trained model. This allows us to ‘transfer’ the knowledge of the model from its original domain to our domain.

### Advantages of transfer learning
In general, transfer learning offers the following benefits:
* Helps solve complex real-world problems with several constraints
* Tackle problems like having little or almost no labeled data availability
* Ease of transferring knowledge from one model to another based on domains and tasks
* Use extremely complex model structures without having to develop them yourself
* Reduce computational resources since only the top layers of a model need to be trained

In our case, the biggest benefit of using transfer learning is that we can use an extremely complex model structure without having to develop it and train it ourselves. 

### Pre-trained model we use
For our model, we use the pre-trained VGG16 model. VGG16 was developed by researchers at the University of Oxford and offered an improvement over AlexNet. The model achieves 92.7% top-5 test accuracy in ImageNet, which is a dataset of over 14 million images belonging to 1000 classes. The model consists of 13 convolutions and 5 poolings. It also includes 3 layers of fully connected layers. 

### Customizing the pre-trained model
To fit VGG16 to our purpose of aerial cactus identification, we replace the top 3 layers with our own layers. This allows us to take advantage of the 13 convolutions and 5 poolings of VGG16 and at the same time ensures that our model is customized to cactus detection.

### Our code
In our code, we first import the data (images). We then download the VGG16 model and freeze all the layers besides the top 3 layers. We then define our own top layers and train them on the images. This completes the transfer learning process and allows us to test our model on the test data.

