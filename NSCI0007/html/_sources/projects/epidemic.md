(viral_epidemics)=
# Viral Epidemics

## Background
 
We can model a population (e.g. a town or city) using a lattice-type arrangement of cells, where each cell is assumed to represent an individual entity, such as an individual or household or residential area. The entities are labelled according to their current state of infection, here taken to be:

|State|Description|
|---|---|
|S|Susceptible|
|E|Exposed and asymptomatically infected|
|I|Infected, but not yet quarantined|
|Q|Quarantined|
|R|Recovered|

Movement restrictions define a local neighbourhood of each entity, within which neighbouring cells are assumed to influence each other. For example, a [Moore neighbourhood](https://en.wikipedia.org/wiki/Moore_neighborhood) consists of a cell and each of its eight immediate surrounding neighbours.
In each time step the cells are updated according to rules governing (for example) the probability of susceptible individuals contracting the virus from infected neighbours, or the likelihood of recovery/quarantine.

## The Project
 
Implement the computational model of the COVID-19 pandemic described in the following paper, and see if you can reproduce some of their results.

https://arxiv.org/pdf/2006.11270.pdf 

The project can be broken down into steps, such as:
1. Define a function that produces a grid of specified size N for different initial “seeding” mechanisms (e.g a single infection/randomised infection/clusters of infection)
2. Construct a function that counts the number of cells of each state in a given neighbourhood (e.g. Moore neighbourhood)
3. Apply update rules to each cell based on the number of neighbouring cells in each state
4. Visualise the cell states – for example by plotting the grid with colour patches or by computing the fraction of cells in each state.

## Notes
 
The steps required to setup the grid and compute the number of neighbours are not too difficult, but the implementation of the update steps is made challenging here due to the time-dependence of some of the phenomena, which will require you to keep track of the duration of time since exposure, infection or quarantine.

It may be helpful to start with a simpler model, such SIR rules described below:
1. If a susceptible is the nearest neighbour of an infected then the susceptible can be infected with a probability $p=0.5$.
2. Infecteds recover and move into the recovered state with a probability $p_r=0.1$. 
3. Recovereds can be returned to the susceptible state with a probability $p_s=0.05$. 

## Extensions
 
Extensions of this project could involve imposing more sophisticated update rules, such as rules where the probabilities depend on risk factors of the entities, such as age and gender. For example, see:

https://www.mdpi.com/2227-9717/9/1/55/htm 

One limitation of the model is that it does not account for the possibility of long distance interactions. An example of a research paper that seeks to address this using a “small world” model can be found at:

https://www.tandfonline.com/doi/full/10.1080/08898481003689486

Such modelling is beyond the scope of what can be accomplished in a short project, but this would be one way to extend the project in future work.
