
# Cassava disease classification using multiple classification architectures: 
1.
2.
3.
4.
ResNet50 and 

## Data augmentation:
1. Zoom (0.1)
2. Horizontal Flip
3. Vertical Flip 

I chose these 3 because for the purposes of the images, these augmentations do not interfere with the integrety of the image. For example, a plant flipped horizontally can still be seen as a plant and therefore, disease feature extraction would not be affected. 


## Model Improvements
There are many improvements that can be made to the model but were not implemented due to time and computation purposes: 

1. Increase image size 
For reference, each epoch takes: 

Image Size: 500x500
Colab GPU: 15 minutes
i5-8300H CPU: 9 hours

Image Size: 336x336
Colab GPU: 8 minutes
i5-8300H CPU: 5 hours

Image Size: 224x224
Colab GPU: 5 minutes
i5-8300H CPU: 1 hour 30 minutes

2.
3.
4.
5.
