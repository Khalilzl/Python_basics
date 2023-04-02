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

### Lists: Filtering using list comprehenshion
```python
numbers = [70, 60, 80, 90, 50,82,90,91]
filtered_list = [ i for i in numbers if i>= 80]
```

### Lists: Sorting based on tuple positions
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

### Dictionaries: Filtering based on values or keys
```python 
# Filtering based on values
d1 = {'a':1,'b':2,'c':3}
new_dict = {key: value for key, value in d1.items() if value > 1}

# Filtering based on keys
d1 = {'a':1,'b':2,'c':3}
d2 = {key:value for key,value in d1.items() if key=='a'}
```

### Dictionaries: Sorting
```python 
# Sorting a dictionary by key
my_dict = {'1':2,'2':7, '3':7,'4':3}
print(dict(sorted(my_dict.items(), key=lambda item: item[0],reverse=False)))

# Sorting a dictionary by value
print(dict(sorted(my_dict.items(), key=lambda item: item[1],reverse=False)))

# Sorting a dictionary by value then by key
print(dict(sorted(my_dict.items(), key=lambda item: (item[1],item[0]))))
print(dict(sorted(my_dict.items(), key=lambda item: (-item[1],item[0]), reverse=True)))
```

### Lists: transformation using map and lambda
```python
# Make a list of the squares of integers from  to  (both included).
l1 = list(range(10))
l2 =list(map(lambda x: x*2,l1))
l3 = list(map(lambda x:x*x, l1))

print(l1,l2,l3)
```

### Arrays: multiplying vectors
```python
import numpy as np

A = np.array([0, 1])
B = np.array([3, 4])

arr = [A,B]

# Inner or dot product
print(np.inner(A,B))
print (np.dot(A, B))

# Outer product 
print(np.outer(A,B))

# mean/var/std
print(np.mean(arr, axis = 1)) 
print(np.var(arr, axis = 0))
print(round(np.std(arr),11))
```

### Arrays: shape and reshape
```python
my_array = np.array([1,2,3,4,5,6])
my2darray = np.reshape(my_array,(3,2))
```

### Arrays: concatenating array
```python
import numpy as np
array_1 = np.array([[1,2,3],[0,0,0]])
array_2 = np.array([[0,0,0],[7,8,9]])
```

### Pandas: Group by

```python
import pandas as pd

# Read in the CSV file
my_data = pd.DataFrame({'Product':['a','a','b'],
                        'Units Sold':[1,2,0],
                        'Revenue':[2,5,0]})

# Calculate the total number of units sold for each product
units_sold = my_data.groupby("Product",as_index=False)["Units Sold"].sum()
units_sold.columns = ["Product","Total Units Sold"]

# Calculate the total revenue for each product
total_rev = my_data.groupby("Product",as_index=False)["Revenue"].sum()
units_sold.columns = ["Product","Total Revenue"]

# Merge the two DataFrames on the "Product" column
sales_summary = pd.merge(units_sold, total_rev, on="Product")
```

### Pandas: Group by and agg()

```python
import pandas as pd

# Read in the CSV file
my_data = pd.DataFrame({'Product':['a','a','b'],
                        'Units Sold':[1,2,0],
                        'Revenue':[2,5,0]})

# Calculate the total units sold and total revenue for each product
sales_summary = my_data.groupby("Product",as_index=False).\
agg({"Units Sold": "sum", "Revenue": "sum"})
sales_summary.columns = ["Product","Total Units Sold","Total Revenue"]
```
