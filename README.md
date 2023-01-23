{\rtf1\ansi\ansicpg1252\cocoartf2513
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fnil\fcharset0 HelveticaNeue;}
{\colortbl;\red255\green255\blue255;}
{\*\expandedcolortbl;;}
{\*\listtable{\list\listtemplateid1\listhybrid{\listlevel\levelnfc0\levelnfcn0\leveljc0\leveljcn0\levelfollow0\levelstartat1\levelspace360\levelindent0{\*\levelmarker \{decimal\}.}{\leveltext\leveltemplateid1\'02\'00.;}{\levelnumbers\'01;}\fi-360\li720\lin720 }{\listname ;}\listid1}}
{\*\listoverridetable{\listoverride\listid1\listoverridecount0\ls1}}
\margl1440\margr1440\vieww28600\viewh18000\viewkind0
\deftab560
\pard\pardeftab560\slleading20\partightenfactor0

\f0\fs24 \cf0 Business Understanding:\
We have given 426K data points for the price of used cars. Goal is to identify what features define the value of car. This will help dealer to predict price of used cars.\
\pard\pardeftab560\slleading20\pardirnatural\partightenfactor0
\cf0 \
\pard\pardeftab560\slleading20\partightenfactor0
\cf0 Data Understanding:\
There are a few questions I kept in mind while looking at the data. \
\pard\pardeftab560\pardirnatural\partightenfactor0
\ls1\ilvl0\cf0 {\listtext	0.	}Which columns/features had a correlation with price, so we can keep those columns, and the one which doesn\'92t we can drop those columns\
{\listtext	0.	}Then we need to see if there are columns that had lots of missing values, and if they did, should we drop those columns or fill in default values.\
{\listtext	0.	}Which of the columns are categorical, and which ones have multiple string values, this will help us in featuriztion during modeling\
\pard\pardeftab560\slleading20\partightenfactor0
\cf0 \
Data Cleanup\
Based on the above analysis, I cleaned up unwanted columns and missing values and converted string values into numeric ones.\
\pard\pardeftab560\slleading20\pardirnatural\partightenfactor0
\cf0 \
\pard\pardeftab560\slleading20\partightenfactor0
\cf0 Modeling:\
I could see that there was a high correlation between price and odometer, year, and manufacture,.\
I used multiple models to and featurization techniques to come up best model possible.\
\pard\pardeftab560\slleading20\pardirnatural\partightenfactor0
\cf0 \
\pard\pardeftab560\slleading20\partightenfactor0
\cf0 Conclusion:\
I can see that odometer,  year, manufacturer, and model has the highest value to the prices; It would be good to have more data. \
\
Business Understanding:\
\pard\pardeftab560\slleading20\partightenfactor0
\cf0 The goal is to increase the efficiency of directed campaigns for long-term deposit subscriptions by reducing the number of contacts.\
\
\pard\pardeftab560\slleading20\partightenfactor0
\cf0 Data Understanding:\
I first analyzed and cleaned the data, used LabelEncoder and OrdinalEncoder to encode some of the categorial columns, and for the rest, used OneHotEncoder.\
\
Data Cleanup:\
I dropped the default and duration columns; the reason for dropping the default was that the data it had was imbalanced, and duration because we will not have the duration for prediction ever.\
\
Modeling:\
After that, I split the data for training and testing. I created 4 models with default values for KNN, DTree, logistic regression, and SVM. I see that the highest test accuracy is with Logistic regression and SVM, KNN was also comparable, but training time for SVM was really high, and for KNN it was really low. Based on this I would go with logistic regression, but the data sample is really small, so we need to run these models with more data before concluding. Here is the result\
\
    model   train_accuracy  test_accuracy   train_time (sec)\
0   KNN 0.912421    0.889860    0.070544\
\
1   Dtree   0.995595    0.837258    0.236313\
\
2   LGR 0.900385    0.900138    0.328251\
\
3   SVM 0.903680    0.900057    51.258050\
\
Modeling with GridSearch:\
I then used GridSearch for hyperparameter tuning and did the training and testing again; below are the results. All models have comparable test accuracy, but training time had huge variance, SVM and KNN took a long time (I had to remove some of the parameters to make it finish on time). Logistic regression finished in only 9 sec.\
\
\
    model   train_accuracy  test_accuracy   train_time (sec)\
0   KNN 0.914224    0.891317    205.259049\
\
1   Dtree   0.900212    0.899166    43.205432\
\
2   LGR 0.900385    0.900057    8.990946\
\
3   SVM 0.903680    0.900057    826.374927\
\
Next Steps:\
We should collect more data and \
\
\
}