# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Import required Libraries
2. Load the Dataset
3. Copy Data & Drop Unwanted Coloumns
4. Check Data Quality 
5. Encode Categorical Variables
6. Define Features(X) and Target(y)
7. Split into Training and Testing Sets
8. Build and Train Logistic Regression Model
9. Make Predictions
10. Evaluate the /model
11. Predict for a New Student

## Program:

# Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
# Developed by: JANANI K
# RegisterNumber:  212224230102

```
import pandas as pd
from sklearn.preprocessing import LabelEncoder
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score, classification_report
```
```

data = pd.read_csv("/content/Placement_Data (1).csv")

# View first 5 rows
print("First 5 rows of the dataset:")
print(data.head())
```
```
data1 = data.copy()

# Dropping 'sl_no' (serial number) and 'salary' (not needed for predicting placement)
data1 = data1.drop(["sl_no", "salary"], axis=1)

print("\nData after dropping 'sl_no' and 'salary':")
print(data1.head())
```
```
print("\nChecking for missing values (True = missing):")
print(data1.isnull().any())

print("\nNumber of duplicate rows:")
print(data1.duplicated().sum())
```
```
cat_cols = ["gender", "ssc_b", "hsc_b", "hsc_s", 
            "degree_t", "workex", "specialisation", "status"]

le = LabelEncoder()

for col in cat_cols:
    data1[col] = le.fit_transform(data1[col])

print("\nData after Label Encoding:")
print(data1.head())
```
```
X = data1.iloc[:, :-1]
# y = 'status' column
y = data1["status"]

print("\nFeatures (X) sample:")
print(X.head())

print("\nTarget (y) sample:")
print(y.head())
```
```
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=0
)

print("\nTraining and testing shapes:")
print("X_train:", X_train.shape)
print("X_test:", X_test.shape)
print("y_train:", y_train.shape)
print("y_test:", y_test.shape)
```
```
lr = LogisticRegression(solver="liblinear")

# Train the model
lr.fit(X_train, y_train)
```
```
y_pred = lr.predict(X_test)

print("\nPredicted values (y_pred):")
print(y_pred)
```
```
accuracy = accuracy_score(y_test, y_pred)
print("\nModel Accuracy:", accuracy)

# Classification Report: precision, recall, F1-score
print("\nClassification Report:")
print(classification_report(y_test, y_pred))
```
```
new_student = [[1, 80, 1, 90, 1, 1, 90, 1, 0, 85, 1, 85]]

new_prediction = lr.predict(new_student)

print("\nPrediction for new student (0 = Not Placed, 1 = Placed):")
print(new_prediction[0])
```

## Output:

# 2. Load the Dataset
<img width="657" height="262" alt="image" src="https://github.com/user-attachments/assets/e471f459-ec39-4401-a312-f80db173f5eb" />

# 3. Create a Copy and Drop Unwanted Columns

<img width="742" height="288" alt="image" src="https://github.com/user-attachments/assets/ecc6b3d0-3449-4d55-8562-c1db47c4bb3b" />

# 4. Check for Missing and Duplicate Values

<img width="532" height="343" alt="image" src="https://github.com/user-attachments/assets/ad1a7d6c-5633-46fd-892c-9092895434d6" />

# 5. Encode Categorical Variables using LabelEncoder

<img width="755" height="285" alt="image" src="https://github.com/user-attachments/assets/5bee62c5-1c40-4d67-a863-1f2f00913b8e" />

# 6. Define Features (X) and Target (y)

<img width="787" height="413" alt="image" src="https://github.com/user-attachments/assets/a432900b-573e-437a-a284-d0177294582a" />

# 7. Split the Dataset into Training and Testing Sets

<img width="393" height="123" alt="image" src="https://github.com/user-attachments/assets/fa22c2db-1f53-4c88-b0c0-78c116f3c462" />

# 8. Create and Train the Logistic Regression Model

<img width="413" height="80" alt="image" src="https://github.com/user-attachments/assets/1a57262a-d85a-4d05-a07d-67c4a51d0d2c" />

# 9. Make Predictions on the Test Set

<img width="653" height="87" alt="image" src="https://github.com/user-attachments/assets/80ba8b46-6d07-4bb9-ba5a-f2e5bfe65ca3" />

# 10. Evaluate Model Performance

<img width="606" height="247" alt="image" src="https://github.com/user-attachments/assets/f094acf5-25ba-457e-bf84-6c5898d2d719" />

# 11. Predict Placement for a New Student

<img width="772" height="97" alt="image" src="https://github.com/user-attachments/assets/5dc62b95-ed56-42b4-950c-a1c7ad2f312d" />


## Result:

Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
4voi
