# Exercises

:::{exercise}

Only one of the following cases is possible. For that case, write the function `increase_by_one`. For the other cases, explain why it is not possible.
```
val = 5.0
increase_by_one(val)
print(val)
```
```
6.0
```

```
val = "hello"
increase_by_one(val)
print(val)
```
```
'hello1'
```

```
val = [0, 0, 0]
increase_by_one(val)
print(val)
```
```
[0, 0, 0, 1]
```

```
val = np.array([0, 0, 0])
increase_by_one(val)
print(val)
```
```
[0 0 0 1]
```

:::

:::{exercise} Object References and Lists

5 students (numbered 0 to 4) are studying 4 modules (numbered 0 to 3):

 - Student 0 is studying Module 0 and Module 2;
 - Student 1 is studying Module 1 and 2;
 - Student 2 is studying Module 3;
 - Student 3 is studying all modules;
 - Student 4 isn't studying any of the modules.

 This information is stored in a list-of-lists `u` where `u[i]` is a list of the modules taken by student `i`.

 1\. Write a Python program which generates a new list-of-lists `v` where `v[i]` is a list of students taking module `i`.

```
n_students = 5
n_modules = 4
u = [[0, 2],
     [1, 2],
     [3],
     [0, 1, 2, 3],
     []]

# your code here

print(v)
```
```
[[0, 3], [1, 3], [0, 1, 3], [2, 3]]
```

2\. Now, write a function `transpose_list(x)` which does the same. Your function should work for arguments `x` with any number of students and modules.

```
def transpose_list(x):
    # your code here

u = [[0, 2],
     [1, 2],
     [3],
     [0, 1, 2, 3],
     []]
v = transpose_list(u)
print(v)
```
```
[[0, 3], [1, 3], [0, 1, 3], [2, 3]]
```

:::

:::{exercise} Functions and Mutable Variables

The method `list.reverse()` performs an **in-place** reversal of a list (i.e. it reverses the elements of a list without creating a new list).

```
a = [1, 2, 3, 4, 5]
a.reverse()
print(a)
```
```
[5, 4, 3, 2, 1]
```

Write a function `reverse_array(x)` which reverses a Numpy array **in place** (ie without creating a new array).

```
def reverse_array(x):
    # your code here
```

Test your code works as below:

```
import numpy as np
x = np.array([1, 2, 3, 4, 5])
reverse_array(x)
print(x)
```
```
[5 4 3 2 1]
```
:::
