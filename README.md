# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:

1.Import the required packages.
2.Read the data set.
3.Apply label encoder to the non-numerical column inoreder to convert into numerical values.
4.Determine training and test data set.
5.Apply decision tree regression on to the dataframe and get the values of Mean square error, r2
and data prediction.

## Program:

Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

Developed by: Sriram G

RegisterNumber:  212222230149

```
import pandas as pd
data=pd.read_csv("Salary.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
x=data[["Position","Level"]]
y=data[["Salary"]]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)
from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics
mse=metrics.mean_squared_error(y_test,y_pred)
print(mse)
r2=metrics.r2_score(y_test,y_pred)
print(r2)
dt.predict([[5,6]])
```


## Output:

![image](https://github.com/Sriram8452/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118708032/3f0d0d5b-4a41-459c-a7ba-3f3ee303daa9)

![image](https://github.com/Sriram8452/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118708032/534e5306-5730-4712-a13f-13ef96edb40c)

![image](https://github.com/Sriram8452/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118708032/449fb041-f4ca-4663-b4e5-c771d0322a17)

![image](https://github.com/Sriram8452/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118708032/7cc2e087-b37b-42ec-a406-0124662058f7)

![image](https://github.com/Sriram8452/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118708032/c88bae2b-24ab-41f7-aa83-66da84f83ee4)

![image](https://github.com/Sriram8452/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118708032/05a1526d-6bdc-4a4d-851f-2eac574cfc1c)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
