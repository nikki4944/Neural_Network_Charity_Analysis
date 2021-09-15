# Neural_Network_Charity_Analysis
Neural Networks and Deep Learning Models

## Overview of the Analysis

The client, a nonprofit, provided a dataset containing information from previous orgnizations that have received funding from them. The client requested a deep learning model be created to be used in the future to assist the foundation in making assessments on where they should invest. The model evaluates the features provided in the dataset in order to determine whethor or not the organizations funded by the client successfully achieved their stated goal in their grant applications.

## Results

#### Data Preprocessing
- The IS_SUCCESSFUL column of the provided dataset was considered the target for this model.
- The features of the model consisted of the following columns from the provided dataset:
  * APPLICATION_TYPE
  * AFFILIATION
  * CLASSIFICATION
  * USE_CASE
  * ORGANIZATION
  * STATUS
  * INCOME_AMT
  * SPECIAL_CONSIDERATIONS
  * ASK_AMT
- The EIN and NAME columns were removed from the dataset when compiliing, evaluating, and training the model.

#### Compiling, Training, and Evaluating the Model
- The original model consisted of two hidden layers and a total of 43 neurons.
 * The first hidden layer was composed of 28 neurons and used the ReLu activation function. The number of neurons was chosen to be two thirds of the total amount of neurons in the input layer.
 * The second hidden layer was composed of 14 neurons and also used the ReLu activation function. The number of neurons was chosen to be one third of the total amount of neurons in the input layer.
 * The output layer used one neuron and the Sigmoid activation function.
- The model resulted in a 72.67% accuracy rate which is slightly less than the target of 75%.
- Three attempts were made to optimize the model to achieve target accuracy of 75%, none of these were successful.
 * In the first attempt, I added a third hidden layer, changed the number of neurons in each layer, and set the number of epochs at 250.  <img width="356" alt="Screen Shot 2021-09-15 at 4 24 22 PM" src="https://user-images.githubusercontent.com/82982901/133504335-5a7a6ef7-538e-4305-a7dc-53e3dac8c814.png"> The accuracy rate lowered to 72.52%.
 * In the second attempt, I kept the third hidden layer, epochs remained at 250, and adjusted the number of neurons in each layer again. <img width="343" alt="Screen Shot 2021-09-15 at 4 29 23 PM" src="https://user-images.githubusercontent.com/82982901/133505852-7979f47e-bb85-42bc-b75d-06b1cdef4c4b.png"> The accuracy rate raised slightly to 72.59%.
 * In the third attempt, I removed the hidden layer, changed the first hidden layer activation function to Leaky ReLu, returned the number of neurons in each hidden layer to 28 and 14 respectively, and changed the number of epochs to 200. The accuracy rate lowered slightly to 72.56%.

## Summary

While this model fell short of meeting the 75% target accuracy, it could still be used to help the client evaluate future organizations proposals to determine if they should be funded. 
It is possible this model is suffering from overfitting, a common issue with deep learning models. In order to avoid this issue, the features should be reevaluted to see if all are necessary to be included in the model. For instance, removing the USE_CASE, STATUS, and INCOME_AMT features may increase model accuracy.
