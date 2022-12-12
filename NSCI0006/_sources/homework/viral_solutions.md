---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.10.3
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Viral trends solutions

## {numref}`ex-vt1`

Use the code given in the homework sheet to import the data :

````{toggle}
```{code}
import pandas as pd
import numpy as np

df = pd.read_csv('data_2022-Aug-17.csv')
df=df.iloc[::-1] #data in reverse order

x=np.array(df['date'])
y=np.array(df['newCasesBySpecimenDate'])

from datetime import date as dt
date=dt.fromisoformat
dt0 = date(x[0])
x=[abs(date(x[i])-dt0).days for i in range(len(x))]
```
````

Isolate a wave "by eye" and find the running total number of cases

```{code}
import matplotlib.pyplot as plt

x=np.array(x[750:850])
y=np.array(y[750:850])

fig, ax = plt.subplots(1, 2,figsize=(8,2))
ax[0].plot(x,y,'o')

#subtracting baseline number of cases
Y = np.cumsum(y-min(y))
ax[1].plot(x,Y,'o')
plt.show()
```

```{image} imgs/viral000.png
:alt: baseline-data
:width: 90%
:align: center
```

Define the logistic function

```{code}
def logistic_fun(x,K,x0,s):
  return K/(1+np.exp(-(x-x0)/s))
```

`````{note}
It is possible to fit the function without normalising, but to do this we have to help the optimizer locate the parameter values by providing bounds.

````{toggle}
We can identify suitable parameter bounds by trying out some coefficient values in the logistic function until we get some that look roughly correct:

```{code}
xtest = np.linspace(750,850)
ytest = logistic_fun(xtest,2.5e6,780,10)
plt.plot(xtest,ytest)
plt.show()
```

```{image} imgs/viral001.png
:alt: params-est
:width: 80%
:align: center
```

Provide coefficient bounds that span the indicated values:

```{code}
from scipy.optimize import curve_fit
bds=((1e6,760,1),(5e6,840,100))
params=curve_fit(logistic_fun,x,Y,bounds=bds)[0]
print(params) # these are the values we found

# plot the result :
plt.plot(x,Y,'o')
Y_fit=logistic_fun(x,*params)
plt.plot(x,Y_fit)
plt.show()

```

```{image} imgs/viral002.png
:alt: viral-fit1
:width: 80%
:align: center
```
````
`````

The homework suggested to normalize the data. You could plot the result after the following step, to check correctness:

```{code}
def my_normalize(v):
  a=min(v); b=max(v)
  vhat=(v-a)/(b-a)
  return vhat,a,b

xhat,L,R = my_normalize(x)
Yhat,D,U = my_normalize(Y)
```

Now fit the logistic function. You could plot the result after the following step, to check correctness:

```{code}
from scipy.optimize import curve_fit

params=curve_fit(logistic_fun,xhat,Yhat)[0]
Yhat_fit=logistic_fun(xhat,*params)
```


To  "un-normalise" we perform the reverse of the normalization steps:

```{code}
def un_normalize(vhat,a,b):
  return vhat*(b-a)+a

Yfit = un_normalize(Yhat_fit,D,U)
plt.plot(x,Y,'o')
plt.plot(x,Yfit)
plt.show()
```

```{image} imgs/viral003.png
:alt: viral-fit2
:width: 70%
:align: center
```

Finally, to plot the daily cases we reverse the accumulation step

```{code}
yfit = np.diff(Yfit)+min(y)
plt.plot(x,y,'o')
plt.plot(x[0:-1],yfit)
plt.show()
```

```{image} imgs/viral004.png
:alt: viral-final
:width: 70%
:align: center
```

## {numref}`ex-vt2`

Import the call me maybe data

```{code-cell}
import pandas as pd
import numpy as np
df = pd.read_csv('call-me-maybe.csv')
x=np.array(df['week'])
h=np.array(df['hits'])
y=np.cumsum(h)           #accumulate  

```

`````{note}
Again, we can do the fit without normalising if we tinker with the parameters to establish suitable bounds:

````{toggle}

```{code}
def frechet(x,A,k,s):
  y=A*np.exp(-(x/k)**(-s))
  return y

from scipy.optimize import curve_fit
bds=((1e3,50,2),(1e4,500,10))
params=curve_fit(frechet,x,y,bounds=bds)[0]
print(params)

Yfit = frechet(x,*params)

import matplotlib.pyplot as plt
plt.plot(x,y,'b.')
plt.plot(x,Yfit)
plt.show()

```

```{image} imgs/maybe01.png
:alt: cmm1
:width: 80%
:align: center
```
````
`````

With normalisation:

```{code}
# normalise
xhat=x/len(x)
yhat=y/max(y)

# curve fit
from scipy.optimize import curve_fit
import matplotlib.pyplot as plt

def frechet(x,k,s):
  return np.exp(-(x/k)**(-s))

bds=((0.01,0.01),(1,100))
params=curve_fit(frechet,xhat,yhat,bounds=bds)[0]
print(params)

Yfit = frechet(xhat,*params)

plt.plot(xhat,yhat,'b.')
plt.plot(xhat,Yfit)
plt.show()
```

```{image} imgs/maybe02.png
:alt: cmm2
:width: 70%
:align: center
```

Showing the weekly hits :
```{code}
yfit = np.diff(max(y)*Yfit)
plt.plot(x,h,'b.')
plt.plot(x[0:-1],yfit)
plt.show()
```

```{image} imgs/maybe03.png
:alt: cmm-final
:width: 70%
:align: center
```

The distribution pdf has a similar shape to the data (variance, skeweness) but a lower peak (kurtosis).
