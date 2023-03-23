# Inception V3 Binary Classifier

The Inception V3 neural network is pre-trained on the ImageNet dataset. I have used this model for classifying images as having potholes (positive) or not (negative).

The following two datasets were used for training. The two sets were concatenated to create a larger dataset. The combined data set contains 10,662 training images, 1184 validation images, and 984 testing images. A few samples from the training set are shown below. Both the datasets were generated by the same person for a paper. The images were collected by mounting a camera on the vehicle’s dashboard. The images (RGB) are rescaled (480x640) using the image_dataset_from_directory function offered by Keras. 

- [Nienaber_simple](https://www.kaggle.com/datasets/felipemuller5/nienaber-potholes-1-simplex)
- [Nienaber_complex](https://www.kaggle.com/datasets/felipemuller5/nienaber-potholes-2-complex)

I downloaded the dataset from Kaggle to my Google Drive through Kaggle's API and a json file containing my username and key. I imported the dataset to my Google Colab notebook using the image_dataset_from_directory function offered by Keras. The dataset was split into training, validation, and test sets. The Inception V3 pre-trained model was imported from Keras without including the top layer. I added a set of new layers on top of the imported base model. I trained the net for 10 epochs (after freezing imported base layers and only changing the parameters of the newly added layers) with a large learning rate. Then, I trained the net for 15 epochs (after unfreezing all layers and changing parameters of both the base layers and newly added layers) with a small learning rate. I used the binary cross entropy loss and the sparse categorical cross entropy loss with the Adam optimizer.	

The neural network gave an accuracy of 91% with the binary cross entropy loss and a test accuracy of 90% with the sparse categorical cross entropy loss. 



