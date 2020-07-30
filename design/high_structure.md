# REQ-engine
partof: REQ-purpose
###
## Engine
For the model to be able to produce the results that we want it will have the execute given certain conditions. If these conditions are not met then the model will not do what it is intended to, which is simulate the virus spread correctly.

### This model should meet these conditions to execute the programme to run:
- An "initial" sick student, which is randomly assigned, in order to start the actual transmission of disease. 
For the initial sick student, at the beginning of the simulation, they will start off with already have the "sick" status. 
- The network connections for the students
- The assigned sizes for the classes and groups.



# REQ-model
partof: REQ-Purpose
###
## Model

This initialises the model with all the details need to run the simulation, as well as, generating the agents, generating the network and setting up the connections. 

### Setting up the model 

#### The agents for the model:

The Agents of the model will need to be setup and will be required to have certain attributes. This will include:
- Their status - healthy, sick, absent
- Days since infection
- Location - School or Home


#### Network for the model:

According to the paper, the network was created as a small-world network, this is a type of mathematical graph in which most nodes are not neighbors of one another, but the neighbors of any given node are likely to be neighbors of each other and most nodes can be reached from every other node by a small number of hops or steps. The model will be a lattice structure. An example can be seen below:

<img width="253" alt="Screenshot 2020-07-30 at 01 25 23" src="https://user-images.githubusercontent.com/33029552/88866767-8bc68700-d203-11ea-8ab9-aa084c16e26d.png">

#### The connections

As seen above from the lattice model, the conenctions between the students will be generated throughout the network. An example of this can be seen below of how the connections could be formed in the form of a lattice strcuture network.

![network](https://user-images.githubusercontent.com/33029552/88932516-19db5580-d276-11ea-8922-9bf6c7312160.png)


Creating Neighbour Networks:

- In the classroom, each person has a 60% probability to rewire a connection on, allowing students to pair with neighbours on either side of the desk. The network shall allow students in a classroom to have at least two neighbours beside them to be assigned. We can think about it as, each student having someone to left side and right side, unless they are at the corners of the classroom, where they will most likley have a neighbour on the left or right of them. 

Creating Friendship Networks:

- Connections formed with students outside of the classroom are given a 10% chance of rewiring. 


#### Model parameters:

For the model to work we will need to generate our students. The total number of students is 126.


The Initial Model parameters include: 


<img width="374" alt="Screenshot 2020-07-30 at 01 40 34" src="https://user-images.githubusercontent.com/33029552/88867559-b6b1da80-d205-11ea-8a21-fe45d4a33e81.png">

### The Model Process

The process of this model will follow a daily route to evalute the chances of exposure for the students. 

![diagramFlowChat](https://user-images.githubusercontent.com/33029552/88933839-cec24200-d277-11ea-9def-c36845917ec3.jpg)

# REQ-output
partof: REQ-purpose
###
What shall be outputted from the programme after it has been run.
### Programme Report

When the program is complete it shall report:
1. Stabilising results across runs:
- Outbreak duration (days), this will include data from multiple runs.
2. Baseline Simulation Results:

From the data that is gathered from the runs, this will allow for specific results to be acquired for analysis. The results should include:
- Duration (days)
- Duration range (days)
- Max Absentee Rate 
- Total Number of Students Affected 
- Range of students affected across runs



# SPC-engine
At the start of each simulation the following parameters shall be randomly assigned: 

In order for the simulation to commence, there will need to be the initial ‘sick’ student and the network connections of each student should be set up.

### [[.generate_students]]: generation of the students
The students for the model shall be generated. The setup for this is will require to assign the parameters for the students. All the students will have the status of "Healthy".


### [[.generate_sick_student]]: generation of random sick student

To run the simulation and for the model to do what it supposed to, which is spreading infection, an "initial" sick student will be randomly generated to start the infection spread. The attributes that this student will have are:
- Status = "Sick"
- Days since infection = 1
- Location = School

### [[.network]]: generation of the student network
The generation of the student network will allows for all the connections to be made, within the classroom and outside the classroom.


# SPC-model

The main goal of the model is to generate the students, the network of the students, connecting them to their seatmates, groups and friends, so that the model can run and output the results.


- [[.init]]: Initialise the required model parameters.


Evaluating the chances of infection:

During the 5 days, the students have a chance of being infected with the virus by their neighbours, students they connect with for group work, and their lunch. For the spread of infection to happen, the chances will have to be evaluated. 

- Neighbours and group members: The probability of getting infected is 10%.

`p_of_infection_neighbour_groups = 0.10`


- Friend: The probability of getting infected is 12%.

`p_of_infection_friend = 0.12`


Each day you evaluate all the chances, therefore evaluating the chance of infection twice. When the students are in their classroom doing group work or at lunch, the chances of them being infected shall be evaluated.
