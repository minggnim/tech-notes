### Change working directory to current running python file

```python
os.chdir(os.path.dirname(os.path.abspath(__file__)))
```