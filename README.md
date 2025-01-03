# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Start
2.Data preparation
3.Hypothesis Definition
4.Cost Function
5.Parameter Update Rule
6.Iterative Training
7.Model evaluation
8.End 


## Program:
```
/*
Program to implement the linear regression using gradient descent.
Developed by:Mohana K.V.S.L
RegisterNumber: 24900659
*/import numpy as np
import pandas as pd
from sklearn.preprocessing import StandardScaler
def linear_regression(X1,y,learning_rate=0.01,num_iters=1000):
 X=np.c_[np.ones(len(X1)),X1]
 theta=np.zeros(X.shape[1]).reshape(-1,1)
 for _ in range(num_iters):
 predictions=(X).dot(theta).reshape(-1,1)
 errors=(predictions-y).reshape(-1,1)
 theta=learning_rate*(1/len(X1))*X.T.dot(errors)
 return theta
data=pd.read_csv('50_Startups.csv',header=None)
X=(data.iloc[1:, :-2].values)
X1=X.astype(float)
scaler=StandardScaler()
y=(data.iloc[1:,-1].values).reshape(-1,1)
X1_Scaled=scaler.fit_transform(X1)
Y1_Scaled=scaler.fit_transform(y)
print(data.head())
theta=linear_regression(X1_Scaled, Y1_Scaled)
new_data=np.array([165349.2,136897.8,471784.1]).reshape(-1,1)
new_Scaled=scaler.fit_transform(new_data)
prediction=np.dot(np.append(1, new_Scaled),theta)
prediction=prediction.reshape(-1,1)
pre=scaler.inverse_transform(prediction)
print(f"Predicted value: {pre}")

```

## Output:
![Screenshot (19)](https://github.com/user-attachments/assets/b9046d92-4e85-4810-9608-8c59e348ad3d)



## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.
