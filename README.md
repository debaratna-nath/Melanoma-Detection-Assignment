# Detecting Skin Cancer (Melanoma) using Deep Learning

## Problem Statement
 Melanoma is one of the most invasive skin cancer with the highest risk of death. It goes quickly and has the ability to spread to any organ, however, if diagnosed early ,it is highly curable. Prevention and early treatment are critical, especially if you have fair skin, blonde or red hair and blue eyes.
 The problem statement is to build a multi-class classification Deep Learning model which can evaluate images and alert dermatologists about the presence of melanoma.

## Dataset
The dataset consists of 2357 images of malignant and benign oncological diseases, which were formed from the International Skin Imaging Collaboration (ISIC). All images were sorted according to the classification taken with ISIC, and all subsets were divided into the same number of images.

The data set contains the following diseases:

![datasetdf](https://github.com/kshitij-raj/Melanoma-Skin-Cancer-Detection/blob/f143d178495ec6490ce2ee18c4cbbfb2e1388cea/Readme_images/Datasetdf.png)

![datasetplot](https://github.com/kshitij-raj/Melanoma-Skin-Cancer-Detection/blob/f143d178495ec6490ce2ee18c4cbbfb2e1388cea/Readme_images/DatasetPlot.png)

To overcome the issue of class imbalance, used a python package  Augmentor (https://augmentor.readthedocs.io/en/master/) to add more samples across all classes so that none of the classes have very few samples.

### Sample image from Dataset

![sample image](https://github.com/kshitij-raj/Melanoma-Skin-Cancer-Detection/blob/b43daf05e84626d3796321e79caeb2f6f8179346/Readme_images/Samleimagefromdataset.png)

## CNN Architecture Design
To classify skin cancer using skin lesions images. To achieve higher accuracy and results on the classification task, I have built custom CNN model.

- Rescalling Layer - To rescale an input in the [0, 255] range to be in the [0, 1] range.
- Convolutional Layer - Convolutional layers apply a convolution operation to the input, passing the result to the next layer. A convolution converts all the pixels in its receptive field into a single value. For example, if you would apply a convolution to an image, you will be decreasing the image size as well as bringing all the information in the field together into a single pixel. 
- Pooling Layer - Pooling layers are used to reduce the dimensions of the feature maps. Thus, it reduces the number of parameters to learn and the amount of computation performed in the network. The pooling layer summarises the features present in a region of the feature map generated by a convolution layer.
- Dropout Layer - The Dropout layer randomly sets input units to 0 with a frequency of rate at each step during training time, which helps prevent overfitting.
- Flatten Layer - Flattening is converting the data into a 1-dimensional array for inputting it to the next layer. We flatten the output of the convolutional layers to create a single long feature vector. And it is connected to the final classification model, which is called a fully-connected layer.
- Dense Layer - The dense layer is a neural network layer that is connected deeply, which means each neuron in the dense layer receives input from all neurons of its previous layer.
- Activation Function(ReLU) - The rectified linear activation function or ReLU for short is a piecewise linear function that will output the input directly if it is positive, otherwise, it will output zero.The rectified linear activation function overcomes the vanishing gradient problem, allowing models to learn faster and perform better.
- Activation Function(Softmax) - The softmax function is used as the activation function in the output layer of neural network models that predict a multinomial probability distribution. The main advantage of using Softmax is the output probabilities range. The range will 0 to 1, and the sum of all the probabilities will be equal to one.

### Model Architecture
![Model Arch](https://github.com/kshitij-raj/Melanoma-Skin-Cancer-Detection/blob/d8b2ca8cc296af14ab9aa7a6def31a7efc86271b/Readme_images/ModelLayer.png)

### Model Evaluation
![ModelEvaluation](https://github.com/kshitij-raj/Melanoma-Skin-Cancer-Detection/blob/7e7a17d3c891bf12be42385979168135775654c4/Readme_images/ModelEvaluation.png)

## References
Melanoma Skin Cancer from https://www.cancer.org/cancer/melanoma-skin-cancer/about/what-is-melanoma.html

Introduction to CNN from https://www.analyticsvidhya.com/blog/2021/05/convolutional-neural-networks-cnn/

Image classification using CNN from https://www.analyticsvidhya.com/blog/2020/02/learn-image-classification-cnn-convolutional-neural-networks-3-datasets/

Efficient way to build CNN architecture from https://towardsdatascience.com/a-guide-to-an-efficient-way-to-build-neural-network-architectures-part-ii-hyper-parameter-42efca01e5d7