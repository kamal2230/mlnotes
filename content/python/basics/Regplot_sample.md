---
title: "Regplot Sample"
author: "Kamal"
date: 2020-08-11
description: "-"
type: technical_note
draft: false
---

```python
import seaborn as sns
```


```python
a = [1,1,0,0,1,0,1,0,1,1,1,0,0]

b = [0,0,1,0,1,0,1,1,0,0,0,1,1]
```


```python
sns.regplot(x = a, y = b , marker = "*", color="g")
```




    <matplotlib.axes._subplots.AxesSubplot at 0x1d80b3f4e88>




![png](Regplot_sample_3_1.png)



```python

```
