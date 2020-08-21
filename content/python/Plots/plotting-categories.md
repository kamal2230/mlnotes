---
title: "Plotting Categories using Subplots"
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
data = {'apple': 4, 'banana': 7, 'mango': 12, 'orange': 10}
fruit_names = list(data.keys())
prices = list(data.values())
```


```python
fig, ax = plt.subplots(1, 3, figsize=(9, 3), sharey=True)
ax[0].bar(fruit_names, prices)
ax[1].scatter(fruit_names, prices)
ax[2].plot(fruit_names, prices)
fig.suptitle('Plottting Categories')
```




    Text(0.5, 0.98, 'Plottting Categories')




![png](plotting-categories_3_1.png)

