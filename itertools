```python

import itertools
list_test = ['hello','there','world']
str_test = 'hellothereworld'

# Iterate over elements within a list
chain = list(itertools.chain(*list_test))
iteratel = ''.join(list(itertools.chain(*list_test)))

# Combinations without replacement
comb_wo_rep = list(itertools.combinations(list_test,2))

# Combinations with replacement
combw_rpl = list(itertools.combinations_with_replacement(list_test,2))
combw_rpl_2 = ['_'.join(x) for x in list(itertools.combinations_with_replacement(list_test,2))]

# Compress list
selectors = [1,0,1]
compress = list(itertools.compress(list_test, selectors))

# Groupby elements within iterator (e.g. characters in string)
groupbytest = list(k for k,g in itertools.groupby(str_test))
tuple_test=(list((k,len(list(g))) for k,g in itertools.groupby(str_test)))
sample = sorted(tuple_test, key = lambda x: x[1],reverse=True)

# Sort list
tuple_test = list([k,len(list(g))] for k,g in itertools.groupby(str_test))
sample = sorted(tuple_test, key = lambda x: x[1],reverse=True)

# Pairwise
pairwise = list(itertools.permutations(list_test))

# Product
product = list(itertools.product(*list_test, 'XY'))

# Repeat
repeat = list(itertools.repeat(list_test, times=3))

```
