
## Cassava disease classification using: 
1. ResNet50V1
2. MobileNetV2
3. VGG16
4. SE-ResNeXt101-32x4d

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
 

## ResNet50V1 (Val_acc = 0.95, 10 epochs)
https://arxiv.org/abs/1512.03385

Trained using 336x336 image size, 3x augmentation.
Parameters: 25,636,712 (25,583,592 trainable)

 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/resnet_architecture.png width=200/>
 
 ### Loss and accuracy curves
  <p float="left">
 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/resnet_50v1_loss.png width=400 float="left"/>
 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/resnet50v1_accuracy.png width=400 float="left"/>
 </p>
 
## MobileNetV2 (Val_acc = 0.93, 10 epochs)
https://arxiv.org/pdf/1801.04381.pdf

Trained using 336x336 image size, 3x augmentation.
Parameters: 2,257,984 (2,223,872 trainable)


 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/mobilenetv2_architecture.png width=200/>


### Loss and accuracy curves
 <p float="left">
 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/mobilenetv2_loss.png width=400 float="left"/>
 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/mobilenetv2_accuracy.png width=400 float="left"/>
 </p>
 
## VGG16 (Val_acc = 0.94, 10 epochs)
https://arxiv.org/abs/1409.1556

Trained using 336x336 image size, 3x augmentation.
Parameters: 14,717,253 (14,715,461 trainable)

 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/vgg16_architecture.png width=400/>
 
### Loss and accuracy curves
 <p float="left">
 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/VGG16_loss.png width=400 float="left"/>
 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/VGG16_accuracy.png width=400 float="left"/>
 </p>
 
 
## SE-ResNeXt101-32x4d (Val_acc = 0.85, 10 epochs)
https://arxiv.org/abs/1611.05431

Trained using 224x224 image size, 3x augmentation.
Parameters: 47,054,517 (46,916,661 trainable)

 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/resnext_architecture.png width=200/>

### Loss and accuracy curves
 <p float="left">
 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/se_resnext_loss.png width=400 float="left"/>
 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/se_resnext_accuracy.png width=400 float="left"/>
 </p>

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

## Appendix

Sample training (top to bottom - ResNet50, MobileNet, VGG16, SE-ResNeXt)

### ResNet
 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/Resnet50_training.png width=400/>
 
 ### MobileNet
 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/mobilenetv2_training.png width=400/>
 
 ### VGG16
  <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/VGG16_training.png width=400 />
  
  
  ### SE-ResNeXt
 <img src=https://github.com/kwantommy/fgvc6-kaggle-cassava-classification/blob/master/Images/se_resnext_training.png width=400 />

