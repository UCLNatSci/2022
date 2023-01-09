(neurosphere_growth)=
# Neurosphere Growth 

## Background 

We can model a tissue area using a lattice-type arrangement of cells, where each cell represents an individual biological cell (whether it is a stem (S), progenitor (P) or dead (D) cell). Within the lattice, the different cell types can be labelled with different colours/numbers.  

The neurosphere grows through cell division of the initial cells. In each time step, the cells are updated according to the rules governing the probability that a given cell will undergo mitosis and what daughter cells are produced as a result. This probability is defined by a cell’s neighbours (e.g. its four immediate surrounding neighbours, excluding diagonals, in the case of a [von Neumann neighbourhood](https://en.wikipedia.org/wiki/https://en.wikipedia.org/wiki/Von_Neumann_neighborhood)).

## The Project 

In this project you will investigate a model of neurosphere growth, clonal cell clusters made up of neural stem and progenitor cells that drive parts of brain development. It is a poorly understood biological mechanism at present but which can be nicely simulated using cellular automata. This kind of model has widely reaching applications, with its use in modelling any type of tissue growth.  

Implement the computational model of the neurosphere growth as described in the following paper and try to replicate some of their results: 

https://www.sciencedirect.com/science/article/pii/S0022519318300857  

The update rules can be visualised using the [flowchart included in the paper](https://ars.els-cdn.com/content/image/1-s2.0-S0022519318300857-gr1.jpg). The relevant probabilities and other starting values can be found within the text.

Following this diagram, the project can be broken down into a few steps: 

1. Define an initial grid of size N depending on how big an area you want to model. 
2. Construct a function that counts the number of neighbours following the von Neumann neighbourhood. 
3. Apply update rules to each cell based on number of neighbours and therefore mitosis probability depending on initial cell type (see flowchart). 
4. Visualise the updated cell states, for example by plotting the grid with colour patches for the different cell types. 

## Notes

The steps required to setup the grid and compute the number of neighbours are not too difficult, but the implementation of the update steps is made challenging here due to the time-dependence of some of the phenomena.

The flowchart may look complicated however you can start with a simpler model by setting fixed probabilities on a small grid and testing for one iteration. It may be helpful to start with a simpler model incorporating only Projenator (P) and Dead (D) cells. Starting with a single Projenator cell:
1. If a projenator has fewer than 4 neighbours then it undergoes mitosis (cell division) with probability $p_\mathrm{mit}$.
2. The resulting new cell goes in one of the empty neighbouring cells.
3. The projenator cell dies with probability $p_\mathrm{death}$.

## Extensions 

An extension to the project might involve the presence of cancerous cells in the growth of the neurospheres. Depending on the initial grid, you could look at how a cancerous cell might successfully or fail to invade the tissue area. (Cite paper) 