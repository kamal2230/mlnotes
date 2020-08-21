---
title: "Bar plot"
author: "Charles"
date: 2020-08-12
description: "-"
type: technical_note
draft: false
---

```python
import matplotlib.pyplot as plt
import pandas as pd
```


```python
data = {'fruits': ['apple', 'banana', 'mango', 'orange'], 'price':[4, 7, 12, 10]}
```


```python
df = pd.DataFrame(data)
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
      <th>fruits</th>
      <th>price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>apple</td>
      <td>4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>banana</td>
      <td>7</td>
    </tr>
    <tr>
      <th>2</th>
      <td>mango</td>
      <td>12</td>
    </tr>
    <tr>
      <th>3</th>
      <td>orange</td>
      <td>10</td>
    </tr>
  </tbody>
</table>
</div>




```python
plt.bar(df['fruits'], df['price'])
```




    <BarContainer object of 4 artists>




![png](basic-bar-plot_4_1.png)



```python

```
