---
title: "Train-test-split"
author: "Kamal"
date: 2020-08-11
description: "-"
type: technical_note
draft: false
---

```python
from sklearn.model_selection import train_test_split
```


```python
train_x,train_y, test_x,test_y = train_test_split(X, y, test_size=0.3)
```
