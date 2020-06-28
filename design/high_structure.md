# REQ-engine
partof: REQ-purpose
###
## Engine
This will execute the model given the certain conditions.


# REQ-model
partof: REQ-Purpose
###
## Model


This initialises the model with all the details need to run the simulation, as well as, generating the agents and making the connections. 

When the program is complete it will report:
- The epochs
- If the students are at school or at home
- The number of agents categorised by their status: "healthy", "sick" and "absent"


# REQ-SUn-network
partof: REQ-model
###
# Network Model

In the paper the network that is generated is a small world network of a lattice structure. Each of the frameworks will have a different way generating and creating this network.

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


# REQ-SUp-population
## Initial model parameters:

The school size is based off of 
- Classroom size = 21 students
- Number of Classrooms = 6


# SPC-engine
The conditions that the model shall meet are as follows:

- Generate the students


# SPC-model


# SPC-network
partof: REQ-SUn-network
###
The network shall be based off of Wattz and Strogatz small-world network.

When generating the network, the friendships between the students change with the random generation of each network the overall structure remains consistent across runs.