# REQ-engine
partof: REQ-purpose
###
## Engine

### Model parameters:

For the model to work we will need to generate our students. The total number of students is 126.


The Initial Model parameters include: 


<img width="374" alt="Screenshot 2020-07-30 at 01 40 34" src="https://user-images.githubusercontent.com/33029552/88867559-b6b1da80-d205-11ea-8a21-fe45d4a33e81.png">

### The Model Process

The process of this model will follow a daily route to evalute the chances of exposure for the students. 

![diagramFlowChat](https://user-images.githubusercontent.com/33029552/88933839-cec24200-d277-11ea-9def-c36845917ec3.jpg)


# REQ-model
partof: REQ-Purpose
###
## Model



The approximate steps of implementation are as follows:

1. Initialize agents within the model.
2. Set up the friendship network
3. Initialize the disease within the model
4. Setup disease progression
5. Setup the mitigation strategies as options within the model

### Initialize agents 

The Agents of the model will be need to be initialized with three user defined attributes.

This will include:
- Their status - susceptible, infected, recovered
- Days of infection
- Location - School or Home

In total there should 126 agents within the model each segregated into six different breeds denoting the six classrooms.

#### NetLogo commands of interest:

1. "Sprout" 
2. "Breed"

### Initialize network:

#### Baseline network

The original model uses a small world network to model the connections between the agents. To create this network you first need to connect each agent to the other agents within the class room in a lattice structure which is visualised below:

<img width="253" alt="Screenshot 2020-07-30 at 01 25 23" src="https://user-images.githubusercontent.com/33029552/88866767-8bc68700-d203-11ea-8ab9-aa084c16e26d.png">

There should be six versions of this network within the model initially which will then get rewired twice.


#### Creating Neighbour Networks (Rewire 1):

The first rewire requires each connection to be evaluated. If a 60% chance is successful then the connection must be rewired to a random individual within the classroom.



#### Creating Friendship Networks (Rewire 2): 

The second rewire also requires each connection to be evaluated. If a 10% chance is successful then the connection must be rewired to a random individual in the different classroom.

#### An example finished network

![network](https://user-images.githubusercontent.com/33029552/88932516-19db5580-d276-11ea-8922-9bf6c7312160.png)

#### NetLogo commands of interest:

1. "create-link" 
2. "list"

### Initialize the disease

To initialize the disease you must change the attribute of the appropriate number of agents from susceptible to infected.

### Setup disease progression 

### Setup the mitigation strategies as options within the model


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