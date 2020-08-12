---
title: "nrows in read_csv"
author: "Kamal"
date: 2020-08-11
description: "-"
type: technical_note
draft: false
---
#### Limit Rows in read_csv


```python
import pandas as pd
```


```python
df = pd.read_csv("name.csv", nrows = 5000) #returns first 5000 rows
```
