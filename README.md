# SGD-Classifier
## AIM:
To write a program to predict the type of species of the Iris flower using the SGD Classifier.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Initialize Parameters: Set initial weights (theta) to zero.
2.Compute Predictions: Calculate predictions using the sigmoid function on the weighted inputs.
3.Calculate Cost: Compute the cost using the cross-entropy loss function.
4.Update Weights: Adjust weights by subtracting the gradient of the cost with respect to each weight.
5.Repeat: Repeat steps 2–4 for a set number of iterations or until convergence is achieved.

## Program:

Program to implement the prediction of iris species using SGD Classifier.
Developed by: LAKSHANYA.N
RegisterNumber:  212224230136

```
from sklearn.datasets import load_iris
from sklearn.linear_model import SGDClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score, confusion_matrix
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd
iris = load_iris()
df = pd.DataFrame(data=iris.data, columns=iris.feature_names)
df['target'] = iris.target
print(df.head())
```
```
x = df.drop('target', axis=1)
y = df['target']
```
```
x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.2, random_state=42)
```
```
sgd_clf = SGDClassifier(max_iter=1000, tol=1e-3)
sgd_clf.fit(x_train, y_train)
```
```
y_pred = sgd_clf.predict(x_test)
accuracy = accuracy_score(y_test, y_pred)
print(f"Accuracy: {accuracy:.3f}")
```
```
cf = confusion_matrix(y_test, y_pred)
print("Confusion Matrix:")
print(cf)
```

## Output:

![image](https://github.com/user-attachments/assets/3067080e-4ad9-4a64-97f7-1535de10792f)


## Result:
Thus, the program to implement the prediction of the Iris species using SGD Classifier is written and verified using Python programming.
