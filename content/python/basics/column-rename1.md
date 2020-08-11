---
title: "Column Rename"
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
d = {"Dialogue1": ["Vachitaya aapuuuuuuuuu","Sing in the rain","Valikudhu...Aludhuruve","Mande Badharam"], "Num1" : [11,12,13,14]}
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
      <th>Dialogue1</th>
      <th>Num1</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Vachitaya aapuuuuuuuuu</td>
      <td>11</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Sing in the rain</td>
      <td>12</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Valikudhu...Aludhuruve</td>
      <td>13</td>
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
df.columns = ["Dialogue2", "Num2"]
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
      <th>Dialogue2</th>
      <th>Num2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Vachitaya aapuuuuuuuuu</td>
      <td>11</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Sing in the rain</td>
      <td>12</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Valikudhu...Aludhuruve</td>
      <td>13</td>
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
df.rename(columns = {"Dialogue2":"Dialogue3"},inplace = True)
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
      <th>Dialogue3</th>
      <th>Num2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Vachitaya aapuuuuuuuuu</td>
      <td>11</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Sing in the rain</td>
      <td>12</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Valikudhu...Aludhuruve</td>
      <td>13</td>
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
