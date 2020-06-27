# REQ-SUn-network
partof: REQ-purpose
###
# Network Model

In the paper the network that is generated is a small world network of a lattice structure. Each of the frameworks will have a different way generating and creating this network.

## Methodology: Creating Friendship Networks

In the classroom, each node is given a 60% probability to rewire a connection, this will allow the nodes to pair with their neighbour on either side.

Connections formed with other classrooms are given a 10% chance of rewiring, this allows students to have more friends other than the ones in their classroom only.

The parameters in the paper are:

- Group sizes
- Average Degree
- Average Path Length
- Clustering Coefficient

Links between friends:
- Has to be greater or equal to 2


# REQ-SUp
partof: REQ-Purpose
###
## Setup


This initialises the model with all the details need to run the simulation, as well as, generating the agents and making the connections. 

When the program is complete it will report:
- The epochs
- The number of agents categorised by their status: "healthy", "sick" and "absent"


# REQ-SUp-population
## Initial model parameters:

The school size is based off of 
- Classroom size = 21 students
- Number of Classrooms = 6
