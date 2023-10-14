# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:

1.import pandas module and import the required data set.

2.Find the null values and count them.

3.Count number of left values.

4.From sklearn import LabelEncoder to convert string values to numerical values.

5.From sklearn.model_selection import train_test_split.

6.Assign the train dataset and test dataset.

7.From sklearn.tree import DecisionTreeClassifier.

8.Use criteria as entropy.

9.From sklearn import metrics.

10.Find the accuracy of our model and predict the require values.

## Program:
```ruby
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

Developed by: KULASEKARAPANDIAN K
RegisterNumber: 212222240052
```

```python
import pandas as pd
data = pd.read_csv("Employee.csv")
data.head()
data.info()

data.isnull().sum()

data["left"].value_counts

from sklearn.preprocessing import LabelEncoder
le= LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()

x= data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]

x.head()
y=data["left"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state = 100)


from sklearn.tree import DecisionTreeClassifier
dt = DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)

y_pred = dt.predict(x_test)
from sklearn import metrics

accuracy = metrics.accuracy_score(y_test,y_pred)
accuracy

dt.predict([[0.5,0.8,9,260,6,0,1,2]])
```

## Output:

### Data Head:
![OUTPUT](/datahead.png)

### Data Info:
![OUTPUT](/datainfo.png)

### Isnull() and Sum():
![OUTPUT](/isnull_sum.png)

### Data ValueCounts:
![OUTPUT](/valuecounts.png)

### Data Head for SALARY:
![OUTPUT](/salaryhead.png)

### X Data:
![OUTPUT](/xhead.png)

### Accuracy Value:
![OUTPUT](/accuracy.png)

### Predict Value [0.5,0.8,9,260,6,0,1,2]:
![OUTPUT](/predict.png)

## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
