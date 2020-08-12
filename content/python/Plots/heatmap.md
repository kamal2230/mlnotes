---
title: "Heatmap"
author: "Kamal"
date: 2020-08-12
description: "-"
type: technical_note
draft: false
---

```python
import pandas as pd
import seaborn as sb
```


```python
df = pd.read_csv("D:/Datasets/Wine Quality/winequality-white.csv",sep=";")
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
      <th>fixed acidity</th>
      <th>volatile acidity</th>
      <th>citric acid</th>
      <th>residual sugar</th>
      <th>chlorides</th>
      <th>free sulfur dioxide</th>
      <th>total sulfur dioxide</th>
      <th>density</th>
      <th>pH</th>
      <th>sulphates</th>
      <th>alcohol</th>
      <th>quality</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>2694</td>
      <td>6.2</td>
      <td>0.28</td>
      <td>0.27</td>
      <td>10.3</td>
      <td>0.030</td>
      <td>26.0</td>
      <td>108.0</td>
      <td>0.99388</td>
      <td>3.20</td>
      <td>0.36</td>
      <td>10.7</td>
      <td>6</td>
    </tr>
    <tr>
      <td>2542</td>
      <td>8.9</td>
      <td>0.27</td>
      <td>0.34</td>
      <td>10.7</td>
      <td>0.029</td>
      <td>19.5</td>
      <td>166.0</td>
      <td>0.99669</td>
      <td>3.13</td>
      <td>0.48</td>
      <td>10.6</td>
      <td>5</td>
    </tr>
    <tr>
      <td>1170</td>
      <td>7.7</td>
      <td>0.25</td>
      <td>0.43</td>
      <td>4.5</td>
      <td>0.062</td>
      <td>20.0</td>
      <td>115.0</td>
      <td>0.99660</td>
      <td>3.38</td>
      <td>0.50</td>
      <td>9.9</td>
      <td>6</td>
    </tr>
    <tr>
      <td>4622</td>
      <td>6.5</td>
      <td>0.50</td>
      <td>0.22</td>
      <td>4.1</td>
      <td>0.036</td>
      <td>35.0</td>
      <td>131.0</td>
      <td>0.99020</td>
      <td>3.26</td>
      <td>0.55</td>
      <td>13.0</td>
      <td>7</td>
    </tr>
    <tr>
      <td>3681</td>
      <td>7.0</td>
      <td>0.22</td>
      <td>0.26</td>
      <td>9.2</td>
      <td>0.027</td>
      <td>37.0</td>
      <td>122.0</td>
      <td>0.99228</td>
      <td>3.06</td>
      <td>0.34</td>
      <td>12.5</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
d = df.corr().round(2)
sb.set(rc={"figure.figsize":(20,15)}) #plot-size
sb.heatmap(data = d,annot = True)
```




    <matplotlib.axes._subplots.AxesSubplot at 0x195b1fffc48>




![png](heatmap_3_1.png)



```python

```
