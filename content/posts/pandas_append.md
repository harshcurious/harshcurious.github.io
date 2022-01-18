---
title: "Some basic experiments with the pandas' append command"
date: 2021-12-24T12:04:10+05:30
draft: false

# weight: 1
# aliases: ["/first"]
tags: ['python', 'pandas', 'commands']
author: 'Harsh Kumar'
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: 'Taking a look at how the pd.append() command works in practice.'

disableShare: false
# to disable highlightjs
disableHLJS: false
searchHidden: false
cover:
  image: '<image path/url>' # image path/url
  alt: '<alt text>' # alt text
  caption: '<text>' # display caption under cover
  relative: false # when using page bundles set this to true
  hidden: true # only hide on current single page

plotly: false #turn plotly support on and off
mathjax: false #turn mathjax support on and off
---

# Understanding Commands: `pandas.append()`

## Basic Usage

```python
>>> import pandas as pd
>>> df = pd.DataFrame([[1, 2], [3, 4]], columns=list('AB'), index=['x', 'y'])
>>> df2 = pd.DataFrame([[5, 6], [7, 8]], columns=list('AB'), index=['x', 'y'])
>>> df.append(df2)
   A  B
x  1  2
y  3  4
x  5  6
y  7  8
>>> df
   A  B
x  1  2
y  3  4
>>> new = df.append(df2)
>>> new
   A  B
x  1  2
y  3  4
x  5  6
y  7  8
>>> df
   A  B
x  1  2
y  3  4
>>> df2
   A  B
x  5  6
y  7  8
>>> new.loc('x')
Traceback (most recent call last):
  File "/opt/anaconda/lib/python3.8/site-packages/pandas/core/generic.py", line 546, in _get_axis_number
    return cls._AXIS_TO_AXIS_NUMBER[axis]
KeyError: 'x'

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "/opt/anaconda/lib/python3.8/site-packages/pandas/core/indexing.py", line 637, in __call__
    axis = self.obj._get_axis_number(axis)
  File "/opt/anaconda/lib/python3.8/site-packages/pandas/core/generic.py", line 548, in _get_axis_number
    raise ValueError(f"No axis named {axis} for object type {cls.__name__}")
ValueError: No axis named x for object type DataFrame
>>> new.iloc(1)
<pandas.core.indexing._iLocIndexer object at 0x7fb5d1ff09a0>
>>> new.iloc[1]
A    3
B    4
Name: y, dtype: int64
>>> new.iloc[0]
A    1
B    2
Name: x, dtype: int64
>>> new.loc['x']
   A  B
x  1  2
x  5  6
```

Learnt/Recalled:

- `append` does **not** work **inplace** by default!
- Need to call `loc`/`iloc` with square bracket, **[]**, **not** parenthesis **()**.

```python
>>> df1 = pd.DataFrame([[1, 2], [3, 4]], columns=list('CD'), index=['x', 'y'])
>>> df.append(df1)
     A    B    C    D
x  1.0  2.0  NaN  NaN
y  3.0  4.0  NaN  NaN
x  NaN  NaN  1.0  2.0
y  NaN  NaN  3.0  4.0
>>> df3 = pd.DataFrame([[1, 2], [3, 4]], columns=list('CE'), index=['x', 'y'])
>>> df1.append(df3)
   C    D    E
x  1  2.0  NaN
y  3  4.0  NaN
x  1  NaN  2.0
y  3  NaN  4.0
```
