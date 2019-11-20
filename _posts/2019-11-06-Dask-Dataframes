---
layout:     post
title:      Dask Dataframes 
date:       2019-11-06 19:31:20
author:     Soumya Chopra
---

What is Pandas?
Pandas is a python package used for data manipulation, analysis and cleaning. It is well suited for different kinds of data, such as:

- Tabular data with heterogeneously-typed columns
- Ordered and unordered time series data
- Arbitrary matrix data with row & column labels
- Unlabelled data

What is Dask?
Dask is a parallel computing library in Python that scales the existing Python ecosystem. This python library can handle moderately large datasets on a single CPU by making use of multiple cores of machines or on a cluster of machines (distributed computing).

Dask stores the complete data on the disk in order to use less memory during computations. It uses data from the disk in chunks for processing. During processing, if intermediate values are generated they are discarded as soon as possible to save the memory consumption.

Also, it is not necessary that all the machines have same number of cores. Dask can internally handle the variations with the number of cores on a machine ie. it is possible that one system has 2 cores while the other has 4 cores.

What is Dask DataFrame?
A Dataframe is simply a two-dimensional data structure used to align data in a tabular form consisting of rows and columns.

A Dask DataFrame is composed of many smaller Pandas DataFrames that are split row-wise along the index. An operation on a single Dask DataFrame triggers many operations on the Pandas DataFrames that constitutes it. The pandas Dataframes may reside on the disk of a single machine or a number of different machines forming a cluster.
daskdataframe

When you are working with DataFrame operations that tend to reshape the data you must know that the rows are referred to as “axis 0” and the columns are referred to as “axis 1”. DataFrame operations by default work along axis 0.

When to Use the Dask DataFrame?
Dask DataFrame is usually used when Pandas fails due to data size or computation speed. Pandas serves the purpose when you have tabular datasets that fit in memory. Dask becomes useful when the dataset that you want to analyze is larger than the RAM of your machine as it can run on your local computer or it can be scaled up to run on a cluster. It can also be also be used for long computations to accelarate the speed of computation by using many cores.

