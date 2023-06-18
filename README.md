# Predicting and Classifying Droughts in US Region

This repository contains a project aimed at predicting and classifying droughts in the US region. The project utilizes machine learning techniques to analyze historical weather data and build models for drought prediction. The code and resources provided here can be used to understand the process of predicting and classifying droughts and can serve as a starting point for similar projects or research.

## Table of Contents
- Introduction
- Data
- Results
- Contributing
- License

## Introduction
Droughts are a recurring natural phenomenon that can significantly impact agriculture, water resources, and ecosystems. Predicting and classifying droughts can help governments, farmers, and other stakeholders proactively mitigate the potential consequences.

This project focuses on utilizing machine learning techniques to predict and classify droughts in the US region. It employs historical weather data and features such as temperature, precipitation, humidity, wind speed, and more to train models that can forecast drought conditions.

## Data
The data used for this project is not included in this repository due to its large size. However, instructions are provided on how to obtain the necessary data. The data consists of historical weather records from various weather stations across the US region. The dataset contains information such as temperature, precipitation, humidity, wind speed, and other relevant features.

## Results
We present the results of all the models with their best parameters found after hyperparameter tuning on the test dataset.
![image](https://github.com/ayush26sharma/Predicting-and-Classifying-Droughts-in-US-Region/assets/58669560/4dd8c720-9f93-4d98-8999-9406bce6a49f)
Based on the results we had gotten previously, we hypothesized that soil and meteorological data that is mu than our test dataset would not be a good indicator for drought prediction because of the various climatic changes that have occurred over two decades. The results that we have shown here confirmed our hypothesis, where we noticed that increasing the dataset to include older dates caused the accuracy scores to fall.

SVM was the worst-performing model for our problem, and Random Forest was the best-performing model on the train set and one of the best on the test set. In the end, we found that the Random Forest classifier and MLP are the best-performing models, which was also shown to be the case in the literature.


## License
This project is licensed under the MIT License. You can find more details in the LICENSE file.
