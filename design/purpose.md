# REQ-purpose
The goal of this project is to develop a reasonable replication of the Norovirus Model from the paper [NOROVIRUS OUTBREAKS: USING AGENT-BASED MODELING TO EVALUATE SCHOOL POLICIES](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7822182).


The model should focus on the transmission of a virus among primary school classrooms and seeing how the number of children infected can be reduced.  

The daily activities of the students are looked at and how these activities allow for students’ exposure to the virus including classroom activities and lunch. 

The last step of developing the model will include implementing mitigation strategies. This will be done by creating two policies which would limit the amount of student-student interaction. The sooner the policy is implemented the shorter the duration of the outbreak.

## ABM Model
It is important to understand 2hen developing an ABM, there are three main elements :
1. A set of agents: For this case, the set of agents will represent the students. 
2. A set of agent relationships and methods of interaction: the relationships between the students and their friends and neighbours. 
3. Agents’ environment: for this papers case as the agents do not move, but their envionment can be seen as their location attribute being in school. 

It is important to remember that for this model, the students only have the chance of getting infected whilst they are at school, so if it is the weekend then there is no risk of exposure.


## Goal

The model should simulate 6 classrooms, containing 21 students per class and then evaluate the chances of infection depending on if the students are next to their neighbours, doing group work or having lunch with friends.  


## Structure
  

- [[ REQ-model]] - The model setup. This will initialise the model with all the details needed to run the simulation, it will include the generation of the students and the network, which allow for the chance of infection to be evaluated between the students.
- [[ REQ-engine]] - The model will need certain conditions to be executed.
- [[ REQ-output]] - The model output, the results required to evaluate the replicated models results and then compare with the results from the paper.
