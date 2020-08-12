---
title: "To_datetime"
author: "Kamal"
date: 2020-08-12
description: "-"
type: technical_note
draft: false
---

```python
import pandas as pd
```

#### Sample 1


```python
df = pd.DataFrame({'year': [2015, 2016],
                   'month': [2, 3],
                   'day': [4, 5]})
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
      <th>year</th>
      <th>month</th>
      <th>day</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>2015</td>
      <td>2</td>
      <td>4</td>
    </tr>
    <tr>
      <td>1</td>
      <td>2016</td>
      <td>3</td>
      <td>5</td>
    </tr>
  </tbody>
</table>
</div>




```python
df = pd.to_datetime(df)
df
```




    0   2015-02-04
    1   2016-03-05
    dtype: datetime64[ns]



#### Sample 2


```python
date = ["05SEP2014:12:45:54.000", "06SEP2014:06:21:41.000", "07SEP2014:07:30:40.000", "05OCT2014:05:26:23.000", "06OCT2014:22:30:17.000"]
```


```python
df = pd.DataFrame(date, columns = ["Date"])
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
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>05SEP2014:12:45:54.000</td>
    </tr>
    <tr>
      <td>1</td>
      <td>06SEP2014:06:21:41.000</td>
    </tr>
    <tr>
      <td>2</td>
      <td>07SEP2014:07:30:40.000</td>
    </tr>
    <tr>
      <td>3</td>
      <td>05OCT2014:05:26:23.000</td>
    </tr>
    <tr>
      <td>4</td>
      <td>06OCT2014:22:30:17.000</td>
    </tr>
  </tbody>
</table>
</div>




```python
df['Date'] =  pd.to_datetime(df['Date'], format='%d%b%Y:%H:%M:%S.%f')
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
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>2014-09-05 12:45:54</td>
    </tr>
    <tr>
      <td>1</td>
      <td>2014-09-06 06:21:41</td>
    </tr>
    <tr>
      <td>2</td>
      <td>2014-09-07 07:30:40</td>
    </tr>
    <tr>
      <td>3</td>
      <td>2014-10-05 05:26:23</td>
    </tr>
    <tr>
      <td>4</td>
      <td>2014-10-06 22:30:17</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
