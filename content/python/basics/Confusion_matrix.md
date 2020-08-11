---
title: "Confusion Matrix"
author: "Kamal"
date: 2020-08-11
description: "-"
type: technical_note
draft: false
---

```python
from sklearn.metrics import confusion_matrix, classification_report 
```


```python
C="Cat"
F="Fish"
H="Hen"
```


```python
true = [C,C,C,C,C,C,C,C,C,C, F,F,F,F,F,F,F,F,F,F, H,H,H,H,H,H,H,H,H,H,H]

pred = [C,C,C,C,C,C,F,H,F,C, C,C,H,F,F,F,F,F,F,H, H,H,H,H,H,H,C,F,H,H,H]
```


```python
confusion_matrix(true,pred)
```




    array([[7, 2, 1],
           [2, 6, 2],
           [1, 1, 9]], dtype=int64)




```python
print(classification_report(true,pred))
```

                  precision    recall  f1-score   support
    
             Cat       0.70      0.70      0.70        10
            Fish       0.67      0.60      0.63        10
             Hen       0.75      0.82      0.78        11
    
        accuracy                           0.71        31
       macro avg       0.71      0.71      0.70        31
    weighted avg       0.71      0.71      0.71        31
    



```python

```
