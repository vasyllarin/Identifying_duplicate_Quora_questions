# Identifying_duplicate_Quora_questions



## Results
| Model                |Parameters                     | Log loss (train)   | Log loss (test)   |  Training time
|----------------------|-------------------------------|--------------------|-------------------|----------------------|
| Logistic Regression  | {'solver': 'liblinear', <br> 'penalty': 'l2', <br>'C': np.float64(37.92690190732246)}                           | 0.5118             | 0.5173            | 1 min                | 
| XGBoost              | {'subsample': 0.7, <br> 'n_estimators': 200, <br> 'max_depth': 6, <br> 'learning_rate': 0.1, <br> 'colsample_bytree': 0.9}      | 0.5098             | 0.5159            | 1 min                |
| LSTM                 |                               |                    |                   |                      |
| BERT                 |                               |                    |                   |                      |

## Best model
- showed the best result among other models: AUROC 81% both for training and test datasets. The most significant features are: emp.var.rate and euribor3m.
