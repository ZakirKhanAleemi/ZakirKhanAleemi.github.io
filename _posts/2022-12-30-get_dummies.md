---
layout: post
published: True
title: get_dummies Function in Python
---


`pandas.get_dummies` is a function in the Pandas library for Python that is used to convert categorical variables into dummy/indicator variables.

It takes a dataframe and a list of columns as input, and returns a new dataframe with the specified columns converted into dummy variables. Each unique value in a categorical column will be converted into a separate column with a 1 or 0 indicating the presence or absence of that value in the original data.

Here's an example of how you might use `get_dummies`:

```
import pandas as pd

# Create a sample dataframe with a categorical column
df = pd.DataFrame({'color': ['red', 'green', 'blue', 'red', 'green'], 'value': [1, 2, 3, 4, 5]})

# Use get_dummies to convert the 'color' column into dummy variables
df_dummies = pd.get_dummies(df, columns=['color'])

# The original dataframe with 'color' as a categorical column
print(df)

# The new dataframe with 'color' converted into dummy variables
print(df_dummies)
```
The output of this code would be:

```
   color  value
0    red      1
1  green      2
2   blue      3
3    red      4
4  green      5
   value  color_blue  color_green  color_red
0      1           0            0          1
1      2           0            1          0
2      3           1            0          0
3      4           0            0          1
4      5           0            1          0
```

As you can see, the original 'color' column has been replaced with three new columns: 'color_blue', 'color_green', and 'color_red', which indicate the presence or absence of each color in the original data.
