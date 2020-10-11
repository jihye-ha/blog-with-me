---
layout: post
title:  "How to handle big data"
date:   2020-10-11
category: bigdata
tags: [DataFrame, Spark]
---


## **Use `Vaex`**

Dask: scaling code to compute clusters
Vaex: easier to work on a single machine


These offer the following operations:
* calculating 10th quantile of a column,
* adding a new column,
* filtering by column,
* grouping by column and aggregating,
* visualizing a column.

<https://towardsdatascience.com/dask-vs-vaex-for-big-data-38cb66728747>


## **`Vaex` vs `Pandas` vs `Dask` vs `Spark`**

>>**How: The GIL, C++, and ApacheArrow**  
How is that even possible? Three ingredients are involved: C++, Apache Arrow and the Global Interpreter Lock GIL (GIL). In Python multithreading is hampered by the GIL, making all pure Python instructions effectively single threaded. When moving to C++, the GIL can be released and all cores of your machine will be used. To exploit this advantage, Vaex does all string operations in C++.
The next ingredient is to define an in-memory and on-disk data structure that is efficient in memory usage, and this is where Apache Arrow comes into play. Apache Arrow defines a well thought out StringArray that can be stored on disk, is friendly to the CPU, and even supports masked/null values. On top of that, it means that all projects supporting the Apache Arrow format will be able to use the same data structure without any memory copying.

>>**Conclusion:**  
Vaex uses ApacheArrow data structures and C++ to speed up string operations by a factor of about ~30–100x on a quadcore laptop, and up to 1000x on a 32 core machine. Nearly all of Pandas’ string operations are supported, and memory usage is practically zero because the lazy computations are done in chunks.


<https://towardsdatascience.com/vaex-a-dataframe-with-super-strings-789b92e8d861>

