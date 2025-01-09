# Multi Layer Perceptron (MLP) for Binary Classification
## Overview
This is a university project and part of the 2024 exam of a course regarding
Deep Learning at the University of Pavia. The project consists of constructing
an MLP that is able to classify two distinct classes of a dataset.

Moreover, the project has the requirement of finding some ways of analysing the
final model in order to retrieve and understand how the decision process works,
at least in the first few layers of the model.

## Dataset
The dataset is composed of 13 features and 1 target variable. The features 
can be numerical, categorical or binary. The target variable is binary.

## Model
After preprocessing the dataset, different models are trained and evaulated. The
best model is selected and analysed. It is a MLP with 3 hidden layers, with
respectively 12, 34 and 34 neurons, ReLU activation functions, and a final ouput
layer with a sigmoid activation function and a single neuron. See the file
[`DL-exam/Project_DL.ipynb`](DL-exam/Project_DL.ipynb) for a more detailed description of the model, the training
process and the selection of the best model.

## Results
The model is able to classify the two classes with an accuracy of 0.8125. The
confusion matrix is shown below:

![Confusion Matrix](https://github.com/user-attachments/assets/ff422d9d-65ea-4df6-abfa-30d8f8d7153e)

## Analysis
The analysis of the model is performed by visualizing the weights of the model
and then recursively checking which features are the most important for the
determination of the output. A more detailed description of the analysis can be
seen again in file [`DL-exam/Project_DL.ipynb`](DL-exam/Project_DL.ipynb). Here
I will just report the final chart showing what part of the decision is taken by
each of the 13 features of the dataset (the chart shows on the left 27 features
since in preprocessing the number of features was increased by the one-hot
encoding of the categorical features). 

![Decision Chart](https://github.com/user-attachments/assets/e7cd42fd-2ac7-4b1e-abc0-abe79ea5a247)

As we can see there isn't any feature that is particularly dominant. There are
though some who have slightly more or less influence. For instance, Feature 1
(count the right part of the bar) has an appearent influence on the decision:
indeed it seems as though when the outcome of the model is 1 it's more likely
that the value is either 1 or 2, while when the outcome is 0 it's more likely
that the value is either 0 or 3

