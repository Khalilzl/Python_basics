# Notebook settings

```python 
from IPython.core.interactiveshell import InteractiveShell
InteractiveShell.ast_node_interactivity = "all"
```

Some useful resources:
<br>
[Pandas](https://pandas.pydata.org/pandas-docs/stable/user_guide/10min.html)
[numpy quick start](https://numpy.org/doc/stable/user/quickstart.html)
[sklearn OLS](https://scikit-learn.org/stable/modules/linear_model.html#ordinary-least-squares)


# Python basics: Lists, tuples, Dictionaries, Arrays, Strings
## strip(), split(), and join() to split strings into lists and remove trailing spaces


```python 
# Strip
a = "this is a string        "
print(a)
a = a.strip()
print(a)

# Split
a = "this is a string"
print(a)
a = a.split(" ")
print(a)

# Join
print(a)
a = "-".join(a)
print(a)

```


