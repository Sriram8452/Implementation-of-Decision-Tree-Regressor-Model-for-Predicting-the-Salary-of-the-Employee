# Ex.No.7-Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

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

5.Apply decision tree regression on to the dataframe and get the values of Mean square error, r2 and data prediction.



## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: Sriram G
RegisterNumber:  212222230149
*/
```

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

![image](https://github.com/Sriram8452/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118708032/12da37ac-b07c-474e-8e4f-3d714d3da200)

![image](https://github.com/Sriram8452/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118708032/45f60aae-85bb-4eea-911f-e9695a18bf56)

![image](https://github.com/Sriram8452/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118708032/38c7e50a-dffe-4df0-b37f-188e57176bc8)

![image](https://github.com/Sriram8452/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118708032/33454022-4b21-404e-9904-4c94e1c387aa)

![image](https://github.com/Sriram8452/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118708032/9ac732d4-0710-4fa6-958d-9a4f681a7982)

![image](https://github.com/Sriram8452/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118708032/bc4486c3-05c0-4f5b-bf1a-fa3c1459a994)

## Result:

Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
