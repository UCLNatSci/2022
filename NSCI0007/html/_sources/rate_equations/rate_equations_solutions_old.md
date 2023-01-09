# Solutions



:::{solution} exercise_2_7

First we need to extend the for loop from above. To get $x_{16}$ we will need to calculate 17 terms of the sequence - remember that the first term is $x_0$.

```{code-block} python
x = np.zeros(17)

x[0] = 10

for i in range(16):
    x[i+1] = x[i] + 0.1*x[i] 
    
print("x[16]:", x[16]) 
```

:::

:::{solution} exercise_2_8

```
x = np.zeros(20)
x[0] = 10

# create array y and set initial value
y = np.zeros(20)
y[0] = 10

for i in range(19):
    x[i+1] = x[i] - 0.5 * y[i]  

    # set value of y[i+1]
    y[i+1] = y[i] + 0.4 * x[i]

plt.figure(figsize=(3,3))
plt.plot(x)

# plot y on the SAME graph
plt.plot(y)
```
:::

:::{solution} exercise_2_9
- $I_0 = 1000$
- $I_1 = I_0 - 0.1*I_0 = 1000 - 100 = 900$
- $I_2 = I_1 - 0.1*I_1 = 900 - 90 = 810$
- $I_3 = I_2 - 0.1*I_2 = 810 - 81 = 729$
and so on...

By adapting the code from above, we get:
```
n_days = 100

I = np.zeros(n_days)

I[0] = 1000

for i in range(n_days - 1):
    I[i+1] = I[i] - 0.1 * I[i]

plt.figure(figsize=(5,5))
plt.plot(I)
plt.xlabel("Time (days)")
plt.ylabel("Infected population")
```
:::

:::{solution} exercise_2_10

```
# set up variables and arrays
n_days = 100
a = 0.1
b = 0.00005
S = np.zeros(n_days)
I = np.zeros(n_days)

# initialise the variables
S[0] = 20000
I[0] = 100

# implement equations
for i in range(n_days - 1):
    S[i+1] = S[i] - (b * S[i] * I[i])
    I[i+1] = I[i] + (b * S[i] * I[i]) - (a * I[i])

plt.figure(figsize=(5,5))
plt.plot(I)
plt.plot(S)
plt.xlabel("Time (days)")
plt.ylabel("Population")
```
:::

:::{solution} exercise_2_11

By using a for loop and a numpy array we can try lots of different values of b.
Let's try starting with a larger value, and then halve the value a few times
```
for i in range(5):
    # set up variables and arrays
    n_days = 100
    a = 0.1
    b = 0.0001/(2**i)
    S = np.zeros(n_days)
    I = np.zeros(n_days)

    # initialise the variables
    S[0] = 20000
    I[0] = 100

    # implement equations
    for i in range(n_days - 1):
        S[i+1] = S[i] - (b * S[i] * I[i])
        I[i+1] = I[i] + (b * S[i] * I[i]) - (a * I[i])

    plt.figure(figsize=(5,5))
    plt.plot(I)
    plt.plot(S)
    plt.xlabel("Time (days)")
    plt.ylabel("Population")
    plt.title(b) # add title so we know what value we are currently looking at
```
We can see in the first graph that the infection peaks a lot earlier - after about 5 days. Notice that there is a small oscillation to a negative susceptible population size, before stabilising - this is because the program doesn't know that population size can't be negative (the model doesn't reflect this either!). We could adapt the code to reflect this, if we wanted to. 

At $b = 2.5e-05$ the infection peaks at around $10,000$ people. Halving again, we see a peak at $5,000$, but there are never more infected people that susceptible. In the final graph, when $b = 6.25e-06$ the number of infected people never peaks - there is no epidemic. So the minimum value of $b$ that results in an epidemic lies somewhere in the interval $(6.25e-06, 1.25e-05) = (0.00000625, 0.0000125)$.

To estimate the minimum value that results in an epidemic, let's use `np.linspace` to test some values in that interval.

```
for b in np.linspace(0.00000625, 0.0000125, 10):
    # set up variables and arrays
    n_days = 100
    a = 0.1
    S = np.zeros(n_days)
    I = np.zeros(n_days)

    # initialise the variables
    S[0] = 20000
    I[0] = 100

    # implement equations
    for i in range(n_days - 1):
        S[i+1] = S[i] - (b * S[i] * I[i])
        I[i+1] = I[i] + (b * S[i] * I[i]) - (a * I[i])

    plt.figure(figsize=(5,5))
    plt.plot(I)
    plt.plot(S)
    plt.xlabel("Time (days)")
    plt.ylabel("Population")
    plt.title(b) # add title so we know what value we are currently looking at
```
Examining the graphs, the second graph doesn't seem to have a peak, but the third graph arguably has a *tiny* peak. We can go back to python to find out what these values are.

```
print('The minimum value of b that results in an epidemic lies in the interval (', np.linspace(0.00000625, 0.0000125, 10)[1], ', ', np.linspace(0.00000625, 0.0000125, 10)[2], ').')
```
:::