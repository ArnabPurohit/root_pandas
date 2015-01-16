
# root\_pandas

A convenience wrapper around the `root_numpy` library that allows you to load and save pandas DataFrames in the ROOT format used in high energy phyics.

```python
from pandas import DataFrame
from root_pandas import read_root

df = DataFrame({'x': [1, 2, 3], 'y': [4, 5, 6]})

df.to_root('test.root', 'tree')

df_new = read_root('test.root', 'tree', ignore=['x*'])

# DataFrames are extremely convenient
df['answer'] = 42

df.to_root('new.root')
# The file contains a tree called 'default' with the 'y' and 'answer' branches
```

