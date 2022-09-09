[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/12VGVmRB2NKTHLIvLkeh5oPtP5adyAc5a?usp=sharing)

### Problem Statement : It is a binary classification problem 

### Approach 

#### After EDA , came to conclusion that 

1. the dataset is imbalanced Dataset 
2. The dataset looks like Power law (approx)
3. There are no negative points and null values 

#### Built Weighted KNN with cosine distance , Unifom KNN with Cosine Distance , Weighted KNN with minkowski distance, Weighted KNN with cosine distance , Logistic Regression , Random Forest ,XGboost (Decision Tree base learners) , XGboost (linear models as base learners) for all transformations given below :

1. Standard scaled data
2. Minmax scaled data
3. Robust scaled data
4. Log transformed and min max sclaed data
5. Log transformed and Robust scaled data
6. Square transformed and Robust scaled
7. Square root transformed and robust scaled
8. BoxCox transformed and robust scaled
9. Beta to normal transformation 

then checked AUC , Accuracy, Precision, Recall, F1 Score, Logloss, Percentage of misclassification of both test and train data of all the above models and all the above transformations , then came to conclusion that, 

1. Distance based models like KNN, Logistic Regression are performing well after transforming data using log

then made foreword feature selection using Logistic Regression and checked for any colinear features using Pertubation test ,after Pertubation test came to conclustion that there are no colinear features on top 15 features given by the foreword feature selection using Logistic Regression. Took threshold of 15 features because there is no much improvement of performance when i add more features to the dataset .

then made foreword feature selection using XGboost and came to conclusion that the features given by foreword feature selection using XGboost were better than foreword feature selection using Logistic regression , After 15 features , performance of the model didn't increase significantly , so choosed top 15 features and then trained a XGboost model with calibration using top 15 features 

