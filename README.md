# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the packages.

2.Analyse the data.

3.Use modelselection and Countvectorizer to preditct the values.

4.Find the accuracy and display the result.

## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: Priyangha G
RegisterNumber:212223040157 
*/

import pandas as pd
data=pd.read_csv("spam.csv", encoding='Windows-1252')
data

data.shape

x=data['v2'].values
y=data['v1'].values
x.shape

y.shape

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2, random_state=0)
x_train

x_train.shape

from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()
x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)
from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred

from sklearn.metrics import accuracy_score,confusion_matrix,classification_report
acc=accuracy_score(y_test,y_pred)
acc

con=confusion_matrix(y_test,y_pred)
print(con)

cl=classification_report(y_test,y_pred)
print(cl)
```

## Output:
<img width="1048" height="657" alt="image" src="https://github.com/user-attachments/assets/cde95cf0-82a3-4153-ad98-2e5ceb908f92" />
<img width="962" height="83" alt="image" src="https://github.com/user-attachments/assets/2b69cfde-96a8-4ee9-9630-6bb9a79db740" />
<img width="877" height="77" alt="447100524-d1b52a4e-add4-4533-b2ec-914450655b75" src="https://github.com/user-attachments/assets/62814771-b808-4201-94f8-f58a39fc64e7" />
<img width="873" height="265" alt="447099831-7411653b-9ca9-4ebf-9ba6-ec3f126c97bd" src="https://github.com/user-attachments/assets/1b8398d5-aae6-4a19-a332-3d8899e0985f" />


## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
