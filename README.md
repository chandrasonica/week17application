**Business Understanding:**
The goal is to increase the efficiency of directed campaigns for long-term deposit subscriptions by reducing the number of contacts.

**Data Understanding:**
I first analyzed and cleaned the data, used LabelEncoder and OrdinalEncoder to encode some of the categorial columns, and for the rest, used OneHotEncoder.

**Data Cleanup:**
I dropped the default and duration columns; the reason for dropping the default was that the data it had was imbalanced, and duration because we will not have the duration for prediction ever.

**Modeling:**
After that, I split the data for training and testing. I created 4 models with default values for KNN, DTree, logistic regression, and SVM. I see that the highest test accuracy is with Logistic regression and SVM, KNN was also comparable, but training time for SVM was really high, and for KNN it was really low. Based on this I would go with logistic regression, but the data sample is really small, so we need to run these models with more data before concluding. Here is the result

    model   train_accuracy  test_accuracy   train_time (sec)
0   KNN 0.912421    0.889860    0.070544

1   Dtree   0.995595    0.837258    0.236313

2   LGR 0.900385    0.900138    0.328251

3   SVM 0.903680    0.900057    51.258050

**Modeling with GridSearch:**
I then used GridSearch for hyperparameter tuning and did the training and testing again; below are the results. All models have comparable test accuracy, but training time had huge variance, SVM and KNN took a long time (I had to remove some of the parameters to make it finish on time). Logistic regression finished in only 9 sec.


    model   train_accuracy  test_accuracy   train_time (sec)
0   KNN 0.914224    0.891317    205.259049

1   Dtree   0.900212    0.899166    43.205432

2   LGR 0.900385    0.900057    8.990946

3   SVM 0.903680    0.900057    826.374927

**Next Steps:**
Our model is showing 90% test accuracy, which is really good, as the next step, we should run a few experimental campaigns and compare the results against the model performance, also we can use campaign results to test and re-train our model. I also feel that there could be more time spent cleaning the data to make sure we are using correct and relevant data.

**Here is the link to the notebook:**
https://github.com/chandrasonica/week17application/blob/main/prompt_III.ipynb
