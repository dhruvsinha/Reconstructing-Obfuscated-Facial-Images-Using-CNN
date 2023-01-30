# Reconstructing Obfuscated Facial-Images Using Convolutional Autoencoder

## Abstract
Our paper aims to reconstruct obfuscated facial images. We have used a convolutional
autoencoder that takes noisy, pixelated, or blurred images as input and attempts to reconstruct recognizable facial images. For training, pixel, perceptual and a weighted combination of the two have been used as loss functions. The results demonstrate that our
trained model can successfully reconstruct facial images from highly obfuscated images,
with some limitations in clarity, relative to the ground truth. Obfuction techniques are widely used to protect the privacy of any individual. However, using the technique we employ, it is possible to reconstruct the original image. Therefore, we need to think more deeply about the techniques we employ to hide an individual's indentity.

## Python Files attached
The first part of this project is data cleaning. We clean the data by standardizing each image to a particular size and also create the training dataset by inducing different types of noice in the dataset. 'data_preparation.ipynb' handles the data cleaning part. We train the autoencoder and evaluate its performance in 'autoencoder_training.ipynb'. 



