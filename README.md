# Online Shoppers Purchasing Intention

## Context

This project uses a dataset from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Online+Shoppers+Purchasing+Intention+Dataset), which contains information about different users, such as the time spent in each web page and if that lead to a purchase or not.

## Objective

The objective of this project is to use classification models in order to predict wether the user will make a purchase or not.

## Process

Before training the classification models, this dataset had to go through data preprocessing first, such as **removing columns with correlation, normalizing the numerical columns and encoding the categorical variables**.

After data preprocessing is done, **feature selection** was applied to select the most important variables to be used for the classification models. **10 variables were chosen out of 51**.

The rest of the variables, instead of being dropped and not being used in the training set and test set, were used to create clusters. Those clusters would be later used alongside the 10 variables that were selected previously.

### Training and testing the data

Because the dataset is imbalanced, oversampling and undersampling was applied using SMOTE and the RandomUnderSampler.

Cross-validation was also used in order to avoid overfitting. And because the dataset is imbalanced, **RepeatedStratifiedKFold** was used.

The classification models that were trained were the following:

* Logistic Regression
* Gaussian NB
* SVC
* KNN
* Decision Tree
* Random Forest
* XGBoost
* AdaBoost
* CatBoost

The models that had the best performance were the **Random Forest and the AdaBoost models**. So these were chosen for the next stage which was **Hyperparameter tuning**.

This stage was useful to see if we could improve the performance of the models by adjusting their parameters.

Since the Random Forest had a lot of parameters, **RandomizedSearchCV** was used to be more efficient. The hyperparameter tuning definitely helped improve the precision score of both models. However, the baseline model still performed better because the hypertuned models were overfitted after all these stages.

For more information, please check the [python file](https://github.com/tmcdonald92/Online-Shoppers-Purchasing-Intention/blob/main/dataset.ipynb)
