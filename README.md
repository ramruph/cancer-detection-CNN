# Problem Description and Data
This Kaggle competition is a binary image classification problem where I will identify metastatic cancer in small image patches taken from larger digital pathology scans. I will implement a CNN (Convultional Neural Network) to label new image scans to determine the presence of metastasis cancer.

## Description 
Create an algorithm to identify metastatic cancer in small image patches taken from larger digital pathology scans. The data is a slightly modified version of the PatchCamelyon (PCam) benchmark dataset.
- Removed duplicates from dataset 
- PCam packs metastasis (cancer growth) detection into binary image classification tasks


## Dataset 
- Training Data Size - 22,025

- Test Data Size - 57,458

#### About the dataset
- Large number of small pathology images to classify. 
- Files are named with an image id. 
- The train_labels.csv file provides the ground truth for the images in the train folder. You are predicting the labels for the images in the test folder. 
    - A positive label indicates that the center 32x32px region of a patch contains at least one pixel of tumor tissue. 
- Tumor tissue in the outer region of the patch does not influence the label. This outer region is provided to enable fully-convolutional models that do not use zero-padding, to ensure consistent behavior when applied to a whole-slide image.
- No duplicates ( Original PCam Dataset had duplicates from sampling, but kaggle dataset doesn't contain duplicates)

# Model

**The model will have the following design:**
- Input Image 
- Convolutions
    - 3 x per each filter
        - Convolution -> Pooling -> Dropout 
- Flatten
- Dense Layer
- Dropout
- Output Classification 

# Conculsion 

Through this project I implemented a convolution nueral network to label if an input image of medical image scans. Through this project I used a 3 layer convolution neural network to process the train images, then make predicitons. My model had a 94% accuracy score and through kaggle and with the test data I achieved a public and private score of 0.8409 and 0.8495 respectively. I could further this score by hypertuning the epochs, batch sizes and filter/ model architecure redesign or refactoring.
Due to time constraints I couldn't further explore hypertuning to achieve a higher score for this competition 
