# [Global-Wheat-Detection](https://www.kaggle.com/competitions/global-wheat-detection/)

**Problem Statement**

To detect wheat heads from outdoor images of wheat plants, including wheat datasets from around the globe. Using worldwide data, we will focus on a generalized solution to estimate the number and size of wheat heads. To better gauge the performance for unseen genotypes, environments, and observational conditions, the training dataset covers multiple regions. We will use more than 3,000 images from Europe (France, UK, Switzerland) and North America (Canada). 

**Method**

We will use YOLO (You Only Look Once) algorithm to solve this problem, though we can't use this model in kaggle competition. Still, its good to learn and check.

**Steps to Setup YOLO**

YOLO needs dataset to be formated in a perticular format: The directory structure should look something like below image.

`Directory Structure`

![image](https://user-images.githubusercontent.com/43055935/173280016-975392ba-7e2e-41ac-94a9-5bfc539ba1cb.png)



**Architecture**

<img width="700" alt="yolo" src="https://user-images3.githubusercontent.com/43055935/174430508-b6f573ab-1f69-421e-854d-914b2f2a5cdd.png">

* This architecture takes an image as input and resizes it to 448*448 by keeping the aspect ratio same and performing padding.
* This image is then passed in the CNN network. This model has 24 convolution layers, 4 max-pooling layers followed by 2 fully connected layers. For the reduction of the number of layers (Channels), we use 1*1 convolution that is followed by 3*3 convolution. Notice that the last layer of YOLO predicts a cuboidal output. This is done by generating (1, 1470) from final fully connected layer and reshaping it to size (7, 7, 30). 
* This architecture uses Leaky ReLU as its activation function in whole architecture except the last layer where it uses linear activation function. Batch normalization also helps to regularize the model. Dropout technique is also used to prevent overfitting.


**Results**

![image](https://user-images.githubusercontent.com/43055935/174430753-581a6621-570a-4984-a444-3b27155866de.png)

![d3ed0578-b1c3-4ecc-ace1-2151b379dea2](https://user-images.githubusercontent.com/43055935/173284100-08557a4d-897d-47de-8a7f-313c5c93513c.jpg)
