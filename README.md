# GradCam_Visualization

## Overview:
A technique for making Convolutional Neural Network (CNN)-based models more transparent by visualizing the regions of input that are “important” for predictions from models.

In practice, deep learning models are treated as “black box” methods, and many times we have no reasonable idea as to:

- Where the network is “looking” in the input image
- Which series of neurons activated in the forward-pass during inference/prediction
- How the network arrived at its final output

To help deep learning practitioners visually debug their models and properly understand where it’s “looking” in an image, Selvaraju et al. created Gradient-weighted Class Activation Mapping, or more simply, Grad-CAM.

## How it Works:
**"Grad-CAM uses the gradients of any target concept (say logits for “dog” or even a caption), flowing into the final convolutional layer to produce a coarse localization map highlighting the important regions in the image for predicting the concept.”**

![Image of GradCam](https://github.com/janmejaybhoi/GradCam_Visualization/blob/main/img/1%20hHPn81BbKEl7xDsHr5aSIA.jpg)

To obtain the class-discriminative localization map, Grad-CAM computes the gradient of yc (score for class c) with respect to feature maps A of a convolutional layer. these gradients flowing back are global-average-pooled to obtain the importance weights αck.

![Image of GradCam](https://github.com/janmejaybhoi/GradCam_Visualization/blob/main/img/1%20ATzleTWhhnC9kvSb4GStow.png)


Similar to CAM, Grad-CAM heat-map is a weighted combination of feature maps, but followed by a ReLU:

![Image of GradCam](https://github.com/janmejaybhoi/GradCam_Visualization/blob/main/img/1%20EagKCAdsdKHwSSvZwdDuww.png)


## Dataset:
The dataset used here is  [Image Scene Classification of Multiclass](https://www.kaggle.com/puneet6060/intel-image-classification) from kaggle.
This Data contains around 25k images of size 150x150 distributed under 6 categories.
{'buildings' -> 0,
'forest' -> 1,
'glacier' -> 2,
'mountain' -> 3,
'sea' -> 4,
'street' -> 5 }

The Train, Test and Prediction data is separated in each zip files. There are around 14k images in Train, 3k in Test and 7k in Prediction.
This data was initially published on https://datahack.analyticsvidhya.com by Intel to host a Image classification Challenge.
