# Exercises

:::{exercise}
:label: exercise_increase_by_one

Only one of the following cases is possible. For that case, write the function `increase_by_one`. For the other cases, explain why it is not possible to write such a function.

a\.
```
>>> val = 5.0
>>> increase_by_one(val)
>>> print(val)
6.0
```
b\.
```
>>> val = "hello"
>>> increase_by_one(val)
>>> print(val)
hello1
```
c\.
```
>>> val = [0, 0, 0]
>>> increase_by_one(val)
>>> print(val)
[0, 0, 0, 1]
```
d\.
```
>>> val = np.array([0, 0, 0])
>>> increase_by_one(val)
>>> print(val)
[0 0 0 1]
```

:::

:::{exercise} Functions and Mutable Variables

The method `list.reverse()` performs an **in-place** reversal of a list (i.e. it reverses the elements of a list without creating a new list).

```
>>> a = [1, 2, 3, 4, 5]
>>> a.reverse()
>>> print(a)
[5, 4, 3, 2, 1]
```

Write a function `reverse_array(x)` which reverses a Numpy array **in place** (ie without creating a new array).

```
def reverse_array(x):
    # your code here
```

Test your code works as below:

```
>>> import numpy as np
>>> x = np.array([1, 2, 3, 4, 5])
>>> reverse_array(x)
>>> print(x)
[5 4 3 2 1]
```
:::

:::{exercise} Nested Lists

A nested list is a list whose elements are also list. For example,

```
x = [[1, 2], [3, 4], [5, 6, 7]]
```

1\. What is the type and value of each of the following expressions?

a. `x[2]`
b. `x[0][1]`

Lists are mutable, which can have some rather surprising consequences when they are nested inside each other.

2\. What is the value of `x` and `y` after executing the following code? Explain why.

a\.
```
x = [1, 2, 3]
y = [x, x]
x.append(4)
```

b\.
```
x = [1, 2]
y = []
for i in range(5):
    y.append(x)
x[0] = 100
```

c\.

```
x = [1]
for z in x:
    x.append(z)
```

d\.
```
x = []
y = []
x.append(y)
y.append(x)
```

3\. Write a function which *flattens* a list-of-lists. That is, given the array
```
[[1, 2, 3], [4, 5, 6], [7], [8, 9]]
```
your function should return
```
[1, 2, 3, 4, 5, 6, 7, 8, 9]
```
:::

:::{exercise}

Write a function which transposes a list of list. That is, if 

```
[[1, 2, 3, 4, 5],
 [2, 3, 4, 5, 6],
 [3, 4, 5, 6, 7]]
```

Then your function should return

```
[[1, 2, 3],
 [2, 3, 4],
 [3, 4, 5],
 [4, 5, 6],
 [5, 6, 7]]
```

[There are many ways to do this. You should try to find a solution that uses only loops and lists.]
:::
