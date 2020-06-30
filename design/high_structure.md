# REQ-engine
partof: REQ-purpose
###
## Engine
This will execute the model given the certain conditions.


# REQ-model
partof: REQ-Purpose
###
## Model


This initialises the model with all the details need to run the simulation, as well as, generating the agents, generating the network and setting up the connections. 

When the program is complete it will report:
- Outbreak duration (days)
- If the students are at school or at home
- The number of agents categorised by their status: "healthy", "sick" and "absent"


# REQ-SUn-network
partof: REQ-model
###
# Network Model

According to the paper, the network was created as a small world network in a lattice structure, allowing the student to pair with their niehgbours on either sides.

## Initial model parameters:

The school size is based off of:
- Classroom size = 21 students
- Number of Classrooms = 6


## Goals 

Creating Neighbour Networks:
- In the classroom, each node is given a 60% probability to rewire a connection, this will allow the nodes to pair with their neighbour on either side.

Creating Friendship Networks:
- Connections formed with other classrooms are given a 10% chance of rewiring, this allows students to have more friends other than the ones in their classroom only.

The parameters:

- Group sizes
- Average Degree
- Average Path Length
- Clustering Coefficient

Links between friends:
- Has to be greater or equal to 2


# SPC-engine
At the start of each simulation the following parameters were randomly assigned: the initial ‘sick’ student, the network connections of each student.

Each day you evaluate all the chances, therefore evaluating the chance of infection twice. This shall be when the student is in class and when the student is at lunch.


The conditions that the model shall meet are as follows:

- Generate the students
- Generate the initial 'sick' student
- Generate connections through network


# SPC-model
The main goal of the model is to generate the students and network so that the model can run and output the report.

- [[.generate_students]]: There shall be a function which generates the students for the model. The setup for this is will require to assign the parameters for the students. 
- [[.generate_sick_student]]: There shall be a function to generate the sick student.


# SPC-network
partof: REQ-SUn-network
###
The network shall be based off of a small-world network. There will be 126 nodes in the network, representing the students.

When generating the network, the friendships between the students change with the random generation of each network the overall structure remains consistent across runs.
- [[.generate_network]]: The network will be generated which will allow to assign the neighbours to each node.

The network shall allow students in a classroom to have at least two neighbours besides them to be assigned.


# TST-network