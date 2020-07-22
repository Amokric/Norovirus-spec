# REQ-engine
partof: REQ-purpose
###
## Engine
This will execute the model given certain conditions.

### This model shall meet these conditions to execute the programme:
- An "initial" sick student, which is randomyl assigned, in order to start the actual transmission of disease.
- The network connections for the students
- The assigned sizes for the classes and groups.


# REQ-model
partof: REQ-Purpose
###
## Model


This initialises the model with all the details need to run the simulation, as well as, generating the agents, generating the network and setting up the connections. 

### Setting up the model 

#### Network for the model:

According to the paper, the network was created as a small world network in a lattice structure, allowing the student to pair with their niehgbours on either sides.

#### Initial model parameters:

For the model to work we will need to generate our students. The total number of students is 126.

The school size is based off of:

- Classroom size = 21 students
- Number of Classrooms = 6

The other parameters that will be required are:
- Risk of Infection = 50%
- Illness Rate (Post Infection) = 10%
- Incubation period = 2 days
- Symptomatic (Isolation) period = 3 days
- School Days per Week = 5 days
- Weekend Days per Week = 2 days

#### The connections

Creating Neighbour Networks:

- In the classroom, each person has a 60% probability to rewire a connection on, allowing students to pair with neighbours on either side of the desk.

Creating Friendship Networks:

- Connections formed with students outside of the classroom are given a 10% chance of rewiring.

### Programme Report

When the program is complete it will report:
1. Stabilising results across runs:
- Outbreak duration (days), this will include data from multiple runs.
2. Baseline Simulation Results:
- Duration (days)
- Duration range (days)
- Max Absentee Rate 
- Total Number of Students Affected 
- Range of students affected across runs

# SPC-engine
At the start of each simulation the following parameters shall be randomly assigned: 

In order for the simulation to commence there will need to be the initial ‘sick’ student and the network connections of each student should be set up.

Each day you evaluate all the chances, therefore evaluating the chance of infection twice. This shall be when the student is in class and when the student is at lunch.


The conditions that the model shall meet are as follows:

- Generate the students
- Generate the initial 'sick' student
- Generate connections through network


# SPC-model

The main goal of the model is to generate the students, the network of the students, connecting them to their seatmates, groups and friends, so that the model can run and output the report.


- [[.init]]: Initialise the required model parameters.

### [[.generate_students]]: generation of the students
The students for the model shall be generated. The setup for this is will require to assign the parameters for the students. All the students will be "Healthy", except for the random "Sick" student. 

### [[.generate_sick_student]]: generation of random sick student

To run the simulation and for the model to do what it supposed to, which is spreading infection, an "initial" sick student will be randomly generated to start the infection spread.

### [[.network]]: generation of the student network
The generation of the student network wil allow for all the connections to be made, within the classroom and outside the classroom.

Evaluating chances of infection:

- Neighbours:
The probabiltiy of getting infected is 10%.

- Friend: The probabiltiy of getting infected is 12%.

When the students are in their classroom doing group work or at lunch, the chances of them being infected shall be evaluated.


# SPC-network
partof: REQ-SUn-network
###
The network shall be based off of a small-world network. There will be 126 nodes in the network, representing the students.

When generating the network, the friendships between the students change with the random generation of each network the overall structure remains consistent across runs.

- [[.generate_network]]: Generating a network to connect the students.  The structure should remain consistant while the friendships between the students change with the random generations of each network.


The network shall allow students in a classroom to have at least two neighbours besides them to be assigned.


# TST-network
## Tests

Make sure that the valid connections are being made between students. 


Students should be randomly assigned friends, there is 10% chance of being wired to someone outside of the class, which should be checked.

In the classroom, each student should at least have two links in the classroom.

In order for this to be "unit tested":