# EX.7: Implementation of Decision Tree Regressor Model for Predicting the Salary of the Employee


## REQUIREMENTS:
Anaconda – Python 3.7 Installation / Jupyter notebook

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Algorithm:
1. Import the required libraries .
2. Read the data frame using pandas.
3. Get the information regarding the null values present in the dataframe.
4. Apply label encoder to the non-numerical column inoreder to convert into numerical values.
5. Determine training and test data set.
6. Apply decision tree regression on to the dataframe.
7. Get the values of Mean square error, r2 and data prediction.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: HARITHASHREE.V
RegisterNumber:  212222230046
*/
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
![Decision Tree Regressor Model for Predicting the Salary of the Employee](sam.png)

### HEAD OF THE CSV FILE:
![Screenshot 2024-04-01 085529](https://github.com/haritha-venkat/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/121285701/82862edf-83e7-4223-be69-4b499c2d72d3)

### INFORMATION OF THE CSV FILE:
![Screenshot 2024-04-01 085708](https://github.com/haritha-venkat/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/121285701/18646a8e-d992-44ab-aed3-5dd8d06594df)

### ISNULL AND SUM FUNCTION OF THE CSV FILE:
![Screenshot 2024-04-01 085822](https://github.com/haritha-venkat/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/121285701/7f4d3767-47a5-419d-9cd9-bac253989491)

### HEAD FOR THE POSITION:
![Screenshot 2024-04-01 085854](https://github.com/haritha-venkat/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/121285701/7ed9166a-9a53-45c7-8db6-42d16ef6b445)

### MSE VALUE:
![Screenshot 2024-04-01 085948](https://github.com/haritha-venkat/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/121285701/6041c8ec-ab2c-4940-9f78-7c7460fe90c6)

### R2 VALUE:
![Screenshot 2024-04-01 090051](https://github.com/haritha-venkat/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/121285701/dee9ae38-53df-446b-ae9c-0d16f86a81b1)

### PREDICTION VALUE:
![Screenshot 2024-04-01 090059](https://github.com/haritha-venkat/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/121285701/2d7a942c-084c-4dcb-bf04-676d264f9cb9)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
