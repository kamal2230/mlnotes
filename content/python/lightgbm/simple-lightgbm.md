---
title: "Baseline LightGBM model"
author: "Charles"
date: 2020-08-16
description: "-"
type: technical_note
draft: false
---

```python
import lightgbm as lgb
```


```python
def run_lgb(train_x, train_y, val_x, val_y, test_x):
    parameters = {
        'objective': 'regression',
        'metric': 'rmse',
        'num_leaves': 30,
        'learning_rate': 0.01,
        'bagging_fraction': 0.7,
        'feature_fraction': 0.7,
        'bagging_frequency': 5,
        'bagging_seed': 2018,
        'verbosity': -1
    }
    
    lgtrain = lgb.Dataset(train_x, label=train_y)
    lgval = lgb.Dataset(val_x, label=val_y)
    evals_result = {}
    model = lgb.train(parameters, lgtrain, 1000, valid_sets=[lgval], early_stopping_rounds=100, verbose_eval=200, evals_result=evals_result)
    
    pred_test_y = model.predict(test_x, num_iteration=model.best_iteration)
    
    return pred_test_y, model, evals_result
```

After creating this you can call KFold cross validation in another snippet


```python

```
