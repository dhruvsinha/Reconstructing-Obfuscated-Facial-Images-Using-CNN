# Reconstructing Obfuscated Facial Images Using Convolutional Autoencoder

## Abstract
Our paper aims to reconstruct obfuscated facial images. We have used a convolutional
autoencoder that takes noisy, pixelated, or blurred images as input and attempts to reconstruct recognizable facial images. For training, pixel, perceptual and a weighted combination of the two have been used as loss functions. The results demonstrate that our
trained model can successfully reconstruct facial images from highly obfuscated images,
with some limitations in clarity, relative to the ground truth. Obfuction techniques are widely used to protect the privacy of any individual. However, using the technique we employ, it is possible to reconstruct the original image. Therefore, we need to think more deeply about the techniques we employ to hide an individual's indentity.

## Files attached
The first part of this project is data cleaning. We clean the data by standardizing each image to a particular size and also create the training dataset by inducing different types of noice in the dataset. 'data_preparation.ipynb' handles the data cleaning part. We train the autoencoder and evaluate its performance in 'autoencoder_training.ipynb'. The detailed project report is in the attached pdf file.

## Obfuscation techniques used

In this project, we used 3 obfucation techniques- speckle noise, gaussian blur, and pixelation. The details of each of these noises are mentioned in the image. However, we can see here how these noises can alter an image. 

| ![noise_images.jpg](/obfucation_images/noise_images.jpg) | 
|:--:| 
| *Obfuscation techniques* |

## Architecture Used

Our model input and output are of the shape $(128\times128\times3)$
A convolutional neural network has been used to un-obfuscate the input facial images which are obfuscated. For the autoencoder, our input image is encoded using 2 convolutions layers, each of which are followed by a max pool layer. Each convolutional layer has $32$ $3\times3$ feature maps with a RELU activation function. The maxpooling windows are of size $3\times3$
\newline The encoded image, then, is passed through 2 convolutions layers, each of which are followed by an upsampling layer. Each convolutional layer has $32$ $3\times3$ feature maps with a RELU activation function and the up sampling window is of size $2\times2$. The final layer convolution layer consists of 3 filter maps of $3\times3$, with the sigmoid activation function. I use the Adam optimizer to update parameters in our network. We use two different loss functions i.e. the Mean squared error/pixel by pixel loss and perceptual loss. Here is the summary of the model. 

| ![model.jpg](/obfucation_images/model.jpg) | 
|:--:| 
| *Model Summary* |

## Result

While detailed results can be read in the project report, the result of training using perceptual loss function is attached. As we can see in these table, the model is able to reconstruct highly obfucated images. Therefore, this result should be seen with a pinch of salt. Maybe the model is overfitting because of which the results are spectacular. 

| ![perceptual_loss.jpg](/perceptual_loss/model.jpg) | 
|:--:| 
| *Model Summary* |
