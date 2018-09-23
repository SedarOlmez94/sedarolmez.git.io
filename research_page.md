## Research
This page contains all my research projects developed during my PhD at the Alan Turing Institute/University of Leeds Institute of Data Analytics. My past work at King's College London can be found on my [github](https://github.com/SedarOlmez94) and papers including my dissertation at [academia](https://kcl.academia.edu/SedarOlmez).

### Agent Based Model 21/09/2018


I participated in the module titled: __Programming for Social Science: Core Skills GEOG5995M__ at the Leeds Institute for Data Analytics (LIDA) where I developed an agent based model using python with an external library __matplotlib__ and __Atom__ IDE. Two versions of the software was developed a __core__ version and __poacher edition__:


- Core: The core model contains two __.py__ sourcecode files, one is the __Agent__ object (__agentframework.py__) the other __core_code_v1.py__ (main). The model simulates an environment which contains grass (each pixel coloured green) and sheep agents that roam and consume grass, sheep that are within the __neighbourhood__ distance share food. The variables are initialised within the script to unique values:
```
num_of_iterations = 200 # How many iterations should the simulation loop.
num_of_agents = 10 # How many sheep agents should appear.
neighbourhood = 10 # What is the neighbourhood distance for sharing.
```
  The variables above can be changed before run-time to produce different results, but given these variable intialisations, we
  get something like this:


<p align="center">
  <img width="500" height="500" src="simulation_v1.gif">
</p>

- Poacher edition: I decided to add new features to the simulation. I wrote a new script called __core_code_v2.py__ which is the main that uses the same object __agentframework.py__ but this time we have a __poacher__ agent which shoots sheep that are in close proximity to it (I'm definitely against poaching, this was just a fun experiment). The script now takes an extra value (poacher_neighbourhood) and these values are initialised in the terminal to execute the script using the __sys__ library. 
```
num_of_iterations = int(sys.argv[1])
num_of_agents = int(sys.argv[2])
neighbourhood = int(sys.argv[3])
poacher_neighbourhood = int(sys.argv[4]) #The fourth argument, the minimum distance a sheep needs to be to a poacher for it to shoot.
```
The script is executed as such:
![terminal](terminal.png)
(Note: the terminal screenshot was taken before name changes, so the script is actually called core_code_v2.py and not core_code.py, poacher kill range is the poacher_neighbourhood).


The __poacher edition__ is demonstrated below:


<p align="center">
  <img width="500" height="500" src="Poacherexecution.gif">
</p>
