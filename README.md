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
| Logistic Regression  | {'solver': 'liblinear', <br> 'penalty': 'l2', <br>'C': np.float64(37.92690190732246)}                           | 0.5118             | 0.5173            | 1m                | 
| XGBoost              | {'subsample': 0.7, <br> 'n_estimators': 200, <br> 'max_depth': 6, <br> 'learning_rate': 0.1, <br> 'colsample_bytree': 0.9}      | 0.5098             | 0.5159            | 1m                |
| LSTM                 | {'embedding_dim': 50, <br> 'lstm_units': 32, <br> 'dropout_rate': 0.4, <br> 'learning_rate': 0.001}                              | 0.4383             | 0.4869            | 2h 36m               |

## Conclusions
The LSTM model achieved the best performance, with the lowest test log loss (0.4869).

The results show that deep learning models such as LSTM can learn contextual information and detect similarities between questions that traditional models (Logistic Regression or XGBoost) may miss.  

The model can be used to identify duplicate questions in Q&A platforms or customer support systems. This can help reduce redundant content and improve the user experience by merging similar queries.  

The LSTM model requires a large amount of training data and computational resources. It may also struggle with rare or domain-specific words that were not well represented in the training set. Additionally, the model’s interpretability is lower compared to simpler algorithms like Logistic Regression. These limitations should be considered when applying the model.    

Future work could focus on using pre-trained transformer models (e.g., BERT) to further improve performance by leveraging contextual embeddings.
