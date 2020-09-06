---
title: "Learning_and_predicting"
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
from sklearn import svm
clf = svm.SVC(gamma=0.001, C=100.)
```


```python
clf.fit(digits.data[:-1], digits.target[:-1])
```




    SVC(C=100.0, gamma=0.001)




```python
clf.predict(digits.data[-1:])

```




    array([8])


