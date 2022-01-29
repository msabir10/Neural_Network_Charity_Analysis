# Neural_Network_Charity_Analysis
## Project Overview
The purpose of this project is to create a a binary classifier that is capable of predicting whether applicants will be successful if funded by a fictional company "Alphabet Soup." After the data is preprocessed, a Neurnal Network Model is compiled, trained and evaluated. Finally, there is an attempt made to optimize the model by increasing the accuracy to 75% or higher.

## Software and Resources
  Python 3.7
  pandas 1.2.4
  sklearn 0.24.1
  tensorflow 2.5.0
  Data: charity_data.csv

## Results
After reading in the charity_data.csv file to a Pandas DataFrame, the "EIN" and "NAME" columns were dropped from the dataset. These identification columns did not contain any valuable information.

Columns with more than 10 unique values, such as the "CLASSIFICATION" and "APPLICATION_TYPE" columns, have had their rare categorical variables binned into a new "other" column. A list of categorical variables is generated and is then encoded using OneHotEncoder. These encoded variable names are added to a new dataframe. After merging the one-hot encoded features, the originals are dropped.

The variable considered the target for this model is "IS_SUCCESSFUL," all other variables in the dataframe are considered features. The numerical variables are standardized using Scikit-Learn’s StandardScaler module.

The following variable(s) should be considered on features model
* ORGANIZATION
* STATUS
* INCOME_AMT
* SPECIAL_CONSIDERATIONS
* ASK_AMT
* APPLICATION_TYPE
* AFFILIATION
* CLASSIFICATION
* USE_CASE

The following variable(s) should be removed from input and data.
* NAME
* EIN

After preprocessing the data, a deep learning model is designed to to create a binary classification model that can predict if an "Alphabet Soup" funded organization will be successful based on the features in the dataset.

Rectified Linear Unit (ReLU) is used as the activation function for both the first and second hidden layers. For the output layer, a sigmoid activation function is used. While training the model, a callback saves the model's weights every 5 epochs. After training, the model's Loss and Accuracy values are evaluated. 

## Summary
None of the optimization attempts in this analysis were able to produce a model with a predictive accuracy level of 75% or higher. The following methods were attempted:

Adding an additional hidden layer.
Adding more neurons to a hidden layer.
Using different activation functions.
Decreasing the number of epochs in the training.
There could be numerous reasons why this model did not reach the targeted predictive accuracy level of 75%. The number of neurons in the hidden layers may need to be adjusted. The number of epochs during trainiing may need to be increased. The input data may have outliers or variables that are confusing the model.
Best results I was able to produce was: "Loss: 0.7277907850443448, Accuracy: 0.7271137237548828"
