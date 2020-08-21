---
title: "Plot Importance in LightGBM"
author: "Charles"
date: 2020-08-16
description: "-"
type: technical_note
draft: false
---

```python
import lightgbm as lgb
import matplotlib.pyplot as plt
```


```python
fig, ax = plt.subplots(figsize=(14,20))
lgb.plot_importance(model, max_num_features=50, height=0.8, ax=ax)
#ax.grid(False) Prints in grid format
plt.title("LightGBM - Feature Importance", fontsize=16)
plt.show()
```

![Final plot look](lightgbm.png) 


```python

```
