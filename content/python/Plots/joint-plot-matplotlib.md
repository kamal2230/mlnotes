---
title: "Joint plot in Matplotlib"
author: "Charles"
date: 2020-08-12
description: "-"
type: technical_note
draft: false
---
**Joint plot is generally easy with Seaborn with the command**


```python
import matplotlib.pyplot as plt
plt.Figure.add_axes
plt.Figure.add_subplot
plt.Figure.add_gridspec
plt.Axes.scatter
plt.Axes.hist
import numpy as np
```


```python
np.random.seed(19680801)

x = np.random.randn(1000)
y = np.random.randn(1000)
```


```python
def scatter_hist(x, y, ax, ax_histx, ax_histy):
    # no labels
    ax_histx.tick_params(axis="x", labelbottom=False)
    ax_histy.tick_params(axis="y", labelleft=False)

    # the scatter plot:
    ax.scatter(x, y)

    # now determine nice limits by hand:
    binwidth = 0.25
    xymax = max(np.max(np.abs(x)), np.max(np.abs(y)))
    lim = (int(xymax/binwidth) + 1) * binwidth

    bins = np.arange(-lim, lim + binwidth, binwidth)
    ax_histx.hist(x, bins=bins)
    ax_histy.hist(y, bins=bins, orientation='horizontal')
```


```python
left, width = 0.1, 0.65
bottom, height = 0.1, 0.65
spacing = 0.005


rect_scatter = [left, bottom, width, height]
rect_histx = [left, bottom + height + spacing, width, 0.2]
rect_histy = [left + width + spacing, bottom, 0.2, height]

# start with a square Figure
fig = plt.figure(figsize=(8, 8))

ax = fig.add_axes(rect_scatter)
ax_histx = fig.add_axes(rect_histx, sharex=ax)
ax_histy = fig.add_axes(rect_histy, sharey=ax)

# use the previously defined function
scatter_hist(x, y, ax, ax_histx, ax_histy)

plt.show()
```


![png](joint-plot-matplotlib_5_0.png)

