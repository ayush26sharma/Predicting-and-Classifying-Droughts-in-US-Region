# Predicting and Classifying Droughts in US Region

This repository contains a project aimed at predicting and classifying droughts in the US region. The project utilizes machine learning techniques to analyze historical weather data and build models for drought prediction. The code and resources provided here can be used to understand the process of predicting and classifying droughts and can serve as a starting point for similar projects or research.

## Table of Contents
- [Introduction](https://github.com/ayush26sharma/Predicting-and-Classifying-Droughts-in-US-Region/edit/main/README.md#introduction)
- [Literature](https://github.com/ayush26sharma/Predicting-and-Classifying-Droughts-in-US-Region/edit/main/README.md#literature)
- [Data](https://github.com/ayush26sharma/Predicting-and-Classifying-Droughts-in-US-Region/edit/main/README.md#data)
- [Methodology]()
- [Results]()
- [References]()

## Introduction
Droughts are a recurring natural phenomenon that can significantly impact agriculture, water resources, and ecosystems. Predicting and classifying droughts can help governments, farmers, and other stakeholders proactively mitigate the potential consequences.

This project focuses on utilizing machine learning techniques to predict and classify droughts in the US region. It employs historical weather data and features such as temperature, precipitation, humidity, wind speed, and more to train models that can forecast drought conditions.

## Literature

- ### [Applying machine learning for drought prediction using data from a large ensemble of climate simulations](https://nhess.copernicus.org/articles/21/3679/2021/)

This paper uses meteorological data to predict droughts with a lead time of 1 month using ANN’s. They use the
meteorological data from the ClimEx Project (Leduc et al,2019) which consists of data for North America and
Europe. They are solving a binary classification problem using Standardized Precipitation Index (SPI) as
their output class. The paper goes into greater detail regarding where the data came from with specific
sources for some of the features that they have used.

They explain the reasoning behind how an ANN works and the metrics that they have used to evaluate their
models. They ran their model in two different climate regions of Lisbon and Munich The authors have used
L2 regularization in their ANN and investigated the effect of different loss functions and architectures, the
results of which have been summarized below 

- ### [Forecasting standardized precipitation index using data intelligence models](https://www.nature.com/articles/s41598-021-82977-9)

While the previous paper focused on ANN as the
classification model, this paper instead focuses on models
such as Random Forests, minimum probability machine
regression (MPMR), M5 Tree (M5tree), extreme learning
machine (ELM) and online sequential-ELM (OSELM). They
too use the SPI as the drought indicator like the previous
paper. 

The paper goes into detail of how all these models
work as well as the metrics that they have used to evaluate
these models. the metrics they have used are for every base
station as the metric and according to them. The SPI was
calculated for 1,3,6 and 12 months and the results were
reported for each case. According to the authors RF was the
best for SP1, and ELM was the best for SP3, SP6 and SP12.

## Data
The data used for this project is not included in this repository due to its large size. However, instructions are provided on how to obtain the necessary data. The data consists of historical weather records from various weather stations across the US region. The dataset contains information such as temperature, precipitation, humidity, wind speed, and other relevant features.

## Methodology
• As this is a multi-class classification problem, we
applied Logistic Regression and Random Forests at
the beginning

• To fit the target classification categories with actual
decimal values, data had to be rounded down or
floored.

• Feature selection must be done carefully for better
results. As a starting point, 44 features were taken
out of 53 for training.

• After unsatisfactory results, feature selection was
done using domain knowledge and correlation
heatmap. 25 features were selected.


### Models Used:
- #### Logistic regression with OVR classification:
  Since Logistic Regression is one of the simplest
classification models, we began our analysis
with this model Tuned hyper parameters like max_iters,
loss_penalty and class_weights
- #### Random Forest Classification:
  Ensembled several decision trees to build a
classification model.
 Hyper Parameters tuned: n_bins, max_depth,
n_estimators, max_samples
 Tuning n_bins can improve the performance on
dataset.
- #### Naïve Bayes Classifier:
   Gaussian Naïve Bayes Classifier was used since
that was the only model that fits our dataset.
   Since all our features are continuous in nature
there are no categorical features.
- #### SVM Classifier:
   We used the linear kernel to train our model
since a SVM model using the rbf or polynomial
kernel does not scale well to larger datasets.
   There is a tradeoff here between training times
and accuracy because large dataset is unlikely
to be linearly separable.
 The hyper parameter that was mainly tuned was
tolerance.
- #### MLP Classifier:
  We tried out various Multilayer perceptron classifier architectures and activation functions. Finally the hidden layer sizes that were used are
(10,5), (10,5,3) and (6,4,2) for the best results.

- #### K Neighbor Classification:
  K-Neighbor Classifier is sklearn
implementation of k-nearest neighbors.
  We tried this algorithm for various values
of k from 3 to 40.
  As we increased the value of k, our model
accuracy increased as shown in the plot
given below:

     ![image](https://github.com/ayush26sharma/Predicting-and-Classifying-Droughts-in-US-Region/assets/58669560/bd720450-daf5-44f4-ab8b-f7f4c826dae3)


## Results
We present the results of all the models with their best parameters found after hyperparameter tuning on the test dataset.
![image](https://github.com/ayush26sharma/Predicting-and-Classifying-Droughts-in-US-Region/assets/58669560/4dd8c720-9f93-4d98-8999-9406bce6a49f)
Based on the results we had gotten previously, we hypothesized that soil and meteorological data that is mu than our test dataset would not be a good indicator for drought prediction because of the various climatic changes that have occurred over two decades. The results that we have shown here confirmed our hypothesis, where we noticed that increasing the dataset to include older dates caused the accuracy scores to fall.

SVM was the worst-performing model for our problem, and Random Forest was the best-performing model on the train set and one of the best on the test set. In the end, we found that the Random Forest classifier and MLP are the best-performing models, which was also shown to be the case in the literature.

## References

- Yaseen, Z.M., Ali, M., Sharafati, A. et al. Forecasting standardized precipitation index using data intelligence models: regional investigation of Bangladesh. Sci Rep 11, 3435 (2021). https://doi.org/10.1038/s41598-021-82977-9
- Felsche, Elizaveta & Ludwig, Ralf. (2021). Applying machine learning for drought prediction in a perfect model framework using data from a large ensemble of climate simulations. Natural Hazards and Earth System Sciences. 21. 3679-3691. 10.5194/nhess-21-3679-2021. 
