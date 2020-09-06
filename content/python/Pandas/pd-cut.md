---
title: "Cut in pandas"
author: "Charles"
date: 2020-09-06
description: "-"
type: technical_note
draft: false
---

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```


```python
l = np.arange(1, 20)
l
```




    array([ 1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15, 16, 17,
           18, 19])




```python
pd.cut(l, bins=3)
```




    [(0.982, 7.0], (0.982, 7.0], (0.982, 7.0], (0.982, 7.0], (0.982, 7.0], ..., (13.0, 19.0], (13.0, 19.0], (13.0, 19.0], (13.0, 19.0], (13.0, 19.0]]
    Length: 19
    Categories (3, interval[float64]): [(0.982, 7.0] < (7.0, 13.0] < (13.0, 19.0]]




```python
pd.cut(l, bins=3, labels=["small", "medium", "large"])
```




    ['small', 'small', 'small', 'small', 'small', ..., 'large', 'large', 'large', 'large', 'large']
    Length: 19
    Categories (3, object): ['small' < 'medium' < 'large']




```python
df = pd.DataFrame(pd.cut(l, bins=3, labels=["small", "medium", "large"]))
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
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>small</td>
    </tr>
    <tr>
      <th>1</th>
      <td>small</td>
    </tr>
    <tr>
      <th>2</th>
      <td>small</td>
    </tr>
    <tr>
      <th>3</th>
      <td>small</td>
    </tr>
    <tr>
      <th>4</th>
      <td>small</td>
    </tr>
    <tr>
      <th>5</th>
      <td>small</td>
    </tr>
    <tr>
      <th>6</th>
      <td>small</td>
    </tr>
    <tr>
      <th>7</th>
      <td>medium</td>
    </tr>
    <tr>
      <th>8</th>
      <td>medium</td>
    </tr>
    <tr>
      <th>9</th>
      <td>medium</td>
    </tr>
    <tr>
      <th>10</th>
      <td>medium</td>
    </tr>
    <tr>
      <th>11</th>
      <td>medium</td>
    </tr>
    <tr>
      <th>12</th>
      <td>medium</td>
    </tr>
    <tr>
      <th>13</th>
      <td>large</td>
    </tr>
    <tr>
      <th>14</th>
      <td>large</td>
    </tr>
    <tr>
      <th>15</th>
      <td>large</td>
    </tr>
    <tr>
      <th>16</th>
      <td>large</td>
    </tr>
    <tr>
      <th>17</th>
      <td>large</td>
    </tr>
    <tr>
      <th>18</th>
      <td>large</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.value_counts().plot(kind='barh')
plt.show()
```


![png](pd-cut_6_0.png)



```python

```
