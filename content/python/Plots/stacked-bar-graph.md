---
title: "Stacked Bar Graph"
author: "Charles"
date: 2020-08-10
description: "-"
type: technical_note
draft: false
---

```python
import matplotlib.pyplot as plt
import numpy as np
```


```python
#With error bars
N = 5
menMeans = (20, 35, 30, 35, 27)
womenMeans = (25, 32, 34, 20, 25)
menStd = (2, 3, 4, 1, 2)
womenStd = (3, 5, 2, 3, 3)
ind = np.arange(N)    
width = 0.35       

p1 = plt.bar(ind, menMeans, width, yerr=menStd)
p2 = plt.bar(ind, womenMeans, width, bottom=menMeans, yerr=womenStd)

plt.ylabel('Scores')
plt.title('Scores by group and gender')
plt.xticks(ind, ('G1', 'G2', 'G3', 'G4', 'G5'))
plt.yticks(np.arange(0, 81, 10))
plt.legend((p1[0], p2[0]), ('Men', 'Women'))
```




    <matplotlib.legend.Legend at 0x7fe44a9e1a90>




![png](stacked-bar-graph_2_1.png)



```python
#Without error bars
p1 = plt.bar(ind, menMeans, width)
p2 = plt.bar(ind, womenMeans, width, bottom=menMeans)

plt.ylabel('Scores')
plt.title('Scores by group and gender')
plt.xticks(ind, ('G1', 'G2', 'G3', 'G4', 'G5'))
plt.yticks(np.arange(0, 81, 10))
plt.legend((p1[0], p2[0]), ('Men', 'Women'))
```




    <matplotlib.legend.Legend at 0x7fe44d2e82e0>




![png](stacked-bar-graph_3_1.png)



```python

```
