---
title: "Type_casting"
author: "Aavinash"
date: 2020-09-04
description: "-"
type: technical_note
draft: false
---

```python
import numpy as np
from sklearn import random_projection

rng = np.random.RandomState(0)
X = rng.rand(10, 2000)
X = np.array(X, dtype='float32')
X.dtype
```




    dtype('float32')




```python
transformer = random_projection.GaussianRandomProjection()
X_new = transformer.fit_transform(X)
X_new.dtype
```




    dtype('float64')




```python
from sklearn import datasets
from sklearn.svm import SVC
iris = datasets.load_iris()
clf = SVC()
clf.fit(iris.data, iris.target)
```




    SVC()




```python
list(clf.predict(iris.data[:3]))
```




    [0, 0, 0]




```python
clf.fit(iris.data, iris.target_names[iris.target])
```




    SVC()




```python
list(clf.predict(iris.data[:3]))
```




    ['setosa', 'setosa', 'setosa']


