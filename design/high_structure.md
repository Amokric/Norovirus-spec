# REQ-engine
partof: REQ-purpose
###
## Engine
This will execute the model given certain conditions.

### This model shall meet these conditions to execute the programme:
- An "initial" sick student, which is randomly assigned, in order to start the actual transmission of disease.
- The network connections for the students
- The assigned sizes for the classes and groups.


# REQ-model
partof: REQ-Purpose
###
## Model


This initialises the model with all the details need to run the simulation, as well as, generating the agents, generating the network and setting up the connections. 

### Setting up the model 

#### Network for the model:

According to the paper, the network was created as a small-world network in a lattice structure, allowing the student to pair with their neighbours on either side.

#### Initial model parameters:

For the model to work we will need to generate our students. The total number of students is 126.

The school size is based on:

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

- In the classroom, each person has a 60% probability to rewire a connection on, allowing students to pair with neighbours on either side of the desk. The network shall allow students in a classroom to have at least two neighbours beside them to be assigned.

Creating Friendship Networks:

- Connections formed with students outside of the classroom are given a 10% chance of rewiring.


# REQ-output
partof: REQ-purpose
###
What shall be outputted from the programme after it has been run.
### Programme Report

When the program is complete it shall report:
1. Stabilising results across runs:
- Outbreak duration (days), this will include data from multiple runs.
2. Baseline Simulation Results:

From the data that is gathered from the runs, this will allow for specific results to be acquired for analysis.
- Duration (days)
- Duration range (days)
- Max Absentee Rate 
- Total Number of Students Affected 
- Range of students affected across runs

![alt text](https://github.com/[Amokric]/[Norovirus-spec]/blob/[master]/img1.png? raw=true)


# SPC-engine
At the start of each simulation the following parameters shall be randomly assigned: 

In order for the simulation to commence, there will need to be the initial ‘sick’ student and the network connections of each student should be set up.

### [[.generate_students]]: generation of the students
The students for the model shall be generated. The setup for this is will require to assign the parameters for the students. All the students will be "Healthy", except for the random "Sick" student. 

### [[.generate_sick_student]]: generation of random sick student

To run the simulation and for the model to do what it supposed to, which is spreading infection, an "initial" sick student will be randomly generated to start the infection spread.

### [[.network]]: generation of the student network
The generation of the student network will allows for all the connections to be made, within the classroom and outside the classroom.


# SPC-model

The main goal of the model is to generate the students, the network of the students, connecting them to their seatmates, groups and friends, so that the model can run and output the report.


- [[.init]]: Initialise the required model parameters.


Evaluating the chances of infection:

- Neighbours: The probability of getting infected is 10%.

`p_of_infection_neighbour = 0.10`

The neighbour chance applies to group work as well, it is the same probability.

- Friend: The probability of getting infected is 12%.

`p_of_infection_friend = 0.12`


Each day you evaluate all the chances, therefore evaluating the chance of infection twice. When the students are in their classroom doing group work or at lunch, the chances of them being infected shall be evaluated.