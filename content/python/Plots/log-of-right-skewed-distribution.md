---
title: "Better way to show Left Skewed Distributions"
author: "Charles"
date: 2020-08-14
description: "-"
type: technical_note
draft: false
---

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```


```python
df = pd.read_csv('train.csv')
```


```python
plt.figure(figsize=(12,8))
sns.distplot(df["target"].values, bins=50, kde=False)
plt.xlabel('Test', fontsize=12)
plt.title("Test Histogram", fontsize=14)
plt.show()
```


![png](log-of-right-skewed-distribution_3_0.png)


This is a left skewed distribution. The basis of scoring will vary if this is what they give. Best way to deal with it is show it in a log scale


```python
import numpy as np #For log function
plt.figure(figsize=(12,8)) #Define size of figure
sns.distplot(np.log1p(df["target"].values), bins=50, kde=False)
plt.xlabel('Test', fontsize=12)
plt.title("Log of the Test Histogram", fontsize=14)
plt.show()
```


![png](log-of-right-skewed-distribution_5_0.png)


Looks much better now
