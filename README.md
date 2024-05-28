# Disease diagnosis service
## Service description
This service is an implementation of an automated medical diagnosis method based on symptoms. The user interface is presented as a Telegram bot.
## Technology stack
Python 3.10.12. Libraries: Pandas, NumPy, sklearn, Tenserflow, pyTelegramBotAPI.
## Datasets description
### data_symptoms_diagnosis:
Number of classes: 41
Number of features: 132
Number of samples: 4920
Saples consist of symptoms (features) with binary values (0/1) and a target value. 
### data_symptoms38_diagnosis:
Number of classes: 41
Number of features: 38
Number of samples: 4920
Same as data_symptoms_diagnosis but with a reduced number of features. Feature selection methods were applied with accordance classification accuracy.
### data_prec:
Consist of two columns: diagnosis and corresponding precautions.
## Models description
### Multilayer Perceptron (nn_model).
The first layer consists of 38 neurons (the number of input data features) with a ReLU (Rectified Linear Unit) activation function and L2 kernel regularization. This is followed by two more layers with 64 and 128 neurons respectively, both with ReLU activation functions and L2 kernel regularization. After the second layer, there is a Dropout layer with a dropout rate of 0.2, which is used to prevent overfitting. The final layer has a number of neurons equal to the number of classes (41) with a softmax activation function. The model is compiled with the categorical_crossentropy loss function, the Adam optimizer, and the accuracy metric. The training parameters used for the model are 500 epochs and a batch size of 32.
### Gaussian Naive Bayes (nb_model).
The parameter var_smoothing = 1e-2 was used for variance smoothing.
### Random Forest (rf_model).
The parameters used were: random_state = 18 for reproducibility of results and n_estimators = 100 to determine the number of trees in the ensemble.
