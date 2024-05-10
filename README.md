
# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import the required libraries.

2.Read the data frame using pandas.

3.Get the information regarding the null values present in the dataframe.

4.Apply label encoder to the non-numerical column inoreder to convert into numerical values.

5.Determine training and test data set.

6.Apply decision tree regression on to the dataframe.

7.Get the values of Mean square error, r2 and data prediction.


## Program:

Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

Developed by: HARITHASHREE.V

RegisterNumber:  212222230046


```python
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
y=data["Salary"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn import metrics
mse=metrics.mean_squared_error(y_test,y_pred)
mse

r2=metrics.r2_score(y_test,y_pred)
r2

dt.predict([[5,6]])
```

## Output:

1. Head of the csv file:

   <img width="134" alt="image" src="https://github.com/TejaswiniGugananthan/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/121222763/78f655e9-6ef3-4aa3-948e-7e1ed19e2e98">

2. info of the csv file:

   <img width="179" alt="image" src="https://github.com/TejaswiniGugananthan/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/121222763/59e86cce-fe2c-495a-b502-3f1492918439">

3. isnull & sum function:

   <img width="71" alt="image" src="https://github.com/TejaswiniGugananthan/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/121222763/a1557ef2-b7c8-4e5d-95bb-ff8d097c6a0a">


4. Head for position:

   <img width="112" alt="image" src="https://github.com/TejaswiniGugananthan/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/121222763/c006d130-664c-4950-83f0-d66d10971014">

5. MSE value:

    <img width="76" alt="image" src="https://github.com/TejaswiniGugananthan/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/121222763/2308d594-4e95-4e40-a16b-b72f7546e7a4">

6. r2 value:

    <img width="104" alt="image" src="https://github.com/TejaswiniGugananthan/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/121222763/6a10eb4e-2d4c-43b0-944a-a2d6e789c004">

7. Prediction value:

    <img width="566" alt="image" src="https://github.com/TejaswiniGugananthan/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/121222763/e0ad232c-08fa-4e86-aab1-fced4ff71526">



## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
