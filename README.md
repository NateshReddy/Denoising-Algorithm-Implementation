# Image Denoising Implementation
We have applied various ML models for Image Denoising on CIFAR-10 Dataset

### Models -
1. A Denoising Autoencoder(DAE)
1. DeNoising Convolutional Neural Network(DNCNN)
1. Wide Inference Network(WIN)

### Dataset -
We have used CIFAR-10 dataset which consists of 60000 32x32 colour images in 10 classes, with 6000 images per class. There are 50000 training images and 10000 test images.

We have added noise to this dataset. 
To do this we added gaussian noise with mean=0 and std=0.1 and then clip values back to 0-1.\n
Mean=0 noise makes some parts of the image darker and some lighter after addition.
