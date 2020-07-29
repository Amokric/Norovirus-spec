# REQ-purpose
The goal of this project is to develop a reasonable replication of the Norovirus Model from the paper [NOROVIRUS OUTBREAKS: USING AGENT-BASED MODELING TO EVALUATE SCHOOL POLICIES](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7822182).

The paper is about the transmission of a virus among primary school classrooms and seeing how the number of children is infected can be reduced.  It focuses on the daily activities that allow for students’ exposure to the virus including classroom activities and lunch. 

The last process of developing the programme will include mitigation strategies. to control the transmission, two policies were implemented to limit the amount of student-student interaction. The results demonstrated that implementation of either policy helps reduce the number of students who become ill and that the sooner the policy is implemented the shorter the duration of the outbreak.


## Goal

The model should simulate 6 classrooms, containing 21 students per class. 

Simulate the spread of norovirus through a series of elementary school classrooms and implement policies in order to reduce the number of children who become infected. 

  ## Structure
  

- [[ REQ-model]] - The model setup. This will initialise the model with all the details needed to run the simulation, it will include the generation of the students and the network, which allow for the chance of infection to be evaluated between the students.
- [[ REQ-engine]] - The model will need certain conditions to be executed.

## Setup Agents:

```dot
digraph G {
    node [shape=box];

 // join main and branch

     "SPC-DATA-FAMILY" -> "SPC-DATA-ARTIFACT"
      -> [[SPC-lint]]
      -> {done [shape=oval]};
}
}
```