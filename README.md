# Credit Card Fraud Detection using Machine Learning

A capstone project by Daniel Pérez Hernández., current Analyst at Deloitte and a Machine Learning enthusiast.

Most current update: April 03, 2023.

## Why doing a project of this nature?

Foe 6 months, Deloitte's AI Academy has provided me basic knowledge regarding the fascinanting world of data analysis and artifical intelligence. From basic Python functions, through SQL queries and Pandas data manipulation, to advanced mathematical models that employ any kind of data (structured, unestructured) to classify or predict behaviours previously unknown to us and that now are essential at any workplace where decision-making takes place.

This is a summary and application of all these knowledge and techniques with a clear purpose: extract and analyze data, generate information from it and build up  machine learning-powered models that can give solution to personal or business needs, leaning towards scalable automation.

## About the dataset

The collected dataset consists of a CVS type file with transactions made by credit cards in September 2013 by European cardholders.

Data was obtained data through a direct download form the Kaggle website, result of an extensive search of machine learning datasets. The web link to this dataset is: https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

Once downloaded, the data from the downloaded file `creditcard.csv` will be obtained via Python `pandas` library and use the `read_csv()` function.

## Business understanding

Purchases made through websites or in situ stores represent an imminent danger to credit/debit cardholders throughout the world, given their exposure to cybernetic dangers that may generate unrecognized fraud transactions. Thus, it is important to generate a trustworthy AI model that detects potential threats based on transaction datasets collected on a daily-basis routine.

This applies particularly to the finance industry, with an emphasis on the fraud monitoring techniques that are implemented on a bigger scale at banks worldwide.

The main focus of this project is to demonstrate how a bank can detect frauds based on your daily financial activities.

## Knowing our data

This dataset consists of numerical input variables only. Most features (V1 to V28) are the result of PCA transformation of the original features due to confidentiality issues; the rest (‘Time’, ‘Amount’ and 'Class') haven’t been modified at all.

There are non-null values in this dataset, which means no method to delete or fill N/A values with mean (for numerical variables) or mode (for ctageorical variables) are necessary at all. 29 features consist of float-type data and only the 'Class' category is an integer, given the 1 or 0 values that identify if a transaction is an authentic fraud or not.

But from all characteristics, the most important are:

1.   There is a confirmed unbalanced phenomenon present in our data, and the affected category is non other that "Fraud"
2.   By observing the correlation matrix, it becomes evident than most of the features (V1 to V28) have basically a null correlation between them. However, there is a modest linear correlation between V1 to V28 variables and Time, Ammount and Class, though most of the correlation values are positive (not exceeding the 0.40 treshold) and the rest negative (not exceeding the -0.60 treshold).

## Data preparation

Once we know what kind of data we are dealing with, we will divide our dataset in features and label (X and y, respectively).

It is important to keep in mind the first step to avoid data leakage: normalize the data using 



Before preparing our data for it to be input of a machine learning model, first we need to split it in training and test sets. This is used through the `train_test_split()` function obtained through `from sklearn.model_selection import train_test_split`.


standarize our data.

Once we have analyzed our data, it is necessary to split it into training, validation and test data sets. These later will be standarized and later resampled in order to use them to train, fit and compare our ML models.

Defining X and y: Target variable is the column called ‘Class’, where 1 represents fraud and 0 the opposite. We will predict if a transaction is fraud or not, so the output is a categorical variable.

## Treating imbalanced data

 SMOTE (Synthetic Minority Oversampling Technique) method: example using original data
In SMOTE new instances are synthesized from preexisting data using k-nearest neighbor to select a random nearest neighbor, and a synthetic instance is created randomly in feature space. It is basicaly an oversampling method, meaning there will be an increase the minority class' row quantity.

<img src="https://images.app.goo.gl/j2tT5wDG39TM7NkE6" width="400" height="400"/>
