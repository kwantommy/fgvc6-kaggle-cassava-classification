
# Cassava disease classification using multiple classification architectures: 
1. ResNet50 V1
2. ResNet101 V1
3. ResNet50 V2
4. ResNeXt50
5. SE-ResNeXt101

## Data augmentation:
1. Zoom (0.1)
2. Horizontal Flip
3. Vertical Flip 

These augmentations were chosen because for the purposes of the images, these augmentations do not interfere with the integrety of the image. For example, a plant flipped horizontally can still be seen as a plant and therefore, disease feature extraction would not be affected. 

 <p float="left">
 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/images/horizontal_flip.png width=400 float="left"/>
 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/images/vertical_flip.png width=400 float="left"/>
   <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/images/zoom.png width=400 float="left"/>
 </p>
 

## ResNet50V1
Link: https://keras.io/applications/#resnet

Parameters: 25,636,712 (25,583,592 trainable)

 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/images/Resnet50_training.png width=400/>


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

2. Potentially add data augmentation
3. K-fold cross validation
4. Test time augmentation
