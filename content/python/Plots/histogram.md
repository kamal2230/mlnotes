---
title: "Histogram"
author: "Charles"
date: 2020-08-12
description: "-"
type: technical_note
draft: false
---

```python
import pandas as pd
import matplotlib.pyplot as plt
```


```python
def sent_length(message):
    
    return (len(message))
```


```python
data = ['Vachitaya aapuuuuuuuuu','Sing in the rain' ,'Great power comes wih great responsibility']  
df = pd.DataFrame(data, columns = ['Sent'])

df['len'] = df['Sent'].apply(sent_length)

plt.hist(df['len'], bins=15)
```




    (array([1., 0., 0., 1., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 1.]),
     array([16.        , 17.73333333, 19.46666667, 21.2       , 22.93333333,
            24.66666667, 26.4       , 28.13333333, 29.86666667, 31.6       ,
            33.33333333, 35.06666667, 36.8       , 38.53333333, 40.26666667,
            42.        ]),
     <BarContainer object of 15 artists>)




![png](histogram_3_1.png)



```python

```
