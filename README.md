# Neural_Network_Charity_Analysis

## Overview

The purpose of this project was to use deep learning to analyze a CSV of organizations that have received funding from Alphabet Soup and train a model to be able to predict with at least 75% accuracy if applicants will be successful if their projects are funded by Alphabet Soup.

## Results

### Data Preprocessing

- The variable considered to be the target for our model is "IS_SUCCESSFUL."

- The variables considered to be the features for our model are "EIN", "NAME", "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION", "USE_CASE", "ORGANIZATION", "STATUS", "INCOME_AMT", "SPECIAL_CONSIDERATIONS" and "ASK_AMT."

- The variables that should be removed from the input data are, at minimum, "EIN", "NAME", "CLASSIFICATION", "USE_CASE", "ORGANIZATION" and "STATUS."

### Compiling, Training and Evaluating the Model

The initial program had us drop the "EIN" and "NAME" columns from the dataset, assume 2 hidden layers with the first having 80 neurons and the second having 30 neurons, use RELU for the activation function in both hidden layers and use Sigmoid for the output layer's activation function.  This produced an accuracy of 72.6%.  Three attempts were made to improve accuracy.

#### Attempt 1

Attempt 1 had the following changes in an attempt to improve accuracy:

- Decreased the number of features by removing "USE_CASE, "ORGANIZATION" and "STATUS" in addition to "EIN" and "NAME" features.

![Attempt 1 Features]()

- Doubled the number of neurons for each hidden layer.

![Attempt 1 Neurons]()

The result was a slight decrease in accuracy at 72.2%.

![Attempt 1 Accuracy]()

#### Attempt 2

Attempt 2 had the following changes in an attempt to improve accuracy:

- Again decreased the number of features by removing "AFFILIATION" and "CLASSIFICATION" in addition to the features listed in Attempt 1.

![Attempt 2 Features]()

- Added a third hidden layer with 10 neurons.

![Attempt 2 Hidden Layers]()

The result was a significant decrease in accuracy at 58.5% and increase in loss at 66.1%.

![Attempt 2 Accuracy]()

#### Attempt 3

Attempt 3 had the following changes in an attempt to improve accuracy:

- Added "AFFILIATION" back in as a feature due to its apparent significance.

![Attempt 3 Features]()

- Doubled the neurons for the first two hidden layers and quadrupled the neurons in the third hidden layer.

![Attempt 3 Hidden Layers]()

- Changed the activation function for the first hidden layer to TANH.

![Attempt 3 Activation Functions]()

- Increased the number of epochs from 100 to 150.

![Attempt 3 Epochs]()

The result was an increase back to 72.2%, similar to Attempt 1 but with a little more loss.

![Attempt 3 Accuracy]()

None of the above attempts resulted in a minimum 75% accuracy for our model.

## Summary

Overall, we were not able to achieve the target model performance with the above changes.  Perhaps using a simpler machine learning model would yield better results.  PCA (principal component analysis) is one recommendation to apply here due to most of the features in our dataset appearing to be insignificant.  Another recommendation would be using the Random Forest model due to its ability to predict classification based on the consensus of weak learners, of which there appear to be plenty here.