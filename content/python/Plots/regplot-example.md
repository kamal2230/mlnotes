---
title: "Example of Regplot in Seaborn"
author: "Charles"
date: 2020-08-08
description: "-"
type: technical_note
draft: false
---

```python
import seaborn as sns
```


```python
x_ex = [1, 1, 0, 0, 1, 0, 1, 0, 1, 1, 1, 0, 0]

y_ex = [0, 0, 1, 0, 1, 0, 1, 1, 0, 0, 0, 1, 1]
```


```python
sns.regplot(x = x_ex, y = y_ex, marker = '*', color = 'b')
```




    <AxesSubplot:>




![png](regplot-example_3_1.png)



```python

```
