
# Cassava disease classification using multiple classification architectures: 
1. ResNet50 V1
2. MobileNet V2
3. VGG16

The defining feature of ResNet is its residual connections. ResNeXt, built on top of ResNet, incorporates cardinality blocks and SE-ResNet/SE-ResNeXt incorporates squeeze and excitation blocks.

<p float="left">
 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/resnet_architecture.png width=200 float="left"/>
 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/se.png width=200 float="left"/>

 </p>
 
## Data augmentation:
1. Zoom (0.1)
2. Horizontal Flip
3. Vertical Flip 

These augmentations were chosen because for the purposes of the images, these augmentations do not interfere with the integrety of the image. For example, a plant flipped horizontally can still be seen as a plant and therefore, disease feature extraction would not be affected. 

 <p float="left">
 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/horizontal_flip.png width=200 float="left"/>
 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/vertical_flip.png width=200 float="left"/>
   <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/zoom.png width=200 float="left"/>
 </p>
 

## ResNet50V1 (Val_acc = 0.91, submission = 0.84)
Link: https://keras.io/applications/#resnet

Parameters: 25,636,712 (25,583,592 trainable)

 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/Resnet50_training.png width=600/>


## Model Improvements
There are many improvements that can be made to the model but were not implemented due to time and computation purposes: 

1. Increase image size 
For reference, each epoch takes: 

Image Size: 500x500 - Colab GPU: 15 minutes, i5-8300H CPU: 9 hours

Image Size: 336x336 - Colab GPU: 8 minutes, i5-8300H CPU: 5 hours

Image Size: 224x224 - Colab GPU: 5 minutes, i5-8300H CPU: 1 hour 30 minutes

2. Potentially add data augmentation
3. K-fold cross validation
4. Test time augmentation
5. Callbacks (though may not be useful due to the low training epochs)
ReduceLROnPlateau
EarlyStopping
6. Add additional Dense layers to the base model output including DropOut.
7. Potentially remove the mean from training data. 
