---
title: "Spearman Coefficient"
author: "Charles"
date: 2020-08-15
description: "-"
type: technical_note
draft: false
---

```python
import pandas as pd
from scipy.stats import spearmanr
import numpy as np
import warnings #Used primarily to ignore warnings
warnings.filterwarnings("ignore")
```


```python
df = pd.read_csv('train.csv')
```


```python
labels = []
values = []

for col in df.columns:
    if col not in ["ID", "target"]:
        labels.append(col)
        values.append(spearmanr(df[col].values, df['target'].values)[0])

correlation_df = pd.DataFrame({'column_label':labels, 'correlation_val':values})        
correlation_df = correlation_df.sort_values(by='correlation_val')

correlation_df = correlation_df[(correlation_df['correlation_val']>0.1) | (correlation_df['correlation_val']<-0.1)]
correlation_df
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
      <th>column_label</th>
      <th>correlation_val</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>216</th>
      <td>77eb013ca</td>
      <td>-0.116095</td>
    </tr>
    <tr>
      <th>1908</th>
      <td>a60027bb4</td>
      <td>-0.115835</td>
    </tr>
    <tr>
      <th>1378</th>
      <td>3adf5e2b5</td>
      <td>-0.114185</td>
    </tr>
    <tr>
      <th>220</th>
      <td>186b87c05</td>
      <td>-0.113428</td>
    </tr>
    <tr>
      <th>2232</th>
      <td>f8b733d3f</td>
      <td>-0.113011</td>
    </tr>
    <tr>
      <th>2158</th>
      <td>715fa74a4</td>
      <td>-0.112752</td>
    </tr>
    <tr>
      <th>2471</th>
      <td>08af3dd45</td>
      <td>-0.112729</td>
    </tr>
    <tr>
      <th>3595</th>
      <td>7b1ddbabf</td>
      <td>-0.112540</td>
    </tr>
    <tr>
      <th>2102</th>
      <td>adadb9a96</td>
      <td>-0.112109</td>
    </tr>
    <tr>
      <th>2870</th>
      <td>8485abcab</td>
      <td>-0.111304</td>
    </tr>
    <tr>
      <th>4852</th>
      <td>c7ae29e66</td>
      <td>-0.110687</td>
    </tr>
    <tr>
      <th>3600</th>
      <td>4f2f6b0b3</td>
      <td>-0.110345</td>
    </tr>
    <tr>
      <th>4772</th>
      <td>67f9e982f</td>
      <td>-0.110242</td>
    </tr>
    <tr>
      <th>2341</th>
      <td>e7071d5e3</td>
      <td>-0.109869</td>
    </tr>
    <tr>
      <th>4152</th>
      <td>e17f1f07c</td>
      <td>-0.109022</td>
    </tr>
    <tr>
      <th>3275</th>
      <td>f41f0eb2f</td>
      <td>-0.108897</td>
    </tr>
    <tr>
      <th>3767</th>
      <td>fbe52b1b2</td>
      <td>-0.108612</td>
    </tr>
    <tr>
      <th>672</th>
      <td>f2520b601</td>
      <td>-0.108505</td>
    </tr>
    <tr>
      <th>2974</th>
      <td>cd8048913</td>
      <td>-0.108488</td>
    </tr>
    <tr>
      <th>2574</th>
      <td>2c136905e</td>
      <td>-0.108038</td>
    </tr>
    <tr>
      <th>3602</th>
      <td>e5ac02d3c</td>
      <td>-0.106720</td>
    </tr>
    <tr>
      <th>3852</th>
      <td>994b4c2ac</td>
      <td>-0.106573</td>
    </tr>
    <tr>
      <th>3066</th>
      <td>cb162bd89</td>
      <td>-0.106288</td>
    </tr>
    <tr>
      <th>552</th>
      <td>1d79bc053</td>
      <td>-0.105551</td>
    </tr>
    <tr>
      <th>1392</th>
      <td>dd85a900c</td>
      <td>-0.105311</td>
    </tr>
    <tr>
      <th>757</th>
      <td>08d203407</td>
      <td>-0.105278</td>
    </tr>
    <tr>
      <th>1129</th>
      <td>cbf236577</td>
      <td>-0.104954</td>
    </tr>
    <tr>
      <th>1968</th>
      <td>28dc3cc44</td>
      <td>-0.104916</td>
    </tr>
    <tr>
      <th>2320</th>
      <td>a8ef2a0d2</td>
      <td>-0.104837</td>
    </tr>
    <tr>
      <th>3117</th>
      <td>45cda25bb</td>
      <td>-0.104755</td>
    </tr>
    <tr>
      <th>1722</th>
      <td>fd9968f0d</td>
      <td>-0.104548</td>
    </tr>
    <tr>
      <th>1238</th>
      <td>89db78d8e</td>
      <td>-0.104448</td>
    </tr>
    <tr>
      <th>4667</th>
      <td>9e2040e5b</td>
      <td>-0.104247</td>
    </tr>
    <tr>
      <th>1224</th>
      <td>b6fa5a5fd</td>
      <td>-0.104106</td>
    </tr>
    <tr>
      <th>299</th>
      <td>fa6e76901</td>
      <td>-0.103114</td>
    </tr>
    <tr>
      <th>774</th>
      <td>83e2ae51c</td>
      <td>-0.102465</td>
    </tr>
    <tr>
      <th>651</th>
      <td>e9c7ccc05</td>
      <td>-0.102174</td>
    </tr>
    <tr>
      <th>229</th>
      <td>0c4bf4863</td>
      <td>-0.101714</td>
    </tr>
    <tr>
      <th>2999</th>
      <td>13d853d22</td>
      <td>-0.101657</td>
    </tr>
    <tr>
      <th>3922</th>
      <td>0eebebc7c</td>
      <td>-0.101501</td>
    </tr>
    <tr>
      <th>332</th>
      <td>707f193d9</td>
      <td>-0.101385</td>
    </tr>
    <tr>
      <th>1041</th>
      <td>5a88e3d89</td>
      <td>-0.100786</td>
    </tr>
    <tr>
      <th>2425</th>
      <td>ea397d576</td>
      <td>-0.100696</td>
    </tr>
    <tr>
      <th>2417</th>
      <td>912f4f5de</td>
      <td>-0.100464</td>
    </tr>
    <tr>
      <th>4875</th>
      <td>896d1c52d</td>
      <td>-0.100381</td>
    </tr>
    <tr>
      <th>1990</th>
      <td>e2b4d4ef7</td>
      <td>-0.100337</td>
    </tr>
    <tr>
      <th>4178</th>
      <td>06b19b6c4</td>
      <td>-0.100202</td>
    </tr>
    <tr>
      <th>4358</th>
      <td>f190486d6</td>
      <td>0.107678</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
