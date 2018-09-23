## Research
This page contains all my research projects developed during my PhD at the Alan Turing Institute/University of Leeds Institute of Data Analytics. My past work at King's College London can be found on my [github](https://github.com/SedarOlmez94) and papers including my dissertation at [academia](https://kcl.academia.edu/SedarOlmez).

### Agent Based Model 21/09/2018


I participated in the module titled: __Programming for Social Science: Core Skills GEOG5995M__ at the Leeds Institute for Data Analytics (LIDA) where I developed an agent based model using python with an external library __matplotlib__ and __Atom__ IDE. Two versions of the software was developed a __core__ version and __poacher edition__:
- Core: The core model contains two __.py__ sourcecode files, one is the __Agent__ object (__agentframework.py__) the other __core_code_v1.py__ (main). The model simulates an environment which contains grass (each pixel coloured green) and sheep agents that roam and consume grass. The variables are initialised within the script to unique values:
```
num_of_iterations = 200
num_of_agents = 10
neighbourhood = 10
```
  The variables above can be changed before run-time to produce different results, but given these variable intialisations, we
  get something like this: 
  ![simulation_v1](simulation_v1.gif)
