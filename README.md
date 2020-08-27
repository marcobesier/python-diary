# python-diary
Some useful notes on Python.

## 2020-08-26 - Remove the Middle Item of a List of Odd Length

```
>>> odd_list = [1, 2, 3, 4, 5]
>>> del odd_list[len(odd_list)//2]
>>> odd_list
[1, 2, 4, 5]
```

## 2020-08-26 - Two Ways to Print a Rounded Float

```
>>> some_float = 1.23456789
>>> print('The rounded float is: {}'.format(round(some_float, 2)))
The rounded float is: 1.23
>>> print('The rounded float is: %.2f' % some_float)
The rounded float is: 1.23
```

## 2020-08-04 - Selecting Data Frame Rows With `isin`

Say you have a data frame `df` with a column called `name`, and say you want to select
all rows where `name` either equals `'Susan'`, or `'Jess'`, or `'Pete'`.

One way to achieve this would be:

`>>> df[(df.name == 'Susan') | (df.name == 'Jess') | (df.name == 'Pete')]`

However, you can make your code more concise using `isin`:

`>>> df[df.name.isin(['Susan', 'Jess', 'Pete'])]`

## 2020-08-03 - How much percent of a NumPy array's entries fulfill a condition

You can easily compute how much percent of a NumPy array's entries fulfill a
certain condition by using NumPy's `mean` function.

```
>>> import numpy as np
>>> twenty_percent_eq_5 = np.array([1, 2, 3, 4, 5])
>>> np.mean(twenty_percent_eq_5 == 5)
0.20000000000000001
```

This works because the condition is evaluated for each entry of the array and
returns either 1 (True) or 0 (False). Subsequently, the `mean` function
adds up all 0's and 1's and divides the sum by the array's length.

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
