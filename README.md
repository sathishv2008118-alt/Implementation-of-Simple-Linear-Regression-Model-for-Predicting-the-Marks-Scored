# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the libraries and read the data frame using pandas.
2.Calculate the null values present in the dataset and apply label encoder.
3.Determine test and training data set and apply decison tree regression in dataset.
4.calculate Mean square error,data prediction and r2.


## Program:
```
/*
Program to implement the simple linear regression model for predicting the marks scored.
Developed by: Sathish v
RegisterNumber:  212225040391
import pandas as pd
import numpy as np 
import matplotlib.pyplot as plt
from sklearn.metrics import mean_absolute_error, mean_squared_error
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression

df.head() & Df.tail()

df = pd.read_csv('exp_2_dataset_student_scores.csv') 
print("First 5 rows:\n", df.head(), "\n")
print("Last 5 rows:\n", df.tail(), "\n")

X = df.iloc[:, :-1].values   # all rows, all columns except last -> shape (n_samples, 1)
Y = df.iloc[:, -1].values    # all rows, last column -> shape (n_samples,)
print("X (features):", X.flatten())
print("Y (targets):", Y)

# 3) Split data into training and testing sets
X_train, X_test, Y_train, Y_test = train_test_split(X, Y, test_size=1/3, random_state=0)
print("\nTraining samples:", len(X_train), " Testing samples:", len(X_test))

# 4) Create and train the model
regressor = LinearRegression()
regressor.fit(X_train, Y_train)   # fit on training data

# 5) Predict on the test set
Y_pred = regressor.predict(X_test)
print("\nPredicted values:", np.round(Y_pred, 2))
print("Actual values   :", Y_test)

# 6) Plot training results
plt.figure(figsize=(6,4))
plt.scatter(X_train, Y_train, color="orange", label="Training data")
plt.plot(X_train, regressor.predict(X_train), color="red", label="Fitted line")
plt.title("Hours vs Scores (Training set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.legend()
plt.grid(True)
plt.show()

# 7) Plot testing results (use X_test sorted for a nicer line)
order = np.argsort(X_test.flatten())
X_test_sorted = X_test.flatten()[order]
Y_test_sorted = Y_test[order]
Y_pred_sorted = Y_pred[order]
plt.figure(figsize=(6,4))
plt.scatter(X_test, Y_test, color="blue", label="Test data")
plt.plot(X_test_sorted, Y_pred_sorted, color="green", label="Predictions")
plt.title("Hours vs Scores (Testing set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.legend()
plt.grid(True)
plt.show()

# 8) Evaluation metrics
mae = mean_absolute_error(Y_test, Y_pred)
mse = mean_squared_error(Y_test, Y_pred)
rmse = np.sqrt(mse)
print("\nMean Absolute Error (MAE):", mae)
print("Mean Squared Error (MSE):", mse)
print("Root Mean Squared Error (RMSE):", rmse)

# 9) Example: predict for new students
new_hours = np.array([[2.5], [8.0]])   # shape must be (n_samples, 1)
pred_new = regressor.predict(new_hours)
print("\nPredictions for new hours", new_hours.flatten(), "=>", np.round(pred_new,2))
*/
```

## Output:
<img width="308" height="288" alt="684408527-496875ea-c95f-4ae2-ad11-0eef8f718780" src="https://github.com/user-attachments/assets/ab5f3d3b-746f-4016-83b2-b24caa5cfc90" />
<img width="752" height="83" alt="684408597-6396d139-8812-4be0-82e7-f0ebb4d959b9" src="https://github.com/user-attachments/assets/06e60e4e-8bd2-4fd4-aa65-27ff21d41cee" />

<img width="311" height="72" alt="684408755-3c3b4c99-f874-4335-893f-f17dd375c820" src="https://github.com/user-attachments/assets/b40c890e-9641-42cc-815b-8718456d25b4" />
<img width="665" height="62" alt="684408895-71b1a3f2-2e5f-4ccf-9d60-6b3b13691447" src="https://github.com/user-attachments/assets/6ecafed1-668e-4433-b42f-d1d965396b97" />
<img width="530" height="400" alt="684408977-debd3490-cb2f-49fe-847e-aeeaf39c7e8e" src="https://github.com/user-attachments/assets/2874eed4-4b71-42bc-abca-c68dae662702" />
<img width="536" height="397" alt="684409061-6e0d705b-107e-4a50-a9dc-37a026f9154d" src="https://github.com/user-attachments/assets/74080be7-29c7-4ef2-b000-ca52efc16fec" />
Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.



## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
