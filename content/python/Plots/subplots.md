---
title: "Subplots that share X axis"
author: "Charles"
date: 2020-08-12
description: "-"
type: technical_note
draft: false
---

```python
import matplotlib.pyplot as plt
```


```python
data1 = {'objects': ['apple', 'banana', 'mango', 'orange', 'tomato', 'potato'], 'price':[4, 7, 12, 10, 9, 14]}
```


```python
fig, ax = plt.subplots(2, 1, sharex=True)
ax[0].bar(data1['objects'], data1['price'])
ax[1].plot(data1['objects'], data1['price'])
fig.suptitle('Subplot example')
```




    Text(0.5, 0.98, 'Subplot example')




![png](subplots_3_1.png)

