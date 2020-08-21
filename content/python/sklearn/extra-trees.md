---
title: "Extra Trees Regressor"
author: "Charles"
date: 2020-08-16
description: "-"
type: technical_note
draft: false
---

```python
from sklearn import ensemble
```


```python
model = ensemble.ExtraTreesRegressor(n_estimators=200, max_depth=20, max_features=0.5, n_jobs=-1, random_state=0)
model.fit(tr_x, tr_y)
```

With Tuning the parameters can be even better
