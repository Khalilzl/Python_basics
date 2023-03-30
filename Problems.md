### Given a list of dictionaries, return the dictionary with the largest value for a given key. If there are repetitions, return any of them.

```python
# Dictionaries d1 and d2
d1 = {'a':1,'b':2,'c':3}
d2 = {'s':1,'f':2,'w':3}
my_list = [d1,d2]

max_dict = []

# keep track of index and iterate over the list
for i,c in enumerate(my_list):
  # Append the index as the maximum of the values of each dictionary
  max_dict.append([i,max(c.values())])

# Return the first dictionary with the maximum
chosen_dict = sorted(max_dict, key = lambda tup: tup[1])[0]
my_list[chosen_dict[0]]
```

### Given a list of numbers, return a new list where each number is the sum of its digits

```python
list_of_n = [1,42,53,31]
new_list = []

for i,digits in enumerate(list_of_n):
  sum = 0
  for t in str(digits):
    sum = sum + int(t)
  new_list.append(sum)
```

### Using enumerate and zip, find the longest common prefix among a list of strings
The * character : when it appears behind an iterable object, what it does is passing the items inside the iterable to the function's caller one by one.
The zip function accepts a list of iterables in order to return their aligned columns
So, zip(*input) passes all the items inside the input as arguments to zip function, which then gives the iterables in order of the columns.

```python
input = ["apple", "ape", "apricot"]
init_stri = ''

# Loop over each item characters together
for i, chars in enumerate(zip(*input)):
  # If it's the same character, then append it
  if(len(set(chars))==1):
    init_stri= init_stri + chars[0]
print(init_stri)
```

### Count consecutive sequence characters in a string
```python
import itertools
mystring = 'hhheleee'

mylist = []
for k,g in itertools.groupby(mystring):
  mylist.append((k,len(list(g))))
print(mylist)
```


