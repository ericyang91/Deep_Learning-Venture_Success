# Deep Learning: Venture Success
 ![venture](https://github.com/ericyang91/Deep_Learning-Venture_Success/blob/main/Images/venture.jpg)

## Purpose:

  The purpose of this project is to create a binary classification model using a neural network to predicted if an organization will be successful after receiving funding. The model will then be evaluated for its accuracy with target accuracy level at 75%. If the model does not meet the target level, it will go through a series of optimization for better performance. If successful, the model can be used by organizations to select for funding promising venture applicants with the best chance of success.
  
  A quick snapshot of the data:
  ![raw](https://github.com/ericyang91/Deep_Learning-Venture_Success/blob/main/Images/raw.jpg)
  
## Results:
### Data Preprocessing
- The model uses the feature 'IS_SUCCESSFUL' as its target variable(y).
- The featuers 'EIN' and 'NAME' are dropped because they have no visible influence on the outcome of the ventures' success.
- Rest of the columns in the DataFrame are used as features(X).

  ![raw](https://github.com/ericyang91/Deep_Learning-Venture_Success/blob/main/Images/features.jpg)

### Compiling, Training, and Evaluating the Model
- 40, 80, 40, 1 neurons were used for the input layer, hidden layer 1, hidden layer 2, and the output layer respectively. The number of neurons for the hidden layers were selected based on the number of input neurons. The rule of thumb is to place X2 or X3 number of input neurons in the first hidden layer, and a lesser amount in the second hidden layer.
- Two hidden layers were placed because having a single hidden layer does not allow the model to learn complex patterns. Models that use a single hidden layer are generally for linearly separable functions. On the other hand, placing three hidden layers could lead to overfitting.
- 
![raw](https://github.com/ericyang91/Deep_Learning-Venture_Success/blob/main/Images/neuronlayer.jpg)
- The model failed to reach the target accuracy level. Accuracy = 0.724, Loss = 0.596

### Optimization Attepts
#### Attempt 1
- Dropped NaN values for a cleaner data
- Increased the number of bins in the 'APPLICATION_TYPE' column to produce a more complex learning.
- Increased the number of bins in the 'CLASSIFICATION' column to produce a more complex learning.
- Resulting Accuracy = 0.725, Loss = 0.574
#### Attempt 2
- Further increased the number of bins in the 'APPLICATION_TYPE' column.
- Increased the number of neurons in the hidden layers to stimulate complex learning.
- Increased the number of epochs to help the model adjust its weights and biases to minimize the error between the predicted outputs and the actual outputs on the training data.
- Resulting Accuracy = 0.723, Loss = 0.708
#### Attempt 3
- More neurons were added to the hidden layers to counter the increased loss of data.
- Changed the activation function in the hidden layers from 'ReLu' to 'Tanh' in order to optimize the training process by encouraging fast convergence.
- Added a third hidden layer to stimulate complex learning.
- Further increased the number of epochs.
- Resulting Accuracy = 0.723, Loss = 0.574

## Summary:
All three optimization attempts did not lead to a significant change in the model's accuracy. Based on the kind of attempts made, this could indicate that the model is complex enough to prevent loss of information and learn the relationships amongst the features. The underlying issue could be in the data set itself. After running and plotting the box plot to pin out any outliers in the 'APPLICATION_TYPE' column, we have found a large number of outliers that could impact the machine learning process. The way these data sets were collected should be reviewed again for any potential problems. It could also be possible to improve the performance by dropping the outliers first, but that could also lead to a loss of information. It could also be helpful to bin the values in the 'ASK_AMT' as well because it has more than 10 unique values. Adjusting the ratio of train data to the test data could also be beneficial.

## Languages and Libraries:

[![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)
[![Python](https://img.shields.io/badge/python-%3E%3D%203.6-blue.svg)](https://www.python.org/downloads/)
[![Pandas](https://img.shields.io/badge/pandas-v1.0.5-blue)](https://pandas.pydata.org/)
[![Scikit-Learn](https://img.shields.io/badge/scikit--learn-0.24.2-blue)](https://scikit-learn.org/stable/)
[![TensorFlow](https://img.shields.io/badge/tensorflow-%3E%3D%202.0-orange)](https://www.tensorflow.org/)



