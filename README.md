# Digit Recognition using Keras and TensorFlow
## Introduction
The steps for the assignment are commented in the python file.

I'm going to use Keras with TensorFlow to sort MNIST handwritten dataset. 

### MNIST Dataset
This dataset was constructed from a number of scanned document datasets availabe from the National Institute of Standards and Technology (NIST). These images were normalized in size and centered. Each image is in a 28x28 square (784 pixels). 60,000 images were used to train a model and 10,000 were used to test it. Excellent results achieve a prediction error of 1%. State-of-the-art results are approximately 0.2% which could be achieved with a large convolutional neural network.

## Starting model
We'll start with a simplest model possible to expose any parts that can be improved
To do a multilayer perceptron model, we flatten our 28 by 28 pixel images into a single 784 length vector for each image.
Normalize the values from 0-255 to 0-1 to make things easier on our neural network.
Finally, we change the categories 1-9 into a binary matrix.
Our current neural network structure is as follows:

**Visible Layer (784 Inputs) >> Hidden Layer (784 Neurons) >> Output Layer (10 Outputs)**

## Simple Convolutional Neural Network for MNIST
As expected, we achieved a 1-2% error which is pretty good. We can do better by using all aspects of a modern CNN implementation, like convolutional layers, pooling layers, and dropout layers.
The changes to our model are as follows:
A convolutional layer was added with 32 feature maps, with a size of 5 x 5. Also acts as our input layer which expects images to be added.
Dropout 20% of neurons to reduce the amount of overfitting.
Flatten the data using Theanos backend
Finally use 10 neurons for the 10 prediction classes with a softmax (Adam) activation function to output probability-like prediction for each class.
The current neural network structure is as follows:

**Visible Layer (1x28x28 Inputs) >> Convolutional Layer (32 maps, 5x5) >> Max Pooling Layer (2x2) >> Dropout Layer (20%) >> Flatten Layer >> Hidden Layer (128 Neurons) >> Output Layer (10 Outputs)**

## Simple CNN Result:
Train on 60000 samples, validate on 10000 samples

Epoch 1/10

13m - loss: 0.2981 - acc: 0.9015 - val_loss: 0.1522 - val_acc: 0.9571

Epoch 2/10

13m - loss: 0.1215 - acc: 0.9478 - val_loss: 0.0921 - val_acc: 0.9705

Epoch 3/10

13m - loss: 0.0820 - acc: 0.9694 - val_loss: 0.0781 - val_acc: 0.9770

Epoch 4/10

12m - loss: 0.0606 - acc: 0.9856 - val_loss: 0.0754 - val_acc: 0.9768

Epoch 5/10

13m - loss: 0.0375 - acc: 0.9892 - val_loss: 0.0663 - val_acc: 0.9792

Epoch 6/10

13m - loss: 0.0270 - acc: 0.9926 - val_loss: 0.0612 - val_acc: 0.9810

Epoch 7/10

13m - loss: 0.0211 - acc: 0.9948 - val_loss: 0.0619 - val_acc: 0.9811

Epoch 8/10

13m - loss: 0.0142 - acc: 0.9968 - val_loss: 0.0625 - val_acc: 0.9802

Epoch 9/10

13m - loss: 0.0110 - acc: 0.9977 - val_loss: 0.0549 - val_acc: 0.9812

Epoch 10/10

11m - loss: 0.0082 - acc: 0.9984 - val_loss: 0.0573 - val_acc: 0.9824

Baseline Error: 1.76%

