---
title: "Plotting bar graph with categories"
author: "Charles"
date: 2020-08-12
description: "-"
type: technical_note
draft: false
---

```python
import matplotlib.pyplot as plt
import pandas as pd
```


```python
data = [['Hello mate', 0], ['xxXSADF', 1], ['GG boys', 0]]
df = pd.DataFrame(data, columns=['sentence', 'spam_ham'])

class_counts = pd.value_counts(df['spam_ham'], sort = True)
class_counts.plot(kind = 'bar', rot=0, color=['blue','red']) #Added colors as a list 
plt.title('Counts of Ham/Spam')
plt.xticks(range(2), ['Ham', 'Spam'])
plt.xlabel("Class")
plt.ylabel("Count")
```




    Text(0, 0.5, 'Count')




![png](categorical-bar-plot_2_1.png)



```python

```
