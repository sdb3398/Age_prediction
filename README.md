# Age_prediction

## Description of the dataset

We used an image dataset composed by portrait photographs of people between 20 and 50 years old [Age Prediciton dataset](https://www.kaggle.com/datasets/mariafrenti/age-prediction).
For computational reasons we decided to reduce the class dimensions taking 300 images for each class in the training set and 100 images for each class in the test set. So, at the end, we have 9300 images in the training set and 3100 in the test set.

Every image has the following characteristics: 128x128 pixels and RGB format.

The goal of our project is to make age prediction using regression model based on convolutional neural network, so we created two different models.

## Models

### Weights

In both models we used the same type of weights: Xavier uniform for the convolutional layers, batch normalization layers and normal initialization in the fully connected part.

### Architectures

The architectures of the two models are similar. The first part is composed by convolutional layers with kernel size, stride and padding. In this part we used ReLu as activation function, batch normalization and max pooling. Then, there is a part in which we have fully connected layers where we add also dropout layers. We also added a spatial reduction using adaptive average pooling. In the last fully connected layer we used as output a single value because we want to make linear regression instead of classification. Moreover, we used the sigmoid function at the end. This allows us to represent the final result in a range between 0 and 1.

### Training process

We trained the model with 20 epochs and we used as loss function the MSE because it is used for regression problems. The mean squared error measures the average squared difference between actual values and predictions. For minimizing this loss function we used an optimization algorithm named SGD (stochastic gradient descent).
Furthermore, we applied learning rate of 0.0001 on the first model and 0.001 for the second one.

### Training loss

We made two graphs representing the two loss function and we noted that both decrease during the epochs but the values are still high. This suggested us that the results are very poor in making prediction.

### Errors 

We constructed the two graphs reguarding errors. We saw that the errors' variances are very high and the distributions of the two histograms are similar to the uniform. This is a big issue that we didn't solve.

### Final comments

We infered that these poor results depend on these things:

- we reduced the dimensions of the classes losing some informations
- some input images are in a very low quality (also in the transformations that we performed)
- maybe the problems requires a more sophisticated architecture and a higher computing capacity that we don't have
- Our approach involved adapting the architecture of the AlexNet model, known for its strength in classification tasks, to regression
- Both models consistently produced identical predictions for diverse input images, posing a significant challenge and suggesting potential issues in training or architectural design





