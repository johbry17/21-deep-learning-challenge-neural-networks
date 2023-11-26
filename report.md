# Analysis of Neural Network for Alphabet Soup Charity

## Table of Contents

- [Abstract](#abstract)
- [Overview](#overview)
- [Preprocessing](#preprocessing)
- [Compiling, Training, and Evaluating the Model](#compiling,-training,-and-evaluating-the-model)
- [Results](#results)

## Abstract

At the request of the nonprofit lending group Alphabet Soup, a binary classifier neural network was built to predict the likelihood of success for funding ventures. The request was for a model that predicted success with at least 75% accuracy.

# Overview

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
    CLASSIFICATIOIN, cutoff also at 500 values

* What variable(s) should be removed from the input data because they are neither targets nor features?

EIN, employer identification number, was removed in the final model.

## Compiling, Training, and Evaluating the Model

* How many neurons, layers, and activation functions did you select for your neural network model, and why?

The optimized model used two hidden layers, the first with 80 nodes and the second with 30, both using relu as the activation function. 80 was chosen as the input layer contained about 40 featuers. As a binary classifier, the final output layer had onldy one node and used a sigmoid activation function. 

* Were you able to achieve the target model performance?

Yes, the final optimized model acheives an accuracy of about 79%.

* What steps did you take in your attempts to increase model performance?



## Results

