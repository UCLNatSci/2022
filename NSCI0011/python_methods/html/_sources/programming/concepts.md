# Concepts

## State

## Variables

In programming, a variable is a value identified by a name. Up to now you've probably been conceptualising a variable as a "labelled box" where the contents of the box is the value of the variable, and the label on the box is the name of the variable.

[picture]

We use the **assignment operator** `=` to create a new variable (labelled box) and set its value (put something in the box):

```
x = 3
```

We can later change the value of a variable (replace the contents of the box) using the assignment operator:

```
x = 4
```

In this section we'll see why this picture is slightly misleading and insufficient to understand how variables actually behave in Python. To illustrate this, consider the **equality operator** `==`. The equality operator evaluates to `True` if the expressions on either side are equal.

```
x = 3
y = 3
z = 4

x == y
x == z
```


Value
Type
Identity

Equality of variables

