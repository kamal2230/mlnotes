---
title: "Violin Plot"
author: "Charles"
date: 2020-08-12
description: "-"
type: technical_note
draft: false
---

```python
import matplotlib.pyplot as plt
import numpy as np
```


```python
import numpy as np
np.random.seed(10)
collectn_1 = np.random.normal(100, 10, 200)
collectn_2 = np.random.normal(80, 30, 200)
collectn_3 = np.random.normal(90, 20, 200)
collectn_4 = np.random.normal(70, 25, 200)

data_to_plot = [collectn_1, collectn_2, collectn_3, collectn_4]

fig, ax = plt.subplots(1, 1)

bp = ax.violinplot(data_to_plot)
plt.show()
```


![png](violin-plot_2_0.png)



```python

```
