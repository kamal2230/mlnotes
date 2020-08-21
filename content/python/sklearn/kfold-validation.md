---
title: "KFold Cross Validation"
author: "Charles"
date: 2020-08-17
description: "-"
type: technical_note
draft: false
---

```python
from sklearn.model_selection import KFold
```


```python
k_fold = KFold(n_splits=5, shuffle=True, random_state=2017)
pred_test_final = 0
```

### 5 folds are specified to show that 1 fold is for test and remaining is for train set. This is repeated for the next fold and so on. Minimum needs to be 2


```python
for d_ind, v_ind in k_fold.split(train_x):
    
    d_x, v_x = train_x.loc[d_ind, :], train_x.loc[v_ind, :]
    d_y, v_y = train_y[d_ind], train_y[v_ind]
    pred_test, model, evals_result = run_lgb(d_x, d_y, v_x, v_y, test_x) #Running LightGBM here
    pred_test_final += pred_test
pred_test_final /= 5
pred_test_final = np.expm1(pred_test_final) #e(pred_test_final)-1
```
