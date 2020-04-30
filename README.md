# Credit-Card-Fraud-Detection

The dataset contains transactions made using credit cards by European cardholders in September 2013, and is available on Kaggle. It is a highly imbalanced dataset with fraudulent transactions accounting for 0.172% of all transactions.

I have explored a few techniques to address the imbalance in the data !!! 

## Undersampling

Random sampling of nonfraud records are done and 492 records are selected to get a number which is same as number of fraud records. Both these sets are then concatenated to generate a new train set. In case of undersampling we could suffer from information loss.

On original test set when we use Random Forest+ Undersampling, the recall = 0.89 , but precision is very low. 

Hence we try to oversample.

## Oversampling

In this case more records are added from the fraud cases. But this addition could also lead to overfitting. I have used SMOTE technique (Synthetic Minority Oversampling technique) for oversampling.

With SMOTE we get the following resullts:
 |Algorithm|Precision|Recall
 |---------|---------|------
 |Random Forest|0.22|0.87
 |SVC|0.39|0.82
 |XGBoost|0.87|0.85

Clearly SMOTE+XGBoost outperformed all other approaches giving a precision of 0.87 and recall of 0.85.
