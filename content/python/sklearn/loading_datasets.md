---
title: "Loading_Datasets"
author: "Aavinash"
date: 2020-09-04
description: "-"
type: technical_note
draft: false
---

```python
from sklearn import datasets
iris = datasets.load_iris()
digits = datasets.load_digits()
```


```python
print(digits.data)
```

    [[ 0.  0.  5. ...  0.  0.  0.]
     [ 0.  0.  0. ... 10.  0.  0.]
     [ 0.  0.  0. ... 16.  9.  0.]
     ...
     [ 0.  0.  1. ...  6.  0.  0.]
     [ 0.  0.  2. ... 12.  0.  0.]
     [ 0.  0. 10. ... 12.  1.  0.]]



```python
digits.target
```




    array([0, 1, 2, ..., 8, 9, 8])




```python

```
