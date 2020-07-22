# REQ-purpose
The goal of this project is to develop a reasonable replication of the Norovirus Model from the paper [NOROVIRUS OUTBREAKS: USING AGENT-BASED MODELING TO EVALUATE SCHOOL POLICIES](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7822182).

The paper examines the transmission of the virus among primary school classrooms, evaluating policies to reduce the number of children who become infected. It focuses on the daily activities that allow for students’ exposure to the virus including classroom activities and lunch. 

To control the transmission, two policies were implemented to limit the amount of student-student interaction. The results demonstrated that implementation of either policy helps reduce the number of students who become ill and that the sooner the policy is implemented the shorter the duration of the outbreak.


## Goal

The model shall simulate the spread of norovirus through a series of elementary school classrooms and implement policies in order to reduce the number of children who become infected. 

  ## Structure
  

- [[ REQ-model]] - The model setup. This will initialise the model with all the details needed to run the simulation, it will include the generation of the students and the network, which allow for the chance of infection to be evaluated between the students.
- [[ REQ-engine]] - The model will need certain conditions to be executed.