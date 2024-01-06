# Unpack a lists inside a list
When you have a list of lists and you want to unpack them creatinga single list with all values

```python
list = [list1, list2, ...]
[x for l in list for x in l]
```

