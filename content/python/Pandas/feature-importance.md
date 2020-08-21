---
title: "Feature Importance"
author: "TACT"
date: 2020-08-21
description: "-"
type: technical_note
draft: false
---

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.ensemble import RandomForestClassifier
from sklearn.preprocessing import LabelEncoder
```


```python
df = pd.read_csv("D:/Datasets/Loan/train_original.csv")
df.drop("Loan_ID", axis=1, inplace=True)
df.dropna(how="any", inplace=True)
df.sample(5)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Gender</th>
      <th>Married</th>
      <th>Dependents</th>
      <th>Education</th>
      <th>Self_Employed</th>
      <th>ApplicantIncome</th>
      <th>CoapplicantIncome</th>
      <th>LoanAmount</th>
      <th>Loan_Amount_Term</th>
      <th>Credit_History</th>
      <th>Property_Area</th>
      <th>Loan_Status</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>153</td>
      <td>Male</td>
      <td>Yes</td>
      <td>2</td>
      <td>Not Graduate</td>
      <td>No</td>
      <td>2281</td>
      <td>0.0</td>
      <td>113.0</td>
      <td>360.0</td>
      <td>1.0</td>
      <td>Rural</td>
      <td>N</td>
    </tr>
    <tr>
      <td>180</td>
      <td>Male</td>
      <td>Yes</td>
      <td>1</td>
      <td>Graduate</td>
      <td>No</td>
      <td>6400</td>
      <td>7250.0</td>
      <td>180.0</td>
      <td>360.0</td>
      <td>0.0</td>
      <td>Urban</td>
      <td>N</td>
    </tr>
    <tr>
      <td>361</td>
      <td>Male</td>
      <td>Yes</td>
      <td>2</td>
      <td>Graduate</td>
      <td>No</td>
      <td>5000</td>
      <td>3667.0</td>
      <td>236.0</td>
      <td>360.0</td>
      <td>1.0</td>
      <td>Semiurban</td>
      <td>Y</td>
    </tr>
    <tr>
      <td>122</td>
      <td>Female</td>
      <td>No</td>
      <td>0</td>
      <td>Graduate</td>
      <td>No</td>
      <td>2137</td>
      <td>8980.0</td>
      <td>137.0</td>
      <td>360.0</td>
      <td>0.0</td>
      <td>Semiurban</td>
      <td>Y</td>
    </tr>
    <tr>
      <td>349</td>
      <td>Male</td>
      <td>Yes</td>
      <td>0</td>
      <td>Graduate</td>
      <td>No</td>
      <td>2625</td>
      <td>6250.0</td>
      <td>187.0</td>
      <td>360.0</td>
      <td>1.0</td>
      <td>Rural</td>
      <td>Y</td>
    </tr>
  </tbody>
</table>
</div>




```python
def plot_feature_importance(importance,names,model_type):

    #Create arrays from feature importance and feature names
    feature_importance = np.array(importance)
    feature_names = np.array(names)

    #Create a DataFrame using a Dictionary
    data={'feature_names':feature_names,'feature_importance':feature_importance}
    fi_df = pd.DataFrame(data)

    #Sort the DataFrame in order decreasing feature importance
    fi_df.sort_values(by=['feature_importance'], ascending=False,inplace=True)

    #Define size of bar plot
    plt.figure(figsize=(10,8))
    #Plot Searborn bar chart
    sns.barplot(x=fi_df['feature_importance'], y=fi_df['feature_names'])
    #Add chart labels
    plt.title(model_type + ' FEATURE IMPORTANCE')
    plt.xlabel('FEATURE IMPORTANCE')
    plt.ylabel('FEATURE NAMES')
```


```python
le = LabelEncoder()
df["Gender"] = le.fit_transform(df["Gender"].astype(str))
df["Married"] = le.fit_transform(df["Married"].astype(str))
df["Dependents"] = le.fit_transform(df["Dependents"].astype(str))
df["Self_Employed"] = le.fit_transform(df["Self_Employed"].astype(str))
df["Education"] = le.fit_transform(df["Education"].astype(str))
df["Property_Area"] = le.fit_transform(df["Property_Area"].astype(str))
df["Loan_Status"] = le.fit_transform(df["Loan_Status"].astype(str))
```


```python
rf_model = RandomForestClassifier().fit(df.drop("Loan_Status",axis=1),df["Loan_Status"])
```

    C:\ANACONDA\lib\site-packages\sklearn\ensemble\forest.py:245: FutureWarning: The default value of n_estimators will change from 10 in version 0.20 to 100 in 0.22.
      "10 in version 0.20 to 100 in 0.22.", FutureWarning)



```python
plot_feature_importance(rf_model.feature_importances_,df.drop("Loan_Status",axis=1).columns,'RANDOM FOREST')
```


![png](feature-importance_6_0.png)

