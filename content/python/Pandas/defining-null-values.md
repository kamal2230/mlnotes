---
title: "Defining Null Values"
author: "Kamal"
date: 2020-08-12
description: "-"
type: technical_note
draft: false
---

```python
import pandas as pd
```


```python
d = {'First Score':[100, 90, ".", 95], 
        'Second Score': [30, 45, 56, "-"], 
        'Third Score':["NIL", 40, 80, 98]} 
```


```python
df = pd.DataFrame(d)
df
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
      <th>First Score</th>
      <th>Second Score</th>
      <th>Third Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>100</td>
      <td>30</td>
      <td>NIL</td>
    </tr>
    <tr>
      <td>1</td>
      <td>90</td>
      <td>45</td>
      <td>40</td>
    </tr>
    <tr>
      <td>2</td>
      <td>.</td>
      <td>56</td>
      <td>80</td>
    </tr>
    <tr>
      <td>3</td>
      <td>95</td>
      <td>-</td>
      <td>98</td>
    </tr>
  </tbody>
</table>
</div>




```python
df = df.apply(pd.to_numeric, errors='coerce')
df
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
      <th>First Score</th>
      <th>Second Score</th>
      <th>Third Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>100.0</td>
      <td>30.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>1</td>
      <td>90.0</td>
      <td>45.0</td>
      <td>40.0</td>
    </tr>
    <tr>
      <td>2</td>
      <td>NaN</td>
      <td>56.0</td>
      <td>80.0</td>
    </tr>
    <tr>
      <td>3</td>
      <td>95.0</td>
      <td>NaN</td>
      <td>98.0</td>
    </tr>
  </tbody>
</table>
</div>



#### In read_csv


```python
df = pd.read_csv("name.csv", na_values = ['NIL', '.','-'])
```
