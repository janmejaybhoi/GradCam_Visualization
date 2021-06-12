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

![Image of GradCam](https://octodex.github.com/images/yaktocat.png)
