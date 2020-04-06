## Group by and calculation
```python
data.groupby(['a', 'b'])['c'].agg(np_calc=np.sum, lambda_func=lambda x: x+10, el_list=list)
```

## Import csv when double quoted columns contain comma. A customised separator in the form of regex is required
```python
df = pd.read_csv(io.StringIO(test), header=None, sep='["]*,["]*', engine='python',skipinitialspace=True, quoting=1)
```
