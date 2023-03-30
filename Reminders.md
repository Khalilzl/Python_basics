## Notebook settings

```python 
from IPython.core.interactiveshell import InteractiveShell
InteractiveShell.ast_node_interactivity = "all"
```

## Python basics: Manipulating lists, tuples, dictionaries, arrays, and strings
### strip(), split(), and join() to split strings into lists and remove trailing spaces

```python 
# Strip removes trailing spaces
a = "this is a string        "
a = a.strip()

# Split splits a string into a list of tokens
a = "this is a string"
a = a.split(" ")
# The output is: ['this', 'is', 'a', 'string']

# Join, joins iterable elements, separated by the character specified between ""
a = "-".join(a)

```

### Filtering a list using list comprehenshion
```python
numbers = [70, 60, 80, 90, 50,82,90,91]
filtered_list = [ i for i in numbers if i>= 80]
```

### Sorting a list based on tuple positions
```python
# Sorting based on first element of the tuple
my_list = [['d',2],['v',4],['a',3]]
print(sorted(my_list,key = lambda tup: tup[0],reverse=False))

# Sorting based on all elements in tuple (2 var)
my_list = [['d',2],['v',4],['a',3],['v',5]]
sorted(my_list, key=lambda tup: (tup[0],tup[1]),reverse=True)
sorted(my_list, key=lambda tup: (tup[0],-tup[1]),reverse=True)

# Sorting based on all elements in tuple (3 var)
l = [[1,3,2],[3,4,2],[3,1,4],[1,2,3]]
print(sorted(l, key= lambda t:(t[0],t[1],t[2])))
```

### Filtering a dictionary based on values or keys

```python 
# Filtering based on values
d1 = {'a':1,'b':2,'c':3}
new_dict = {key: value for key, value in d1.items() if value > 1}

# Filtering based on keys
d1 = {'a':1,'b':2,'c':3}
d2 = {key:value for key,value in d1.items() if key=='a'}
```

### Sorting a dictionary
```python 
# Sorting a dictionary by key
my_dict = {'1':2,'2':7, '3':7,'4':3}
print(dict(sorted(my_dict.items(), key=lambda item: item[0],reverse=False)))

# Sorting a dictionary by value
print(dict(sorted(my_dict.items(), key=lambda item: item[1],reverse=False)))

# Sorting a dictionary by value then by key
print(dict(sorted(my_dict.items(), key=lambda item: (item[1],item[0]))))
print(dict(sorted(my_dict.items(), key=lambda item: (-item[1],item[0]), reverse=True)))
print(dict(sorted(my_dict.items(), key=lambda item: (-item[1],item[0]), reverse=False)))
```



