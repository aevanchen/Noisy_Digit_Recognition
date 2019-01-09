# Noisy_Digit_Recognition
# Objectives
The project is to apply machine learning algorithms to design models to classify image of digits. Each image is 28 by 28 pixel in size, a representation of digit from 0 to 9. It aims to maximize the classify accuracy in the presence of different kinds of noise. The text dataset is known to be mixed with clean digit images and nosiy images. Among noisy images, there are two noise patterns
* Pattern 1. Stains effects
![noise](img/1.jpeg)

* Pattern 2. Gasuuian noise
![noise](img/2.jpeg)

It is known that the proportion of the clean images, pattern 1 images, pattern 2 images are 4:4:2.


# Dataset and Preprocessing 
Split the dataset into Train and Validation set with a ratio of 4:1. Among them, the proportion of the clean images, pattern 1 images, pattern 2 images are 4:4:2. 

To model noise, I add these two kinds of noise onto the original clean digit images.

Training data normalization and shape the training images into 3 dimensions: height=28, weight=1. canal=1.

For better classification result, the target categorical variable is converted into dummy variable format using one hot vectors, e.g, class ‘2’ is converted into [0,0,1,0,0,0,0,0,0]


# Models
1. Direct CNN 
Directly train a CNN model to classify noisy images. 
Data augumentation is used to increase the size of training set, this is done by rotating the images, etc.
2. Autoencoder + CNN
Another way thinking of this task is to first reconstruct the clean images from the noisy images then apply a CNN classification model to the reconstructed images.
Two types of autoencoder are tested:
A. Denoising Autoencoder
B. Variational Autoencoder 

Detailed theory of these two mechinisms can be found in the notebook: [Autoencoder](AutoEncoders.ipynb)

# Results
The reconstructed images from autoencoder for both pattern of noise is shown below
Pattern 1:

![noise](img/3.jpeg)


Pattern 2:

![noise](img/4.jpeg)



|Models 	|	Overall accuracy| 
|:--------------:|:-----------:|
|Direct CNN|	0.976 |
|Denoising Autoencoder 	|0.981 	|
|Variational Autoencoder 	|0.962 	|

</b>Validation accuracy for all the models</b>



