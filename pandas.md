## Group by and calculation
```python
data.groupby(['a', 'b'])['c'].agg(np_calc=np.sum, lambda_func=lambda x: x+10, el_list=list)
```

## Import csv when double quoted columns contain comma. A customised separator in the form of regex is required
```python
df = pd.read_csv(io.StringIO(test), header=None, sep='["]*,["]*', engine='python',skipinitialspace=True, quoting=1)
```

## Set column width to display full content
```
pd.set_option('display.max_colwidth', -1)
print(data.loc[data.col1>13000][['col2','col3']])
pd.reset_option('display.max_colwidth')
```

## Dask & multiprocessing for parallel processing when some_func() is expensive to run
```
import dask.dataframe as dd
import multiprocessing

ddf = dd.from_pandas(df, npartitions=4*multiprocessing.cpu_count()) \
        .map_partitions(lambda df: df.apply(lambda row: some_func(row.a, row.b), axis=1)) \
        .compute(scheduler='processes')
```
