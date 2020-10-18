---
layout: post
title:  "Tiny ML"
date:   2020-10-11
category: ai
tag: Deep Learning
---

## Useful Tips for Jupyter Notebook


### 1. Multiple outputs at once

```python
from IPython.core.interactiveshell import InteractiveShell
InteractiveShell.ast_node_interactivity = "all"
```


### 2. Display all columns & rows of dataframe

```python
from IPython.display import display

df = pd.DataFrame()

pd.options.display.max_columns = None
pd.options.display.max_rows = None

display(df)
```