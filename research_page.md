## Research
This page contains all my research projects developed during my PhD at the Alan Turing Institute/University of Leeds Institute for Data Analytics. My past work at King's College London can be found on my [github](https://github.com/SedarOlmez94) and papers including my dissertation at [academia](https://kcl.academia.edu/SedarOlmez).

### Agent Based Model 21/09/2018


[__Click here for repository__](https://github.com/SedarOlmez94/programming_for_social_sciences/tree/working_copy)


I participated in the module titled: __Programming for Social Science: Core Skills GEOG5995M__ at the Leeds Institute for Data Analytics (LIDA) where I developed an agent based model using python with an external library __matplotlib__ and __Atom__ IDE. Two versions of the software was developed a __core__ version and __poacher edition__:


- Core: The core model contains two __.py__ source code files, one is the __Agent__ object (__agentframework.py__) the other __core_code_v1.py__ (main). The model simulates an environment which contains grass (each pixel coloured green) and sheep agents that roam and consume grass, sheep that are within the __neighbourhood__ distance share food. The variables are initialised within the script to unique values:
```
num_of_iterations = 200 # How many iterations should the simulation loop.
num_of_agents = 10 # How many sheep agents should appear.
Neighbourhood = 10 # What is the neighbourhood distance for sharing.
```
  The variables above can be changed before run-time to produce different results, but given these variable initialisations, we
  Get something like this:


<p align="center">
  <img width="500" height="500" src="simulation_v1.gif">
</p>

- Poacher edition: I decided to add new features to the simulation. I wrote a new script called __core_code_v2.py__ which is the main that uses the same object __agentframework.py__ but this time we have a __poacher__ agent which shoots sheep that are in close proximity to it (I'm definitely against poaching, this was just a fun experiment). The script now takes an extra value (poacher_neighbourhood) and these values are initialised in the terminal to execute the script using the __sys__ library. 
```
num_of_iterations = int(sys.argv[1])
num_of_agents = int(sys.argv[2])
Neighbourhood = int(sys.argv[3])
Poacher_neighbourhood = int(sys.argv[4]) #The fourth argument, the minimum distance a sheep needs to be to a poacher for it to shoot.
```
The script is executed as such:
![terminal](terminal.png)
(Note: the terminal screenshot was taken before name changes, so the script is actually called core_code_v2.py and not core_code.py, poacher kill range is the poacher_neighbourhood).


The __poacher edition__ is demonstrated below:


<p align="center">
  <img width="600" height="600" src="Poacherexecution.gif">
</p>


### Linear regression with gradient descent 13/11/2018


[__Click here for repository__](https://github.com/SedarOlmez94/coursework_2_LIDA)


The second piece of coursework for the module __Programming for Social Science: Core Skills GEOG5995M__ required us to develop our own software model which had to:

- Read in some data.
- Process it in some way.
- Display the results.
- Write the results to a file.

My software model was developed in Python but written in Jupyter Notebook so all the results are available in the notebook .ipynb file. To execute the script, you must first:
```
1. Change directory to the same directory as Linear regression.ipynb
2. Type the command: jupyter notebook "Linear regression.ipynb"
```

Here are the important links:
- [Linear Regression.ipynb](https://github.com/SedarOlmez94/coursework_2_LIDA/blob/master/Linear%20regression.ipynb)
- [PDF report](https://github.com/SedarOlmez94/coursework_2_LIDA/blob/master/simple-linear-regression.pdf)
- [UML use case diagram](https://github.com/SedarOlmez94/coursework_2_LIDA/blob/master/UML%20usecase%20diagram.png)

The libraries used in my project are as follows:
<p align="center">
  <img height="200" width="400" src="libraries.png">
</p>


### Data Modelling of Global Bike Sharing 09/02/2019


[__Click here for repository__](https://github.com/Urban-Analytics/SmartSocialCity/tree/master/Machine%20Learning/Bike%20Sharing%20Project)

The libraries required to execute the `data_modelling_bike_sharing_global.ipynb` script are:
```
1. matplotlib
2. numpy
3. scikit
4. IPython
5. seaborn
6. pandas
7. zlib
```

The `data_modelling_bike_sharing_global.ipynb` notebook file can be executed in a conda environment, to create one read the guide here [Virtual Environment](https://uoa-eresearch.github.io/eresearch-cookbook/recipe/2014/11/20/conda/).

The Jupyter notebook can be found here: [notebook](https://github.com/Urban-Analytics/SmartSocialCity/blob/master/Machine%20Learning/Bike%20Sharing%20Project/data_modelling_bike_sharing_global.ipynb)

A static HTML version can be found here: [html notebook](https://github.com/Urban-Analytics/SmartSocialCity/blob/master/Machine%20Learning/Bike%20Sharing%20Project/data_modelling_bike_sharing_global.html)

The code has been fully commented and documented for reference. 

### N20 crop growth data analysis using machine learning methods 26/03/2019


[![Azure Notebooks](https://notebooks.azure.com/launch.svg)](https://notebooks.azure.com/solmez/projects/n20-data-analysis)(Note, you must have an Azure Notebook account, the reason I had to use cloud computing was due to the size of the dataset.)


The libraries required to execute the `N20_DATA_ANALYSIS.ipynb` script are already installed on the Azure cluster used to host the notebook via `requirements.txt`


I was provided with a complex dataset containing information about crop growth, I developed some machine learning methods to analyse the specific dataset and gain some insights as to how N20 is effected by various elments captured.


### Modelling the supply and demand of UK Police Forces, an Agent Based Modelling approach 03/04/2019


(Note, this project is ongoing. All information regarding the project can be found on its website: [Turing page](https://www.turing.ac.uk/research/research-projects/computational-models-police-demand-dynamics))


To execute the model, you must 
- Install `Netlogo` version `6.0.4`, you can install it here: [Netlogo](https://ccl.northwestern.edu/netlogo/download.shtml).
- Download the map dataset: [dataset](https://github.com/SedarOlmez94/police_simulation_project-PSP-/tree/master/project/data)


1) The algorithm developed (Pseudocode):
```
calculate T for all forces
crime occurs somewhere CRIME_LOCATION

1- create list M (array) with all resources with time-to-mobilise <= resources_requirement_cycles
2- delete from M all forces where not(minimise_impact) = 0 (no resources of resource to be used i.e. A in this case)

3- loop untill units_required = 0 or resources_requirement_cycles = 0:

4- 	find in M resource with min(time-to-mobilise) "smallest time to mobilise" AND max(M(not(minimise_impact))) = 1A "maximum 
5-  value of the resource which is not the one to minimise_impact on stored in M" 

6- 	(new list object) X = [1A] (add "1A to X")

7- 	if for all resources in X there exists a time-to-mobilise = 0 then subtract 
8- 		resource with time-to-mobilise = 0 from units_required
	
9- 	if units_required <= 0 then [print "crime prevented"
10- 	print names of all forces resources pulled and amount of resources pulled. BREAK]

11- 	subtract 1 from all resources time-to-mobilise in X

12- 	M = M - 1A remove the force added to X from the list M.
```


2) A run of the system:
