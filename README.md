# Neural Network Analysis of Successful Funding

## Project Overview

The goal of this project was to create a binary classifier capable of predicting whether applicants will be successful if funded by AlphabetSoup. All of the organizations included in the charity_data.csv provided by AlphabetSoup have received funding from AlphabetSoup at some point in time. Our goal is to be able to predict with at least 75% accuracy if the organization will be successful if they are funded by AlphabetSoup.

As mentioned above, AlphabetSoup provided the charity_data.csv which we processed/cleaned for the model. We used one hot encoder and other methods to clean the data. We also removed unneccessary features as well as binning features with too many unique values. We then used tensorflow to build the model, as well as a random forest classifier.

## Results

#### Data Preprocessing

- The target variable was the 'IS_SUCCESSFUL' column
- The variables that are considered features are:
1. APPLICATION_TYPE -- AlphabetSoup application type
2. AFFILIATION -- affiliated sector of industry
3. CLASSIFICATION -- government organization classification
4. USE_CASE -- use case for funding
5. ORGANIZATION -- organization type
6. INCOME_AMT -- income classification
7. SPECIAL_CONSIDERATIONS -- special consideration for application
8. ASK_AMT -- funding amount requested

- The variables that are neither targets nor features, and therefore do not pertain to this model are:
1. EIN -- this is an identification column
2. NAME -- this is an identification column
3. STATUS -- this indicates if the organization is active or not

#### Compiling, Training, Evaluating the Model

- The optimized model:
1. Input layer -- 84 neurons, activation function: tanh
2. First hidden layer -- 42 neurons, activation function: tanh
3. Second hidden layer -- 21 neurons, activation function: tanh
4. Output layer -- activation function: tanh

- The number of neurons was selected based on rule of thumb, for basic neural networks designate two to three times the amount of neurons in the hidden layer as the number of inputs.

![Model Parameters](https://user-images.githubusercontent.com/88804543/147158671-8d4c0db7-f44d-40e0-8566-6c7997f0bbd6.png)

- The model prior to optimization achieved 73% accuracy, which is below the 75% accuracy threshold. The optimized model also achieved 73% accuracy, which again is below the threshold. The random forest classifier achieved a 71% accuracy score. The random forest classifier was significantly more efficient, completing in 1 second or less. The neural network model took multiple minutes to run. Thus the random forest classifier was faster and achieved roughly the same accuracy.


First Model Accuracy:

![First Model Accuracy](https://user-images.githubusercontent.com/88804543/147027289-d8ce4701-0466-44b9-a85e-df56abb32744.png)


Optimized Model Accuracy:

![Optimized Model Accuracy](https://user-images.githubusercontent.com/88804543/147158619-d793e670-00eb-4b50-95db-527d5065afda.png)


Random Forest Classifier Accuracy:

![RFC Accuracy](https://user-images.githubusercontent.com/88804543/147027343-8c46ce24-023f-4778-9da8-a0c3c0b119fb.png)

Random Forest Classifier Parameters:

![RFC Parameters](https://user-images.githubusercontent.com/88804543/147159008-58887aa6-a336-4c3e-a6df-98cd76605ada.png)


- Steps taken to increase model performance:
1. The 'STATUS' feature was removed
2. An additional hidden layer was added
3. Increased the number of epochs from 30 to 60
4. The activation function of all hidden layers was changed from "relu" to "tanh"
5. The output layer activation function was changed from "relu" to "tanh"
6. Utilized a Random Forest Classifier instead of the neural network

## Summary

The deep learning model was unable to meet the threshold accuracy of 75%. The first iteration of the model achieved 73% accuracy which is close to the threshold but below it. 













