# Identifying_duplicate_Quora_questions
The dataset used in this project contains pairs of questions, and the goal of the project is to determine whether each pair of questions is a duplicate or consists of different questions

## Business Problem & Objective
In many platforms such as Q&A websites or customer support portals, duplicate questions can create inefficiencies and redundant content. The objective of this project is to detect duplicate question pairs to improve content management and enhance user experience.

## Data
[Link to the dataset](https://drive.google.com/drive/folders/1vESit2UApBX7aC_sQ9V5JLQKkDmF8b_K)  
The dataset consists of 17.6 MB of training data and 4.4 MB of test data (compressed as .zip files).  
The train dataset has 323,432 records; The test dataset has 80,858 records.  

## Evaluation Metric
The model is evaluated using Log Loss, which measures the accuracy of predicted probabilities for duplicate classification.  

## Approach & Tools
Preprocessing: Tokenization, padding, handling missing values.  
Models: Logistic Regression, XGBoost, Neural Networks (LTSM).  
Tools & Libraries: Python (Google Colaboratory), pandas, scikit-learn, TensorFlow/Keras, matplotlib, seaborn.  



## Results
| Model                |Parameters                     | Log loss (train)   | Log loss (test)   |  Training time
|----------------------|-------------------------------|--------------------|-------------------|----------------------|
| Logistic Regression  | {'solver': 'liblinear', <br> 'penalty': 'l2', <br>'C': np.float64(37.92690190732246)}                           | 0.5118             | 0.5173            | 1 min                | 
| XGBoost              | {'subsample': 0.7, <br> 'n_estimators': 200, <br> 'max_depth': 6, <br> 'learning_rate': 0.1, <br> 'colsample_bytree': 0.9}      | 0.5098             | 0.5159            | 1 min                |
| LSTM                 |                               |                    |                   |                      |

## Best model
- showed the best result among other models: AUROC 81% both for training and test datasets. The most significant features are: emp.var.rate and euribor3m.
