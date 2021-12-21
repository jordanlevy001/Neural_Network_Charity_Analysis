# Neural Network Charity Analysis

## Project Overview
The goal of this project was to create a binary classifier capable of predicting whether applicants will be successful if funded by AlphabetSoup. All of the organizations included in the charity_data.csv provided by AlphabetSoup have received funding from AlphabetSoup at some point in time. Our goal is to be able to predict with at least 75% accuracy if the organization will be successful if they are funded by AlphabetSoup.

As mentioned above, AlphabetSoup provided the charity_data.csv which we processed/cleaned for the model. We used one hot encoder and other methods to clean the data. We also removed unneccessary features as well as binning features with too many unique values. We then used tensorflow to build the model.

## Results
- The target variable is the 'IS_SUCCESSFUL' column
- The variables that are considered features are:



- The variables that are neither targets nor features, and therefore do not pertain to this model are:
1. EIN -- this is an identification column
2. NAME -- this is an identification column
3. STATUS -- this indicates if the organization is active or not



## Summary
