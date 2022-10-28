# (Einstein) Index Notation

Vector quantities can also be expressed in index notation, which makes use of two quantities $\delta_{ij},\, \epsilon_{ijk}$, which in three dimensions follow the following rules:
```{math}
\delta_{ij} &= 
  \begin{cases}
                                   0 & i \neq j \\
                                   1 & i = j = 1,\,2,\,3
  \end{cases}\\
  \epsilon_{ijk} &=  
  \begin{cases}
                                   1 & i,\,j,\,k = 123,\, 231,\, 312 \\
                                   -1 & i,\,j,\,k = 132,\, 213,\, 321 \\
                                   0 & i=j\,\, \text{or}\,\,\ i=k \,\,\text{or}\,\, j=k
  \end{cases}
```
where we notice that $\epsilon_{ijk}$ has both a cyclic and anti-cyclic set of values.  In each case we are expressing the $(x,\,y,\,z)$ components using the 
$(1,\,2,\,3)$ notation.  In higher dimensions this can be extended also! 

### Dot Product
We can express a dot product using the $\delta_{ij}$ symbol
```{math}
{\bf A} \cdot {\bf B} = \delta_{ij}\,A_i\,B_j = A_1\,B_1 + A_2\,B_2 + A_3\,B_3 
```
For a divergence, we can use the differential vector operator in index notation $\partial_i$:
```{math}
\nabla \cdot {\bf A} = \delta_{ij}\,\partial_i\,A_j = \partial_x\,A_x + \partial_y\,A_y +\partial_z\,A_z 
```

### Cross Product
We can express a cross product using the $\epsilon_{ijk}$ symbol
```{math}
{\bf A} \times {\bf B} &=& ({\bf A}_i \times {\bf B}_j)_k = \epsilon_{ijk}\,A_i\,B_j \\
&=& (A_1\,B_2 - A_2\,B_1)_3 + (A_2\,B_3 - A_3\,B_2)_1 + (A_3\,B_1 - A_1\,B_3)_2 \\
&=& (A_y\,B_z - A_z\,B_y)\hat{ \bf x} - (A_x\,B_z - A_z\,B_x)\hat{ \bf y} + (A_x\,B_y - A_y\,B_x)\hat{ \bf z} \nonumber
```
where we note that the overall expression is a vector and therefore must have a free index attached.  Likewise we can represent a curl using the 
differential vector operator in index notation:
```{math}
\nabla \times {\bf A} = (\nabla_i \times {\bf A}_j)_k =  \epsilon_{ijk}\,\partial_i\,A_j 
```

## $\epsilon-\delta$ Identities
We can use these index notation devices to calculate more easily some vector calculus identities, in order to do so we may consider the index equivalent of the triple product:
```{math}
{\bf A} \times \left({\bf B} \times {\bf C}\right) &=& {\bf A} \times\left(\epsilon_{ijk}\, B_i \, C_j \right)_k = \left[\epsilon_{lkm}\, A_l\,\left(\epsilon_{ijk}\,B_i\,C_j\right)_k\right]_m\\ 
&=& \epsilon_{ijk}\,\epsilon_{lkm}\,A_l\,B_i\,C_j 
```
If we have the product of two $\epsilon$ symbols with a common index, then we can replace these with a combination of $\delta$ symbols:
```{math}
\epsilon_{ijk}\,\epsilon_{lkm} = \epsilon_{ijk}\,\epsilon_{mlk}= \delta_{im}\,\delta_{jl} - \delta_{il}\,\delta_{jm} \label{eqn:epsilondelta}
```
which means our result turns into:
```{math}
\epsilon_{ijk}\,\epsilon_{mlk}\,A_l\,B_i\,C_j &=& \left( \delta_{im}\,\delta_{jl} - \delta_{il}\,\delta_{jm}\right)\,A_l\,B_i\,C_j \\ 
&=& A_j\,B_m\,C_j - A_i\,C_m\,B_i \\ &=& \left({\bf A}\cdot{\bf C} \right){\bf B} - \left({\bf A} \cdot {\bf B}\right){\bf C}
```
which is the required result!

We can make use of these identities to simplify the following vector identity:
```{math}
\nabla \times \left(\nabla \times \mathbf {A} \right) = \nabla (\nabla \cdot \mathbf {A} )-\nabla ^{2}\mathbf {A} 
```
Instead of calculating all of the LHS and RHS's in terms of components and equating them, we can look at the expressions in terms of index notation:
```{math}
\nabla \times (\nabla \times {\bf A}) &=& \epsilon_{ijk}\,\partial_i  \,(\nabla \times {\bf A} )_j \\ 
&=& \epsilon_{ijk}\,\partial_i\, \left(\epsilon_{lmj}\,\partial_l\, A_m\right)_j = \epsilon_{ijk}\,\epsilon_{lmj}\,\partial_i\, \partial_j\,A_m \\ 
&=& \epsilon_{kij}\,\epsilon_{lmj}\,\partial_i\, \partial_j\,A_m =\left(\delta_{kl}\,\delta_{im} - \delta_{km}\,\delta_{il}\right)\,\partial_i\, \partial_j\,A_m \\ 
&=& \partial_k (\partial_i A_i) - (\partial_i \partial_i) A_k \\ &=& \nabla(\nabla\cdot {\bf A}) - \nabla^2 {\bf A}
``` 
which is often known as Lagrange's formula for $\nabla$.

