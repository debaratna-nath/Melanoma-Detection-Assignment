# Detecting Skin Cancer (Melanoma) using Deep Learning

## Problem Statement
 Melanoma is one of the most invasive skin cancer with the highest risk of death. It goes quickly and has the ability to spread to any organ, however, if diagnosed early ,it is highly curable. Prevention and early treatment are critical, especially if you have fair skin, blonde or red hair and blue eyes.
 The problem statement is to build a multi-class classification Deep Learning model which can evaluate images and alert dermatologists about the presence of melanoma.

## Dataset
The dataset consists of 2357 images of malignant and benign oncological diseases, which were formed from the International Skin Imaging Collaboration (ISIC). All images were sorted according to the classification taken with ISIC, and all subsets were divided into the same number of images.

The data set contains the following diseases:

![datasetdf](https://github.com/debaratna-nath/Melanoma-Detection-Assignment/blob/main/readme%20images/Sample%20Images.png)

The distribution of the samples in each of the 9 classes in the dataset is as follows:

![datasetplot](https://github.com/debaratna-nath/Melanoma-Detection-Assignment/blob/main/readme%20images/Samples%20Distribution.png)

There is an evidence of class imbalance in the dataset, which has been dealt with in the iteration 3 of the modelling notebook.


## CNN Architecture Design
The NN Architecture designed in this project is as follows [final architecture with the best accuracy metric]

- Rescalling Layer - To rescale an input in the [0, 255] range to be in the [0, 1] range.
- (Convolutional Layer + MaxPooling Layer) x 4 [With 32, 64, 128, 128 channels respectively]
- Dropout Layer - At the end of last two convolutional layer blocks
- Flatten Layer - Flattening is converting the data into a 1-dimensional array for inputting it to the next layer. We flatten the output of the convolutional layers to create a single long feature vector. And it is connected to the final classification model, which is called a fully-connected layer.
- (Dense Layer + ReLU Activation) x 2 [256 and 128 neurons in each]
- Output Layer with 9 neurons for the 9 classes, and softmax activation layer


### Model Performance
![ModelEvaluation](https://github.com/debaratna-nath/Melanoma-Detection-Assignment/blob/main/readme%20images/Model%20Performance.png)

