# Analysis of Neural Network for Alphabet Soup Charity

## Table of Contents

- [Overview](#overview)
- [Preprocessing](#preprocessing)
- [Compiling, Training, and Evaluating the Model](#compiling,-training,-and-evaluating-the-model)
- [Results](#results)
- [Conclusion](#conclusion)

## Overview

At the request of the nonprofit lending group Alphabet Soup, a binary classifier neural network was built to predict the likelihood of success for funding ventures. The request was for a model that predicted success with at least 75% accuracy.

## Preprocessing

* What variable(s) are the target(s) for your model?

THe target variable is `IS_SUCCESSFUL`. The model is being trained to predict if a funding campaign will be successful.

* What variable(s) are the features for your model?

The following features were used in the optimized model:

    NAME—Identification column
    APPLICATION_TYPE—Alphabet Soup application type
    AFFILIATION—Affiliated sector of industry
    CLASSIFICATION—Government organization classification
    USE_CASE—Use case for funding
    ORGANIZATION—Organization type
    STATUS—Active status
    INCOME_AMT—Income classification
    SPECIAL_CONSIDERATIONS—Special considerations for application
    ASK_AMT—Funding amount requested

The following categorical variables were adjusted before being converted to numerical values using pd.getdummies(), each with a cutoff that lumped rare values into a single 'Other' category:

    NAME, cutoff at 6 values
    APPLICATION_TYPE, cutoff at 500 values
    CLASSIFICATION, cutoff also at 500 values

* What variable(s) should be removed from the input data because they are neither targets nor features?

EIN, employer identification number, was removed in the final model.

## Compiling, Training, and Evaluating the Model

* How many neurons, layers, and activation functions did you select for your neural network model, and why?

The optimized model used two hidden layers, the first with 80 nodes and the second with 30, both using relu as the activation function. 80 was chosen as the input layer contained about 40 features. As a binary classifier, the final output layer had only one node and used a sigmoid activation function. 

* Were you able to achieve the target model performance?

Yes, the final optimized model achieves an accuracy of about 79%.

* What steps did you take in your attempts to increase model performance?

The neural network went through many drafts. The 'Other' category cutoff for rare values was lowered and raised for APPLICATION_TYPE and CLASSIFICATION. Three hidden layers, one hidden layer. Switched from relu to tanh for activation functions. Tried binning ASK_AMT. Dropped AFFILIATION and STATUS. Things of that nature. In the end, adding NAME back in was the key to achieving model optimization above the target accuracy of 75%.

## Results

As you can see in the gallery below, model performance improved significantly between the original and optimized model, reducing loss by 10% and improving accuracy by 6%.

Optimized Model Results:

![Optimized Model Results](./images/optimized_results.png)

Original Model Results:

![Original Model Results](./images/original_results.png)

Optimized Model Loss:

![Optimized Model Loss](./images/optimized_loss.png)

Original Model Loss:

![Original Model Loss](./images/original_loss.png)

Optimized Model Accuracy:

![Optimized Model Accuracy](./images/optimized_accuracy.png)

Original Model Accuracy:

![Original Model Accuracy](./images/original_accuracy.png)

## Conclusion

The neural network achieves the goal set by Alphabet Soup, getting a model that predicts above 75% accuracy whether a project will succeed or fail. 

For further research, a useful exercise would be to try running the data through a random forest to see if it can do better. It can handle the numerical and categorical data, and is robust against outliers, overfitting, and non-linear data. It would also be less computationally intense and, importantly, provide better interpretability, which may be important when explaining why someone was denied a loan.