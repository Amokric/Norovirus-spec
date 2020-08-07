# REQ-purpose
The goal of this project is to develop a reasonable replication of the Norovirus Model from the paper: Norovirus outbreaks: using agent-based modelling to evaluate school policies.

Here is the link to the paper - [Norovirus Paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7822182).



## Purpose of this project

* The primary purpose of this project is to reproduce the Norovirus model so that it allows for the simulated transmission of Norovirus among six primary school classrooms containing 21 students.

* The secondary purpose of this project is to implement the mitigation strategies described within the publication into the replicated model to produce results that can then be compared to the original results. These interventions that are set should limit the number of students who get infected.


## Goals of this project

To produce three data sets that can be compared to the original data within the publication to perform an analysis of similarities between the replicated model and the original.


## Structure
  

- [[REQ-model]] - The requirements for the model setup. This contains the steps towards initialising each conceptual unit as listed below:
   - [[SPC-model_background]] 
   - [[SPC-model_agents]]
   - [[SPC-model_network]]
   - [[SPC-model_disease]]

- [[REQ-output]] - The model output, the results required to evaluate the replicated models results and then compare with the results from the paper.