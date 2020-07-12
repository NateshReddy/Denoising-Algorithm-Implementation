# Image Denoising Implementation
We have applied various ML models for Image Denoising on CIFAR-10 Dataset

### Models -
1. Denoising Autoencoder(DAE)
1. DeNoising Convolutional Neural Network(DnCNN)
1. Wide Inference Network(WIN)

### Dataset -
We have used CIFAR-10 dataset which consists of 60000 32x32 colour images in 10 classes, with 6000 images per class. There are 50000 training images and 10000 test images.

We have added noise to this dataset.
To do this we added gaussian noise with mean=0 and std=0.1 and then clip values back to 0-1.</br>
Mean=0 noise makes some parts of the image darker and some lighter after addition.

![GitHub Logo](/images/noisy_image.png)

### Denoising Autoencoder(DAE)
Now we define the building blocks of our DAE: a convolutional block and a deconvolutional block.</br>

Convolutional blocks consist of 3 operations: 2D convolution, batch normalization and ReLu activation. We use strides=2 to downsample data going through the network.</br>

Deconvolutional blocks also consist of 3 operations: 2D transposed convolution, batch normalization and also ReLu activation. Here strides=2 is used to upsample the data.

#### Our model architecture consist of:

* 4 convolutional blocks with downsampling
* 1 convolutional block without downsampling
* 4 deconvolutional blocks with upsampling, interleaving concatenations
* 1 final deconvolution that recreates image size (32, 32, 3)
* 1 activation layer with sigmoid that scales values to 0-1.

**Loss Function**: mean squared error</br>
**Optimizer**: Adam

#### Hyperparamters:
* Batch Size = 128
* no. of epochs = 40
* Learning rate =0.001

### Results
[GitHub Logo](/images/result1.png)

### Evaluation
**PSNR**: 27.972 </br>
**SSIM**: 0.983

## DeNoising Convolutional Neural Network(DnCNN)
