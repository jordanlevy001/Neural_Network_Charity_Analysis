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

- The model:
1. First hidden layer -- 80 neurons, activation function: tanh
2. Second hidden layer -- 30 neurons, activation function: tanh
3. Third hidden layer -- 16 neurons, activation function: tanh
4. Output layer -- activation function: sigmoid

![Model Parameters](https://user-images.githubusercontent.com/88804543/147017568-9e226f22-9e31-49e1-a860-61755e0e3d6f.png)


- The model prior to optimization achieved 73% accuracy, which is below the 75% accuracy threshold. The optimized model achieved 72% accuracy, which is also below the threshold. The random forest classifier achieved a 71% accuracy score. The random forest classifier was significantly more efficient, completing in 1 second or less.  


First Model Accuracy:

![First Model Accuracy](https://user-images.githubusercontent.com/88804543/147027289-d8ce4701-0466-44b9-a85e-df56abb32744.png)


Optimized Model Accuracy:

![Optimized Model Accuracy](https://user-images.githubusercontent.com/88804543/147027315-b206ee00-bd8e-4187-9720-dcf62106df54.png)


Random Forest Classifier Accuracy:

![RFC Accuracy](https://user-images.githubusercontent.com/88804543/147027343-8c46ce24-023f-4778-9da8-a0c3c0b119fb.png)



- Steps taken to increase model performance:
1. The 'STATUS' feature was removed
2. A third hidden layer was added
3. Increased the number of epochs from 30 to 60
4. The activation function of all hidden layers was changed from "relu" to "tanh"
5. Utilized a Random Forest Classifier instead of the neural network

## Summary
