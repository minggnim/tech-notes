### Change working directory to current running python file

```python
os.chdir(os.path.dirname(os.path.abspath(__file__)))
```

```python
class color:
   PURPLE = '\033[95m'
   CYAN = '\033[96m'
   DARKCYAN = '\033[36m'
   BLUE = '\033[94m'
   GREEN = '\033[92m'
   YELLOW = '\033[93m'
   RED = '\033[91m'
   BOLD = '\033[1m'
   UNDERLINE = '\033[4m'
   END = '\033[0m'
```

```python
list_ids = tuple(df.list_ids)
query = f'''
         select *
         from table
         where id_column in {list_ids}
         '''

df = pd.read_sql_query(query, conn)
'''
