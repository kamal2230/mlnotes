---
title: "Apply Function"
author: "Kamal"
date: 2020-08-11
description: "-"
type: technical_note
draft: false
---

```python
import pandas as pd
import numpy as np
```


```python
d = ["Vachitaya aapuuuuuuuuu","Sing in the rain","Valikudhu...Aludhuruve","Mande Badharam"]
```


```python
df = pd.DataFrame(d, columns = ['Dialogue'])
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
      <th>Dialogue</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Vachitaya aapuuuuuuuuu</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Sing in the rain</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Valikudhu...Aludhuruve</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Mande Badharam</td>
    </tr>
  </tbody>
</table>
</div>




```python
def func(msg):
    return len(msg)
```


```python
df["Length"] = df["Dialogue"].apply(func)
```


```python
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
      <th>Dialogue</th>
      <th>Length</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Vachitaya aapuuuuuuuuu</td>
      <td>22</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Sing in the rain</td>
      <td>16</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Valikudhu...Aludhuruve</td>
      <td>22</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Mande Badharam</td>
      <td>14</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
