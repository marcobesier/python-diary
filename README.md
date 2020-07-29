# python-diary
Data base for potential Python blog posts.


## 2020-07-13 - Check Data Frame for NaN's

To check a Pandas data frame, call it `df`, for NaN values, simply execute

`>>> df.isnull().values.any()`

If `False`, then you do not have any NaN's in your data.

## 2020-07-09 - Convert pd.Series Entries to Integers

Consider the following Pandas series:

```
>>> import pandas as pd
>>> sample_series = pd.Series([1.1, 2.2, 3.3])
>>> print(sample_series)
0    1.1
1    2.2
2    3.3
dtype: float64
```

You can convert the entries of this series to integers as follows:

```
>>> integer_sample_series = sample_series.astype(int)
>>> print(integer_sample_series)
0    1
1    2
2    3
dtype: int64
```
