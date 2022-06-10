# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Import the required libraries.
2.Upload the csv file and read the dataset.
3.Check for any null values using the isnull() function.
4.From sklearn.tree inport DecisionTreeRegressor.
5.Import metrics and calculate the Mean squared error.
6.Apply metrics to the dataset, and predict the output. 

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: G.PAVITHRA
RegisterNumber: 212221240036 
*/
```
```
import pandas as pd
data = pd.read_csv("Salary.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
data["Position"] = le.fit_transform(data["Position"])
data.head()
x = data[["Position","Level"]]
y = data["Salary"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state=2)
from sklearn.tree import DecisionTreeRegressor
dt = DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred = dt.predict(x_test)
from sklearn import metrics
mse = metrics.mean_squared_error(y_test,y_pred)
mse
r2 = metrics.r2_score(y_test,y_pred)
r2
dt.predict([[5,6]])
```
## Output:
### DATA HEAD:
![image](https://user-images.githubusercontent.com/93427264/172994585-91362cf7-bcec-4ff1-9f58-1c4488853ef2.png)
### DATA INFO:
![image](https://user-images.githubusercontent.com/93427264/172994629-7af7a1b0-9186-4f08-b7f1-c91149724ac4.png)
### Data Head after applying LabelEncoder():
![image](https://user-images.githubusercontent.com/93427264/172994703-cb2993e8-392c-49c6-9033-120169ed7b3c.png)
### MSE:
![image](https://user-images.githubusercontent.com/93427264/172994777-037a7d68-e53c-4a51-943a-bb304e0a09b1.png)
### R2:
![image](https://user-images.githubusercontent.com/93427264/172994808-0a054405-b5c8-4890-83fe-664c3a57ea52.png)
### DATA PREDICTION:
![image](https://user-images.githubusercontent.com/93427264/172994834-d0bf7d43-6ed6-42a7-a092-81b29040ff03.png)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
