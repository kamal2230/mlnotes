---
title: "Refitting"
author: "Aavinash"
date: 2020-09-04
description: "-"
type: technical_note
draft: false
---

```python
import numpy as np
from sklearn.datasets import load_iris
from sklearn.svm import SVC
X, y = load_iris(return_X_y=True)
```


```python
clf = SVC()
clf.set_params(kernel='linear').fit(X, y)

```




    SVC(kernel='linear')




```python
clf.predict(X[:5])
```




    array([0, 0, 0, 0, 0])




```python
clf.set_params(kernel='rbf').fit(X, y)
```




    SVC()




```python
clf.predict(X[:5])
```




    array([0, 0, 0, 0, 0])


