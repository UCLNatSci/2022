# Propositional Logic

We can turn out statements about set theory into statements about propositions, in the classical logic sense of TRUE and FALSE - so called 
<b>Propositional Logic</b>.  If you're interested in areas of logic where some of these ideas are challened, have a look at 
[<b>The Logic of Quantum Mechanics, by Birkhoff & Von Neumann</b>](https://doi.org/10.2307/1968621).

A propositional or statement is a declaration that is either <b>TRUE (T)</b> or <b>FALSE (F)</b> but not both.  Some propositions are <b>composite</b> or 
<b>compound</b> - i.e. composed of sub-propositions and then are connected in different ways.  Others are primitive or unitary, i.e. cannot be broken down in to 
simpler propositions.  One way to present and calculate the outcomes of compound statements is to use a <truth table</b> - these might look familiar from computer science, 
where the associated algebra is known as <em>Boolean algebra</em> and the T/F is replaced with 1/0.  

Our ideas from set theory can be very easily applied in this area, using the algebra of basic logic:
- <b>Conjunction</b> 

$p \wedge q$: Any two propositions can be combined by the word "AND" to form a compound proposition, known as a conjunction.  The overall truth value of $p \wedge q$ 
depends on the truth values of $p$ and $q$, according to the truth table below:

|$p$| $q$ | $p \wedge q$ |
|---|---|---|
| T | T | T |
| T | F | F |
| F | T | F |
| F | F | F |


- <b>Disjunction</b>

$p \vee q$: Any two propositions can be combined by the word "OR" to form a compound proposition known as a disjunction.  The overall truth value of 
$p \vee q$ depends on the truth values of $p$ and $q$, according to the truth table below:  

|$p$ | $q$ | $p \vee q$ |
|---|---|---|
| T | T | T |
| T | F | T |
| F | T | T |
| F | F | F |


- <b>Negation</b> 

$\neg p$: Given any proposition $p$, we can formed another proposition called the negation of $p$, which can be formed by writing a "NOT" right before it or 
saying "it is false that".  The overall truth value of $\neg p $ depends on the truth value of $p$, according to the truth table below:

|$p$ | $\neg p$  |
|---| ---|
| T | F |
| F | T |

- <b>Order of Precedence</b> 

In order to avoid a lot of parentheses when writing down logical connectives, there is a preferred order of precedence.  
```{math}
\neg \,\text{has precedence over} \,\wedge\, \text{which has precedence over}\, \vee 
```
We can think of this as analogous to <b>BIDMAS</b> on numbers:
- Brackets, 
- Indices, 
- Division/Multiplication, 
- Addition/Subtraction 

An example would be $\neg p \wedge q$ means $(\neg p) \wedge q$ and NOT $\neg(p \wedge q)$ which we can see from the truth table are different:

|$p$ | $q$ | $p \wedge q$ | $\neg p$ | $\neg p \wedge q$ | $\neg (p \wedge q)$ |
|---|---|---|---|---|---|
| T | T | T | F | F | F |
| T | F | F | F | F | T |
| F | T | F | T | T | T |
| F | F | F | T | F | T |


We can use these ideas to outline and differentiate logical ideas, such as those of <b>Contradiction</b> and <b>Tautology</b>. A contraction is a proposition that is always 
false, e.g. it is raining and it isn't raining, we can see this as a truth table that ends with all F's.  Equally a tautology is a proposition that is always true, 
e.g. it is raining or isn't raining, we can see this as a truth table that ends with all T's.  We can see these shown below:

|$p$ | $\neg p$ | $p \wedge \neg p$ | $p \vee \neg p$ |
|---|---|---|---|
| T | F | F | T |
| F | T | F | T |


## Laws of the Algebra of Propositions
There are identity laws, i.e. using AND or OR like multiplying or adding on 1 or 0:
```{math}
p \vee F &= p \\
p \wedge F &= F \\
p \wedge T &= p \\
p \vee T &= T
```
Associative laws, i.e. does the position of the brackets matter:
```{math}
(p \vee q) \vee r &=  p \vee (q \vee r)\\
(p \wedge q) \wedge r &=  p \wedge (q \wedge r)
```
Commutative laws, i.e. does the order of operations matter:
```{math}
p \vee q &= q \vee p \\
p \wedge q &= q \wedge p
```
Distributive laws, i.e. does the operation in a bracket expand out:
```{math}
p \vee (q \wedge r) &= (p\vee q) \wedge (p \wedge r)\\
p \wedge (q \vee r) &= (p\wedge q) \vee (p \wedge r)
```
Involution laws, i.e. is the inverse of the inverse return to the original state:
```{math}
\neg(\neg p) = p
```
Idempotent laws, i.e. it's everything or nothing:
```{math}
p \vee p &= p \\
p \wedge p &= p
```
Complement laws, i.e. does everything add up together or subtract to zero:
```{math}
p \vee \neg p &= T \\
p \wedge \neg p &= F \\
\neg T &= F \\
\neg F &= T
```
And finally DeMorgan's laws, which refer to overall inverse relations:
```{math}
\neg(p \vee q) &= \neg p \wedge \neg q \\
\neg(p \wedge q) &= \neg p \vee \neg q
```
which we see mirrors the algebra of sets.

## Conditional and Biconditional Statements
Many statements in mathematics and elsewhere are of the form if a proposition $p$ (called the antecedent) applies then a proposition 
$q$ (called the consequent) follows, these are known as <b>Conditional</b> statements and are denoted:
```{math}
p \rightarrow q
```
which is read $p$ <b>Implies</b> $q$ or $p$ <b>only if</b> $q$.  The truth table is defined as:

|$p$ | $q$ | $p \rightarrow q$ |
|---|---|---| 
| T | T | T |
| F | F | T |
| T | F | F |
| F | T | T |

We note that the conditional $p \rightarrow q$ is only false when $p = T$ and $q = F$. 

Another common statement is of the form proposition $p$ applies <b>if and only if</b> proposition $q$ applies, these are known as <b>Biconditional</b> statements 
and are denoted:
```{math}
p \longleftrightarrow q
```
The truth table is defined as:
|$p$ | $q$ | $p \longleftrightarrow q$ |
|---|---|---|
| T | T | T |
| F | F | T |
| T | F | F |
| F | T | F |

We note that the conditional $p \longleftrightarrow q$ is true when $p$ and $q$ have the same truth values and false otherwise. 

What is also interesting here is that $p \rightarrow q$ is composite, it can be constructed from primitive propositions:

|$p$ | $q$ | $\neg p$ | $\neg p \vee q$ | $p \rightarrow q$|
|---|---|---|---|---|
| T | T | F | T | T |
| F | F | T | T | T |
| T | F | F | F | F |
| F | T | T | T | T |

and therefore we see the equivalence between the two propositions:

```{math}
p \rightarrow q \equiv \neg p \vee q
```

## Arguments and Fallacies
A logical argument is a situation where there are given set of propositions $\{P_1,\,P_2,\,\dots P_n\}$ called <b>Premises</b> have that as a consequence 
(or yield) a proposition $Q$ known as a <b>Conclusion</b>, we denote this:
```{math}
\{P_1,\,P_2,\,\dots P_n \}\vdash Q
```
An argument $\{P_1,\,P_2,\,\dots P_n\} \vdash Q$ is said to be valid if $Q$ is true whenever all the premises $\{P_1,\,P_2,\,\dots P_n\}$ are true 
but otherwise it is false.  An argument that is not true is known as a <b>fallacy</b>.

We can consider some simple arguments and their validity:
- $\{p,\,p \rightarrow q\} \vdash q$

We should consider the truth table for all the premises and see if they can be simultaneously true:

|$p$ | $q$ | $p \rightarrow q$ |
|---|---|---|
| T | T | T |
| T | F | F |
| F | T | T |
| F | F | T |

Since in the first line the case of the two premises $\{p,\,p\rightarrow q\}$ being simultaneously true results in $q$ true, this argument is valid.
    
- $\{p \rightarrow q,\,q\} \vdash p$

We should consider the truth table for all the premises and see if they can be simultaneously true:

|$p$ | $q$ | $p \rightarrow q$ |
|---|---|---|
| T | T | T |
| T | F | F |
| F | T | T |
| F | F | T |


Since in the first line the case of the two premises being simultaneously true results in $p$ being true and in the third line the case of the two premises being 
true results in $p$ being false, this argument is false.

Another example of this would be:

```{math}
\{q,\, p \longleftrightarrow q\} \vdash q
```

Examining the truth table here:

|$p$ | $q$ | $p \longleftrightarrow q$ |
|---|---|---|
| T | T | T |
| T | F | F |
| F | T | F |
| F | F | T |

Thus from line 1, all the premises are true results in $p$ true and there are no other times when all the premises are true, thus this argument is true.

## Logical Implications
A proposition $P(p,\,q,\,\dots)$ is said to <b>Logically Imply</b> a proposition $Q(p,\,q,\,\dots)$ if $Q(p,\,q,\,\dots)$ is true whenever $P(p,\,q,\,\dots)$ is 
true.  We denote this as:
```{math}
P(p,\,q,\,\dots) \Rightarrow Q(p,\,q,\,\dots) 
```
This is distinct from a logical argument, because we are only interested in statements being true (whereas in logical arguments a false statement can invalidate them).

We can consider the truth table:

- $p \Rightarrow p \vee q$

|$p$ | $q$ | $p \vee q$ |
|---|---|---|
| T | T | T | 
| T | F | T | 
| F | T | T |
| F | F | F |

Since in the first two rows $p \vee q$ is true whenever $p$ is true, thus $p \Rightarrow p \vee q$ and the implication is true.

- $p \Rightarrow \neg p \wedge \neg q$.

|$p$ | $\neg p$ | $q$ | $\neg q$ | $\neg p \wedge \neg q$ |
|---|---|---|---|---|
| T | F | T | F | F |
| T | F | F | T | F | 
| F | T | T | F | F |
| F | T | F | T | T |

Since in the first two rows $p$ is true, but $\neg p \wedge \neg q$ is false, thus this implication is false.

- $\left(p,\, q\right)  \Rightarrow (p \wedge q,\, p \vee q)$.

|$p$ | $q$ | $p \wedge q$ | $p \vee q$ |
|---|---|---|---|
| T | T | T | T |
| T | F | F | T |
| F | T | F | T |
| F | F | F | F |

Since in the first row $p \wedge q$ and $p \vee q$ are both true and also $p$ and $q$ are all true, thus this implication is true.