# REQ-purpose
The goal of this project is to develop a reasonable replication of the Norovirus Model from the paper [NOROVIRUS OUTBREAKS: USING AGENT-BASED MODELING TO EVALUATE SCHOOL POLICIES](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7822182).

The model should focus on the transmission of a virus among primary school classrooms and seeing how the number of children infected can be reduced.  

The daily activities of the students are looked at and how these activities allow for students’ exposure to the virus including classroom activities and lunch. 

The last process of developing the programme will include implementing mitigation strategies. This will be done by creating two policies which would limit the amount of student-student interaction. The sooner the policy is implemented the shorter the duration of the outbreak.


## Goal

The model should simulate 6 classrooms, containing 21 students per class. 


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